# LTX-2.5 AMD RX 7900 XTX + Windows 11

## 整合包

夸克网盘：

```text
https://pan.quark.cn/s/5d693412c56d?pwd=qvDu
```

提取码：

```text
qvDu
```

## 1. 环境

| 项目 | 配置 |
|---|---|
| 系统 | Windows 11 |
| GPU | AMD Radeon RX 7900 XTX 24GB |
| 内存 | 32GB |
| 虚拟内存 | 约 124～160GB |
| ComfyUI | 0.35.0 |
| Python | 3.12.10 Embedded |
| PyTorch | 2.9.1+rocm7.2.1 |
| ROCm | 7.2.1 |
| GPU 架构 | gfx1100 |

目录：

```text
C:\AI2.5\ComfyUI_windows_portable_amd\ComfyUI_windows_portable\
```

---

## 2. ComfyUI AMD Windows Portable

[下载 ComfyUI Windows AMD Portable](https://github.com/Comfy-Org/ComfyUI/releases/latest/download/ComfyUI_windows_portable_amd.7z)

解压后：

```text
ComfyUI_windows_portable\
├── ComfyUI\
├── python_embeded\
└── run_amd_gpu.bat
```

运行：

```text
run_amd_gpu.bat
```

---

## 3. ComfyUI-GGUF

[ComfyUI-GGUF](https://github.com/city96/ComfyUI-GGUF)

### 安装位置

使用 Windows CMD 或 PowerShell，进入 **ComfyUI 便携版根目录**：

```text
C:\AI2.5\ComfyUI_windows_portable_amd\ComfyUI_windows_portable\
```

也就是能看到下面这些文件/文件夹的位置：

```text
ComfyUI\
python_embeded\
run_amd_gpu.bat
```

### 安装

在这个目录打开 CMD，执行：

```bat
git clone https://github.com/city96/ComfyUI-GGUF ComfyUI\custom_nodes\ComfyUI-GGUF
```

再执行：

```bat
.\python_embeded\python.exe -s -m pip install -r .\ComfyUI\custom_nodes\ComfyUI-GGUF\requirements.txt
```

安装完成后重启 ComfyUI。

安装后目录：

```text
ComfyUI\custom_nodes\ComfyUI-GGUF\
```

---

## 4. ComfyUI-UnloadModels

[ComfyUI-UnloadModels](https://github.com/neezoy/ComfyUI-UnloadModels)

### 安装位置

同样进入 **ComfyUI 便携版根目录**：

```text
C:\AI2.5\ComfyUI_windows_portable_amd\ComfyUI_windows_portable\
```

打开 CMD，执行：

```bat
git clone https://github.com/neezoy/ComfyUI-UnloadModels ComfyUI\custom_nodes\ComfyUI-UnloadModels
```

安装后目录：

```text
ComfyUI\custom_nodes\ComfyUI-UnloadModels\
```

重启 ComfyUI。

---

## 5. 运行方式

启动 ComfyUI 时，不需要在 GitHub 页面里运行这些 Git 项目。

直接运行便携版：

```text
run_amd_gpu.bat
```

Git 的作用只是把两个自定义节点项目下载到：

```text
ComfyUI\custom_nodes\
```

下载完成并重启 ComfyUI 后，这两个项目的节点就会出现在 ComfyUI 里。

---

## 6. LTX-2.5 模型

[LTX-2.5 官方 Hugging Face](https://huggingface.co/Lightricks/LTX-2.5)

### 5.1 Q4_K_M GGUF

```text
LTX-2.5-Distilled-Q4_K_M.gguf
```

[下载](https://huggingface.co/Abiray/LTX-2.5-Distilled-GGUF/blob/main/LTX-2.5-Distilled-Q4_K_M.gguf)

放到：

```text
ComfyUI\models\diffusion_models\
```

### 5.2 Gemma 12B

```text
gemma4-12b-with-proj-ltx-2.5-comfy-int8-convrot.safetensors
```

[下载](https://huggingface.co/Lightricks/LTX-2.5/resolve/main/text_encoders/gemma4-12b-with-proj-ltx-2.5-comfy-int8-convrot.safetensors)

放到：

```text
ComfyUI\models\text_encoders\
```

### 5.3 Video VAE

```text
ltx-2.5-video-vae-conv-bf16.safetensors
```

[下载](https://huggingface.co/Lightricks/LTX-2.5/resolve/main/vae/ltx-2.5-video-vae-conv-bf16.safetensors)

放到：

```text
ComfyUI\models\vae\
```

### 5.4 Audio VAE

```text
ltx-2.5-audio-vae-bf16.safetensors
```

[下载](https://huggingface.co/Lightricks/LTX-2.5/resolve/main/vae/ltx-2.5-audio-vae-bf16.safetensors)

放到：

```text
ComfyUI\models\vae\
```

### 5.5 Latent Spatial Upscaler

```text
ltx-2.5-latent-spatial-upscaler-x2-bf16-1.0.safetensors
```

[下载](https://huggingface.co/Lightricks/LTX-2.5/resolve/main/latent_upscale_models/ltx-2.5-latent-spatial-upscaler-x2-bf16-1.0.safetensors)

放到：

```text
ComfyUI\models\latent_upscale_models\
```

---

## 7. 模型目录

```text
ComfyUI\
└── models\
    ├── diffusion_models\
    │   └── LTX-2.5-Distilled-Q4_K_M.gguf
    │
    ├── text_encoders\
    │   └── gemma4-12b-with-proj-ltx-2.5-comfy-int8-convrot.safetensors
    │
    ├── vae\
    │   ├── ltx-2.5-video-vae-conv-bf16.safetensors
    │   └── ltx-2.5-audio-vae-bf16.safetensors
    │
    └── latent_upscale_models\
        └── ltx-2.5-latent-spatial-upscaler-x2-bf16-1.0.safetensors
```

---

## 8. 实测配置

```text
分辨率：608 × 352
帧数：121
帧率：24 FPS
时长：约 5 秒
模型：LTX-2.5 Distilled Q4_K_M
采样器：Euler Ancestral
采样步数：6 Step
```

6-Step Sigma：

```text
1.0, 0.99375, 0.9875, 0.975, 0.909375, 0.725, 0.0
```

图生视频使用首帧输入，并保留音频输出。

---

## 9. 速度实测

```text
RX 7900 XTX 24GB
608 × 352
121 帧
24 FPS
约 5 秒
Q4_K_M
6 Step
带音频
```

**实测生成时间：2 分多钟 / 5 秒视频。**
