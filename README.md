> **Recall.ai - Meeting Transcription API**
>
> Nếu bạn đang tìm kiếm một API phiên âm cho cuộc họp, hãy xem xét **[Recall.ai](https://www.recall.ai/product/meeting-transcription-api?utm_source=github&utm_medium=sponsorship&utm_campaign=jianchang512-pyvideotrans)**, một API hoạt động với Zoom, Google Meet, Microsoft Teams, và nhiều hơn nữa. Recall.ai phân định người nói (speaker diarization) bằng cách lấy dữ liệu người nói và tách các luồng âm thanh từ các nền tảng cuộc họp, điều này mang lại độ chính xác 100% khi phân định người nói với tên thật.



# pyVideoTrans

<div align="center">

**Một Công Cụ Mã Nguồn Mở Mạnh Mẽ: Dịch Video / Phiên Âm / Lồng Tiếng AI / Dịch Phụ Đề**

[Tiếng Trung](docs/README_CN.md) | [**Tài Liệu**](https://en.pyvideotrans.com) | [**Hỏi Đáp Trực Tuyến**](https://bbs.pyvideotrans.com)

[![License](https://img.shields.io/badge/License-GPL_v3-blue.svg)](LICENSE)   [![Python](https://img.shields.io/badge/Python-3.10%2B-green.svg)](https://www.python.org/)   [![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20macOS%20%7C%20Linux-lightgrey.svg)]()

</div>

**pyVideoTrans** chuyên dùng để chuyển đổi video từ ngôn ngữ này sang ngôn ngữ khác một cách liền mạch, cung cấp quy trình làm việc trọn gói bao gồm nhận dạng giọng nói, dịch phụ đề, lồng tiếng đa vai, và đồng bộ hóa âm thanh hình ảnh. Công cụ này hỗ trợ cả triển khai ngoại tuyến (offline) cục bộ và nhiều loại API trực tuyến phổ biến.

<img width="1658" height="935" alt="image" src="https://github.com/user-attachments/assets/c5959e59-6014-480c-9a7d-44c2b1729d36" />

---

## ✨ Tính Năng Cốt Lõi

- **🎥 Dịch Video Hoàn Toàn Tự Động**: Quy trình một cú nhấp chuột: Nhận dạng giọng nói (ASR) -> Dịch phụ đề -> Tổng hợp giọng nói (TTS) -> Tổng hợp video.
- **🎙️ Phiên Âm / Tạo Phụ Đề**: Chuyển đổi hàng loạt âm thanh/video thành phụ đề SRT, hỗ trợ **Phân định người nói (Speaker Diarization)** để phân biệt các vai khác nhau.
- **🗣️ Lồng Tiếng AI Đa Vai**: Gán các giọng đọc AI khác nhau cho các người nói khác nhau.
- **🧬 Nhân Bản Giọng Nói (Voice Cloning)**: Tích hợp các mô hình như **F5-TTS, CosyVoice, GPT-SoVITS** để nhân bản giọng nói zero-shot (không cần huấn luyện trước).
- **🧠 Hỗ Trợ Mô Hình Mạnh Mẽ**: 
  - **ASR**: Faster-Whisper (Cục bộ), OpenAI Whisper, Alibaba Qwen, ByteDance Volcano, Azure, Google, v.v.
  - **Dịch thuật LLM**: DeepSeek, ChatGPT, Claude, Gemini, Ollama (Cục bộ), Alibaba Bailian, v.v.
  - **TTS**: Edge-TTS (Miễn phí), OpenAI, Azure, Minimaxi, ChatTTS, ChatterBox, v.v.
- **🖥️ Chỉnh Sửa Tương Tác**: Hỗ trợ tạm dừng và hiệu đính thủ công ở từng giai đoạn (nhận dạng, dịch thuật, lồng tiếng) để đảm bảo độ chính xác.
- **🛠️ Bộ Công Cụ Tiện Ích**: Bao gồm các công cụ hỗ trợ như tách giọng hát, ghép video/phụ đề, căn chỉnh âm thanh-hình ảnh, và khớp bản ghi (transcript matching).
- **💻 Giao Diện Dòng Lệnh (CLI)**: Hỗ trợ chạy ngầm (headless), thuận tiện cho việc triển khai máy chủ hoặc xử lý hàng loạt.

<img width="2752" height="1536" alt="unnamed" src="https://github.com/user-attachments/assets/960e9e34-84a4-425d-b582-f726623475a8" />

---

## 🚀 Bắt Đầu Nhanh (Người Dùng Windows)

Chúng tôi cung cấp phiên bản `.exe` đóng gói sẵn cho người dùng Windows 10/11, không yêu cầu cấu hình môi trường Python.

1. **Tải xuống**: [Nhấn để tải phiên bản đóng gói mới nhất](https://github.com/jianchang512/pyvideotrans/releases)
2. **Giải nén**: Giải nén tệp tin nén vào một đường dẫn (ví dụ: `D:\pyVideoTrans`).
3. **Chạy**: Nhấp đúp vào `sp.exe` bên trong thư mục để khởi chạy.

> **Lưu ý**: 
> *   Không chạy trực tiếp từ bên trong tệp nén.
> *   Để sử dụng tăng tốc GPU, hãy đảm bảo đã cài đặt **CUDA 12.8** và **cuDNN 9.11**.

---

## 🛠️ Triển Khai Từ Mã Nguồn (Lập trình viên macOS / Linux / Windows)

Chúng tôi khuyên dùng **[`uv`](https://docs.astral.sh/uv/)** để quản lý gói nhằm đạt tốc độ nhanh hơn và cách ly môi trường tốt hơn.

### 1. Yêu cầu trước

*   **Python**: Khuyên dùng phiên bản 3.10 --> 3.12
*   **FFmpeg**: Phải được cài đặt và cấu hình trong biến môi trường.
    *   **macOS**: `brew install ffmpeg libsndfile git`
    *   **Linux (Ubuntu/Debian)**: `sudo apt-get install ffmpeg libsndfile1-dev`
    *   **Windows**: [Tải FFmpeg](https://ffmpeg.org/download.html) và cấu hình Path, hoặc đặt `ffmpeg.exe` và `ffprobe.exe` trực tiếp vào thư mục dự án.

### 2. Cài đặt uv (Nếu chưa cài đặt)

```bash
# macOS/Linux
curl -LsSf https://astral.sh/uv/install.sh | sh

# Windows (PowerShell)
powershell -c "irm https://astral.sh/uv/install.ps1 | iex"
```

### 3. Clone và Cài đặt

```bash
# 1. Clone kho lưu trữ (Đảm bảo đường dẫn không có dấu cách/ký tự tiếng Trung)
git clone https://github.com/jianchang512/pyvideotrans.git
cd pyvideotrans

# 2. Cài đặt các phụ thuộc (uv tự động đồng bộ môi trường)
uv sync
```

### 4. Khởi chạy Phần mềm

**Chạy GUI**:
```bash
uv run sp.py
```

**Sử dụng CLI**:

> [Xem tài liệu để biết các tham số chi tiết](https://pyvideotrans.com/cli)

```bash
# Ví dụ Dịch Video
uv run cli.py --task vtv --name "./video.mp4" --source_language_code zh --target_language_code en

# Ví dụ Âm thanh sang Phụ đề
uv run cli.py --task stt --name "./audio.wav" --model_name large-v3
```

### 5. (Tùy chọn) Cấu hình Tăng tốc GPU

Nếu bạn có card đồ họa NVIDIA, hãy thực hiện các lệnh sau để cài đặt phiên bản PyTorch hỗ trợ CUDA:

```bash
# Gỡ cài đặt phiên bản CPU
uv remove torch torchaudio

# Cài đặt phiên bản CUDA (Ví dụ cho CUDA 12.x)
uv add torch==2.7 torchaudio==2.7 --index-url https://download.pytorch.org/whl/cu128
uv add nvidia-cublas-cu12 nvidia-cudnn-cu12
```

---

## 🧩 Các Kênh & Mô Hình Được Hỗ Trợ (Một phần)

| Danh mục | Kênh/Mô hình | Mô tả |
| :--- | :--- | :--- |
| **ASR (Nhận dạng giọng nói)** | **Faster-Whisper** (Cục bộ) | Khuyên dùng, tốc độ nhanh, độ chính xác cao |
| | WhisperX / Parakeet | Hỗ trợ căn chỉnh mốc thời gian & phân định người nói |
| | Alibaba Qwen3-ASR / ByteDance Volcano | API trực tuyến, xuất sắc cho tiếng Trung |
| **Dịch thuật (LLM/MT)** | **DeepSeek** / ChatGPT | Hỗ trợ hiểu ngữ cảnh, dịch tự nhiên hơn |
| | Google / Microsoft | Dịch máy truyền thống, tốc độ nhanh |
| | Ollama / M2M100 | Dịch hoàn toàn ngoại tuyến cục bộ |
| **TTS (Tổng hợp giọng nói)** | **Edge-TTS** | Giao diện miễn phí của Microsoft, hiệu ứng tự nhiên |
| | **F5-TTS / CosyVoice** | Hỗ trợ **Nhân bản giọng nói**, yêu cầu triển khai cục bộ |
| | GPT-SoVITS / ChatTTS | TTS mã nguồn mở chất lượng cao |
| | 302.AI / OpenAI / Azure | API thương mại chất lượng cao |

---

## 📚 Tài Liệu & Hỗ Trợ

*   **Tài liệu chính thức**: [https://pyvideotrans.com](https://pyvideotrans.com) (Bao gồm hướng dẫn chi tiết, hướng dẫn cấu hình API, câu hỏi thường gặp)
*   **Cộng đồng Hỏi Đáp Trực Tuyến**: [https://bbs.pyvideotrans.com](https://bbs.pyvideotrans.com) (Gửi nhật ký lỗi để AI tự động phân tích và trả lời)

## ⚠️ Tuyên Bố Miễn Trừ Trách Nhiệm

Phần mềm này là một dự án mã nguồn mở, miễn phí và phi thương mại. Người dùng hoàn toàn chịu trách nhiệm về bất kỳ hậu quả pháp lý nào phát sinh từ việc sử dụng phần mềm này (bao gồm nhưng không giới hạn ở việc gọi API của bên thứ ba hoặc xử lý nội dung video có bản quyền). Vui lòng tuân thủ luật pháp và quy định của địa phương cũng như các điều khoản sử dụng của các nhà cung cấp dịch vụ liên quan.

## 🙏 Lời Cảm Ơn

Dự án này chủ yếu dựa trên các dự án mã nguồn mở sau (một phần):

*   [FFmpeg](https://github.com/FFmpeg/FFmpeg)
*   [PySide6](https://pypi.org/project/PySide6/)
*   [faster-whisper](https://github.com/SYSTRAN/faster-whisper)
*   [openai-whisper](https://github.com/openai/whisper)
*   [edge-tts](https://github.com/rany2/edge-tts)
*   [F5-TTS](https://github.com/SWivid/F5-TTS)
*   [CosyVoice](https://github.com/FunAudioLLM/CosyVoice)

---

*Được tạo bởi [jianchang512](https://github.com/jianchang512)*