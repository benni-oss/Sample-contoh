# 🚀 HexStrike AI - Panduan Mudah

## 🎯 Cara Menjalankan Sistem (3 Langkah Mudah)

### 1️⃣ Setup Awal (Sekali Saja)
```bash
# Masuk ke direktori
cd /home/pentest/Documents/myAI/Final_AI

# Edit API key OpenRouter
nano .env
# Ganti "your_openrouter_api_key_here" dengan API key asli Anda
```

### 2️⃣ Jalankan Sistem
```bash
# Cara termudah - jalankan script otomatis
./quick_start.sh
```

### 3️⃣ Integrasi dengan Cursor
```bash
# Setup Cursor integration
./setup_cursor_integration.sh

# Ikuti instruksi yang muncul
```

## ✅ Verifikasi Sistem Berjalan

### Cek Status
```bash
# Test sistem lengkap
python3 demo_system.py
```

### Cek Server
```bash
# HexStrike server
curl http://127.0.0.1:8888/health

# RAG bridge
curl http://127.0.0.1:8889/api/health
```

## 🛠️ Tools yang Tersedia di Cursor

Setelah integrasi, tools berikut tersedia di Cursor AI chat:

1. **`rag_enhanced_nmap_scan`** - Scan jaringan dengan AI
2. **`rag_enhanced_nuclei_scan`** - Scan vulnerability cerdas
3. **`security_intelligence_query`** - Analisis threat dengan RAG
4. **`threat_correlation_analysis`** - Korelasi threat lanjutan
5. **`intelligent_vulnerability_assessment`** - Assessment AI
6. **`export_security_report`** - Export laporan keamanan
7. **`rag_system_stats`** - Monitoring sistem

## 🧪 Contoh Penggunaan di Cursor

### Scan Jaringan
```
rag_enhanced_nmap_scan(
  target="192.168.1.1",
  scan_type="-sV -sC",
  ports="22,80,443",
  enable_rag=true
)
```

### Query Intelligence
```
security_intelligence_query(
  query="SQL injection vulnerabilities",
  limit=10
)
```

### Cek Status Sistem
```
rag_system_stats()
```

## 🔧 Troubleshooting Cepat

### Port Sudah Digunakan
```bash
# Kill process yang menggunakan port
sudo pkill -f "hexstrike"
sudo pkill -f "rag_integration"
```

### Dependencies Error
```bash
# Reinstall dependencies
pip install -r enhanced_requirements.txt --break-system-packages --force-reinstall
```

### API Key Error
```bash
# Cek API key di .env
cat .env | grep OPENROUTER_API_KEY
```

## 📁 File Penting

- `quick_start.sh` - Script untuk menjalankan sistem
- `setup_cursor_integration.sh` - Script setup Cursor
- `demo_system.py` - Test sistem lengkap
- `.env` - Konfigurasi API key
- `STEP_BY_STEP_GUIDE.md` - Panduan detail

## 🎉 Status Sistem

✅ **HexStrike AI Server**: Running (Port 8888)
✅ **RAG Integration**: Working dengan Qdrant
✅ **MCP Server**: Ready untuk Cursor
✅ **Vector Database**: Qdrant (In-Memory)
✅ **AI Models**: Sentence Transformers
✅ **Security Tools**: 76/127 tersedia

## 🆘 Bantuan

Jika ada masalah:
1. Cek log: `tail -f integrated_hexstrike_system.log`
2. Test sistem: `python3 demo_system.py`
3. Restart sistem: `./quick_start.sh`

---

**🚀 Sistem HexStrike AI siap untuk revolusi cybersecurity workflow Anda!**
