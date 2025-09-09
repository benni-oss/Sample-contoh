# 🚀 HexStrike AI - Panduan Step-by-Step

## 📋 Persiapan Awal

### Step 1: Verifikasi Environment
```bash
# Pastikan Anda berada di direktori yang benar
cd /home/pentest/Documents/myAI/Final_AI

# Cek Python version (harus 3.8+)
python3 --version
```

### Step 2: Install Dependencies
```bash
# Install semua dependencies yang diperlukan
pip install -r enhanced_requirements.txt --break-system-packages
```

### Step 3: Setup Environment Variables
```bash
# Edit file .env dengan API key OpenRouter Anda
nano .env
```

**Isi file .env dengan:**
```env
# OpenRouter API Configuration
OPENROUTER_API_KEY=your_actual_openrouter_api_key_here

# HexStrike Configuration
HEXSTRIKE_HOST=127.0.0.1
HEXSTRIKE_PORT=8888

# RAG Integration Configuration
RAG_HOST=127.0.0.1
RAG_PORT=8889

# Qdrant Configuration
QDRANT_HOST=localhost
QDRANT_PORT=6333
QDRANT_USE_MEMORY=true

# Logging Configuration
LOG_LEVEL=INFO
ENABLE_DEBUG=false

# Performance Configuration
MAX_WORKERS=8
BATCH_SIZE=50
PROCESSING_INTERVAL=5.0
```

## 🚀 Cara Menjalankan Sistem

### Metode 1: Menggunakan Script Otomatis (RECOMMENDED)
```bash
# Berikan permission execute
chmod +x start_hexstrike.sh

# Jalankan sistem
./start_hexstrike.sh
```

### Metode 2: Manual Step-by-Step

#### Step 1: Start HexStrike AI Server
```bash
# Terminal 1 - Jalankan HexStrike Server
cd /home/pentest/Documents/myAI/Final_AI
python3 hexstrike-ai/hexstrike_server.py --host 127.0.0.1 --port 8888
```

#### Step 2: Start RAG Integration Bridge
```bash
# Terminal 2 - Jalankan RAG Bridge
cd /home/pentest/Documents/myAI/Final_AI
python3 hexstrike_rag_integration.py
```

#### Step 3: Start MCP Server
```bash
# Terminal 3 - Jalankan MCP Server
cd /home/pentest/Documents/myAI/Final_AI
python3 hexstrike_rag_mcp.py --hexstrike-server http://127.0.0.1:8888 --rag-server http://127.0.0.1:8889
```

### Metode 3: Menggunakan Integrated System (ALL-IN-ONE)
```bash
# Jalankan semua komponen sekaligus
python3 integrated_hexstrike_system.py
```

## ✅ Verifikasi Sistem Berjalan

### Step 1: Cek Status HexStrike Server
```bash
curl http://127.0.0.1:8888/health
```

**Output yang diharapkan:**
```json
{
  "status": "healthy",
  "message": "HexStrike AI Tools API Server is operational",
  "total_tools_available": 76,
  "uptime": 1234.56
}
```

### Step 2: Cek Status RAG Bridge
```bash
curl http://127.0.0.1:8889/api/health
```

**Output yang diharapkan:**
```json
{
  "status": "healthy",
  "timestamp": "2024-01-01T12:00:00Z",
  "bridge_active": true
}
```

### Step 3: Test Sistem Lengkap
```bash
python3 demo_system.py
```

## 🎯 Integrasi dengan Cursor

### Step 1: Buka Cursor Settings
1. Buka Cursor
2. Tekan `Ctrl+,` (atau `Cmd+,` di Mac)
3. Cari "MCP" di search bar

### Step 2: Tambahkan MCP Server
1. Klik "Add MCP Server"
2. Gunakan konfigurasi berikut:

```json
{
  "mcpServers": {
    "hexstrike-rag-ai": {
      "command": "python3",
      "args": ["/home/pentest/Documents/myAI/Final_AI/hexstrike_rag_mcp.py"],
      "env": {
        "HEXSTRIKE_SERVER": "http://127.0.0.1:8888",
        "RAG_SERVER": "http://127.0.0.1:8889",
        "OPENROUTER_API_KEY": "your_actual_openrouter_api_key_here"
      }
    }
  }
}
```

### Step 3: Restart Cursor
1. Restart Cursor untuk memuat konfigurasi MCP
2. Buka AI chat
3. Tools HexStrike akan tersedia

## 🧪 Testing Tools di Cursor

### Test 1: Network Scan dengan RAG
```
rag_enhanced_nmap_scan(
  target="192.168.1.1",
  scan_type="-sV -sC",
  ports="22,80,443",
  enable_rag=true
)
```

### Test 2: Vulnerability Scan
```
rag_enhanced_nuclei_scan(
  target="192.168.1.1",
  severity="critical,high,medium",
  enable_rag=true
)
```

### Test 3: Security Intelligence Query
```
security_intelligence_query(
  query="SQL injection vulnerabilities",
  limit=10,
  include_metadata=true
)
```

### Test 4: System Statistics
```
rag_system_stats()
```

## 🔧 Troubleshooting

### Problem 1: Port Already in Use
```bash
# Cek port yang digunakan
sudo netstat -tulpn | grep :8888
sudo netstat -tulpn | grep :8889

# Kill process jika diperlukan
sudo kill -9 <PID>
```

### Problem 2: Dependencies Missing
```bash
# Reinstall dependencies
pip install -r enhanced_requirements.txt --break-system-packages --force-reinstall
```

### Problem 3: OpenRouter API Key Error
```bash
# Pastikan API key valid di .env
cat .env | grep OPENROUTER_API_KEY
```

### Problem 4: MCP Server Not Found in Cursor
1. Pastikan path absolut benar di konfigurasi MCP
2. Restart Cursor
3. Cek log Cursor untuk error messages

## 📊 Monitoring Sistem

### Cek Logs
```bash
# Log sistem terintegrasi
tail -f integrated_hexstrike_system.log

# Log RAG integration
tail -f hexstrike_rag_integration.log

# Log launcher
tail -f integration_launcher.log
```

### Cek Status Real-time
```bash
# Status HexStrike
curl -s http://127.0.0.1:8888/health | jq

# Status RAG
curl -s http://127.0.0.1:8889/api/stats | jq
```

## 🛑 Menghentikan Sistem

### Graceful Shutdown
```bash
# Tekan Ctrl+C di terminal yang menjalankan sistem
# Atau gunakan:
pkill -f "hexstrike"
pkill -f "rag_integration"
pkill -f "mcp"
```

### Force Kill (jika diperlukan)
```bash
sudo pkill -9 -f "hexstrike"
sudo pkill -9 -f "rag_integration"
sudo pkill -9 -f "mcp"
```

## 🎉 Success Indicators

Sistem berjalan dengan benar jika:

✅ **HexStrike Server**: `curl http://127.0.0.1:8888/health` mengembalikan status "healthy"
✅ **RAG Bridge**: `curl http://127.0.0.1:8889/api/health` mengembalikan status "healthy"
✅ **MCP Tools**: Tersedia di Cursor AI chat
✅ **Demo Test**: `python3 demo_system.py` berhasil tanpa error

## 📞 Support

Jika mengalami masalah:
1. Cek log files untuk error messages
2. Pastikan semua dependencies terinstall
3. Verifikasi API key OpenRouter valid
4. Pastikan port 8888 dan 8889 tidak digunakan aplikasi lain

---

**🚀 Sistem HexStrike AI siap untuk revolusi cybersecurity workflow Anda!**
