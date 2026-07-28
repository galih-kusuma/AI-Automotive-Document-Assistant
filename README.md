# AI Automotive Document Assistant

**AI Automotive Document Assistant** adalah sistem *Retrieval-Augmented Generation* (RAG) berbasis **Langflow**, **Astra DB**, dan **Google Generative AI (Gemini)**. Sistem ini dirancang untuk memproses dokumen kendaraan (seperti PDF/surat kendaraan) dan memberikan informasi presisi mengenai perpanjangan, pajak, serta administrasi otomotif.

---

## 🏗️ Arsitektur Pipeline (Langflow)

Sistem ini terdiri dari 2 alur utama (*Flows*):

1. **Data Ingestion Flow**:
   - Membaca dokumen referensi otomotif (`Read File`).
   - Pemotongan teks (`Split Text` dengan chunk size 1000).
   - Vektorisasi teks menggunakan `models/gemini-embedding-001`.
   - Penyimpanan vektor ke **Astra DB**.

2. **AI Agent Flow**:
   - Menerima pertanyaan pengguna (`Chat Input`)[cite: 1].
   - Mencari konteks relevan di **Astra DB** (`Vector Search`)[cite: 1].
   - Memproses konteks melalui `Prompt Template` & `Parser`[cite: 1].
   - Menggenerasi jawaban menggunakan `Gemini 3.5 Flash`[cite: 1].

---

## 🚀 Cara Penggunaan

1. **Clone Repositori**:
   ```bash
   git clone [https://github.com/galih-kusuma/AI-Automotive-Document-Assistant.git](https://github.com/galih-kusuma/AI-Automotive-Document-Assistant.git)
