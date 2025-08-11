## 如何使用

![[Screenshot 2025-08-08 16.25.53.jpg]]
## 创建「快速操作」

右侧工作区，新建「快速操作」，工作流程收到当前「==文件或文件夹==」，位于「==访达==」。
搜索「==运行Shell脚本==」并添加到右侧工作区，传递输入：‼️==作为自变量==。
粘贴脚本：

```
# 遍历传递给脚本的每个文件
for f in "$@"
do
    # 如果文件路径为空，跳过
    if [ -z "$f" ]; then
        continue
    fi

    # 获取文件名、扩展名以及去除扩展名的文件名
    filename=$(basename "$f")
    extension="${filename##*.}"
    filename_noext="${filename%.*}"

    # 输出转换路径
    output_dir=$(dirname "$f")
    output_file="${output_dir}/${filename_noext}_encoded.${extension}"

    # ⚠️指定完整的 ffmpeg 路径
    FFMPEG_PATH="/opt/homebrew/bin/ffmpeg"

	# 记录开始时间
    start_time=$(date +%s)

	# 执行 ffmpeg 命令
	$FFMPEG_PATH -i "$f" \
    	-c:v hevc_videotoolbox \
		-q:v 60 \
		-tag:v hvc1 \
		-c:a copy \
	    -movflags +faststart \
		-strict -2 \
    	-map_metadata 0 \
	    -y "$output_file"

	# 记录结束时间
    end_time=$(date +%s)
    
    # 计算耗时（秒）
    duration=$((end_time - start_time))
    
    # 输出编码用时到日志
    # echo "编码用时: $duration 秒" >> ~/Desktop/automator_log.txt
	
	# 语音播报编码完成以及用时
	# say "编码完成，总用时 $duration 秒"

    # 检查编码是否成功
    if [ $? -eq 0 ]; then
        echo "✌️编码成功: $output_file"
        # 删除原视频文件
		rm "$f"
    else
        echo "编码失败: 请查看日志文件 ~/Desktop/automator_log.txt" >> ~/Desktop/automator_log.txt
    fi
done
```

## ffmpeg 一些配置参数说明：

```
	-c:v libx265 \            # 使用 H.265 编码
	-c:v libx264 \            # 使用 H.264 编码
	-preset ultrafast \        # 使用 'ultrafast' 预设提高编码速度
	-crf 23 \                  # CRF 23，较低的 CRF 值会提供更高的质量，但文件更大
	
	-c:v h264_videotoolbox \  # 使用 VideoToolbox（硬件加速）H.264 编码
	-c:v hevc_videotoolbox \  # 使用 VideoToolbox（硬件加速）H.265 编码
	-q:v 75 \  # 硬件编码的质量，值越小画质越高（建议 60-75 为平衡点）
	-b:v 6000k     # 直接限制目标码率（与 `-q:v` 二选一）
	-maxrate 8000k # 峰值码率（需配合 `-bufsize`）
	
	-tag:v hvc1 \              # ⚠️将视频标签从hev1改为hvc1（Mac上才可空格预览）
    -movflags +faststart \     # 优化流式播放（默认加上即可）
    
    -c:a copy \               # 音频轨道直接复制，不做任何修改
    
    -map_metadata 0 \          # 保留元数据
    
    -y "$output_file"          # 覆盖相同文件名的文件，无需确认
```

`-preset` 控制==软件编码==速度，选 `ultrafast` 拥有最快编码速度，搭配`-crf` 在编码速度和质量之间实现平衡。

`videotoolbox` 则采用==硬件编码==，此时 `-preset` 和 `-crf` 控制不起作用，可以用 `-q` 控制编码质量（代替 `-preset`）。建议值_：`-q:v <50-100>` 值越小画质越高（建议 65-75 为平衡点）。

`-preset ultrafast` 会比 `-preset fast` 编码速度快 1 倍，视频码率低近一倍，相应的，编码后视频体积也小近一倍。

`-c:v hevc_videotoolbox \` （开启硬件加速HEVC编码）速度再快一倍，编码后视频体积略变大。

## 容易踩的坑：

1. 赋予 Automator（自动操作） ==完全磁盘访问权限==
2. 传递输入：==作为自变量==
3. 使用完整路径调用 ffmpeg
4. ffmpeg 的每一行参数后面不能加注释
5. 修改编码标签为 hvc1


## 其他补充

作为各类动作基础的 Workflow 也可以随时转换成别的动作（其实任何动作都能够互相转换）。方法是在 Automator 里按下 ==shift - option - command - C== 进行格式转换，然后保存。


不同类型的 Automator 动作在 macOS 中保存的位置：

- 快速操作：`~/Library/Services`
- 日历提醒：`~/Library/Workflows/Applications/Calendar`
- 文件夹动作：`~/Library/Workflows/Applications/Folder Actions`
- 图片捕捉插件：`~/Library/Workflows/Applications/Image Capture`
- 听写命令： `~/Library/Speech/Speakable Items`
- 打印插件： `~/Library/PDF Services`

