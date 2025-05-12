**RVC AI 声音模型培养 (适配 Windows PC + RTX 3080Ti)
步骤教程 Step-by-Step**

---

### 📄 第一步: 环境准备

**1. 安装 Python 3.8-3.10**

* 访问: [https://www.python.org/downloads/](https://www.python.org/downloads/)
* 选择 3.10.x 版本, 安装时勾选 "Add Python to PATH"

**2. 安装 Git**

* 访问: [https://git-scm.com/](https://git-scm.com/)

**3. 安装 ffmpeg**

* 访问: [https://ffmpeg.org/download.html](https://ffmpeg.org/download.html)
* 把 ffmpeg 路径添加到 Windows 环境变量 PATH

**4. 安装 PyTorch (CUDA)**

* 访问: [https://pytorch.org/get-started/locally/](https://pytorch.org/get-started/locally/)
* 选择: Windows + Pip + Python 3.10 + CUDA 11.8

```bash
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118
```

---

### 🌟 第二步: 克隆 RVC WebUI 项目

```bash
git clone https://github.com/RVC-Project/Retrieval-based-Voice-Conversion-WebUI
cd Retrieval-based-Voice-Conversion-WebUI
```

**安装所有依赖**

```bash
pip install -r requirements.txt
```

---

### 🎙️ 第三步: 准备输入音频

1. 在 `dataset_raw` 文件夹下新建文件夹，名称为你想训练的声音名 (e.g. `Sol`)
2. 将你已录制好的音频 WAV (推荐 16kHz/48kHz mono) 放入

---

### 🔧 第四步: 预处理 + 分割

**1. 执行分割脚本**

```bash
python infer/modules/train/preprocess.py
```

* 会根据音频分割分段

**2. 执行 f0 抓取 (音高特征)**

```bash
python infer/modules/train/extract_f0_print.py
```

---

### 🚀 第五步: 开始训练 Voice Weights

**编辑 `trainset_preprocess_config.yaml`或使用默认配置同样可以**

**运行训练脚本：**

```bash
python train.py -n Sol -t 100 -sr 40k -e 10
```

* `-n Sol` 是模型名
* `-t 100` 是最大 epoch
* `-sr 40k` 是 sampling rate
* `-e 10` 是每 10 epoch 保存一次 checkpoints

**结束后会产生 .pth 文件，即为 Voice Weights**

---

### 🎶 第六步: 用 RVC 合成歌曲

1. 打开 WebUI

```bash
python infer-web.py
```

2. 选择刚才训好的 Voice Model (.pth)
3. 上传想要合成的音频 (可以是原始vocal或已分载的 acapella)
4. 一键生成转声歌曲

---

### ✅ 附加提示

* 如果想用 GUI 开启：可以用 Gradio 项目中的 `webui.bat`
* 未来想更新声音可以在新音频培养旧模型
* 注意声音样本纯度：无歌声，无背景，没有本地控声器

---

我可以接着为你准备 Sol / Monday / Cove 训练词料，让你直接录音用。
