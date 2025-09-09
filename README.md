# HexStrike AI - Integrated RAG System

🚀 **Complete cybersecurity intelligence platform with AI-powered threat analysis and real-time processing**

## Overview

HexStrike AI is an advanced cybersecurity platform that combines traditional penetration testing tools with cutting-edge AI capabilities. The integrated RAG (Retrieval-Augmented Generation) system provides intelligent threat analysis, correlation, and real-time security event processing.

### Key Features

- 🔍 **AI-Powered Security Analysis**: Real-time threat detection and analysis
- 📊 **Advanced Vector Search**: Qdrant-based intelligent data retrieval
- 🤖 **MCP Integration**: Seamless integration with AI agents and Cursor
- 🔥 **Real-time Processing**: Live security event streaming and analysis
- 📈 **Threat Correlation**: Advanced pattern recognition and threat intelligence
- 🛡️ **Comprehensive Testing**: Full penetration testing toolkit integration

## Architecture

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   HexStrike     │    │   RAG Bridge    │    │   Qdrant DB     │
│   AI Server     │◄──►│   Integration   │◄──►│   Vector Store  │
│   (Port 8888)   │    │   (Port 8889)   │    │   (In-Memory)   │
└─────────────────┘    └─────────────────┘    └─────────────────┘
         │                       │                       │
         │                       │                       │
         ▼                       ▼                       ▼
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Enhanced      │    │   AI Models     │    │   Security      │
│   MCP Server    │    │   (OpenRouter)  │    │   Intelligence  │
│   (hexstrike-   │    │                 │    │   Database      │
│   rag-ai)       │    │                 │    │                 │
└─────────────────┘    └─────────────────┘    └─────────────────┘
```

## Components

### 1. HexStrike AI Server
- Core penetration testing engine
- RESTful API for tool execution
- Real-time event streaming
- Health monitoring and status

### 2. RAG Integration Bridge
- Real-time event processing
- AI-powered data normalization
- Vector embedding and storage
- Intelligent query processing

### 3. Qdrant Vector Database
- High-performance vector storage
- Similarity search capabilities
- Metadata filtering
- Scalable architecture

### 4. Enhanced MCP Server
- AI agent integration
- Advanced security tools
- RAG-powered intelligence
- Cursor-ready configuration

## Quick Start

### Prerequisites

- Python 3.8+
- OpenRouter API key
- Required system dependencies

### Installation

1. **Clone and setup**:
```bash
cd /home/pentest/Documents/myAI/Final_AI
```

2. **Install dependencies**:
```bash
pip install -r enhanced_requirements.txt
```

3. **Configure environment**:
```bash
# Edit .env file with your OpenRouter API key
OPENROUTER_API_KEY=your_openrouter_api_key_here
```

4. **Run the integrated system**:
```bash
python integrated_hexstrike_system.py
```

### Testing

Run the comprehensive test suite:
```bash
python test_integration.py
```

## Configuration

### Environment Variables

Create a `.env` file with the following variables:

```env
# OpenRouter API Configuration
OPENROUTER_API_KEY=your_openrouter_api_key_here

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
```

### Integration Configuration

The `integration_config.json` file contains detailed configuration for all components:

```json
{
  "servers": {
    "hexstrike": {"host": "127.0.0.1", "port": 8888},
    "rag_integration": {"host": "127.0.0.1", "port": 8889}
  },
  "storage": {
    "vector_database": "qdrant",
    "collection_name": "hexstrike_data",
    "embedding_model": "sentence-transformers/all-MiniLM-L6-v2"
  },
  "processing": {
    "batch_size": 50,
    "processing_interval": 5.0,
    "enable_real_time": true
  }
}
```

## Cursor Integration

### Setup

1. **Add MCP server to Cursor settings**:
   - Open Cursor settings
   - Navigate to MCP servers
   - Add the configuration from `hexstrike-rag-mcp-config.json`

2. **Configure server**:
```json
{
  "mcpServers": {
    "hexstrike-rag-ai": {
      "command": "python",
      "args": ["hexstrike_rag_mcp.py"],
      "env": {
        "OPENROUTER_API_KEY": "your_api_key_here"
      }
    }
  }
}
```

### Available Tools

Once integrated, the following tools are available in Cursor:

- **`rag_enhanced_nmap_scan`**: AI-powered network scanning with automatic RAG processing
- **`rag_enhanced_nuclei_scan`**: Intelligent vulnerability scanning with threat correlation
- **`security_intelligence_query`**: RAG-powered security intelligence queries
- **`threat_correlation_analysis`**: Advanced threat correlation and analysis
- **`intelligent_vulnerability_assessment`**: AI-powered comprehensive vulnerability assessment
- **`export_security_report`**: Export security intelligence reports
- **`rag_system_stats`**: System performance and statistics monitoring

## Usage Examples

### Basic Network Scan with RAG Processing

```python
# In Cursor AI chat
rag_enhanced_nmap_scan(
    target="192.168.1.1",
    scan_type="-sV -sC",
    ports="22,80,443,8080",
    enable_rag=True
)
```

### Security Intelligence Query

```python
security_intelligence_query(
    query="SQL injection vulnerabilities on web applications",
    limit=10,
    include_metadata=True
)
```

### Threat Correlation Analysis

```python
threat_correlation_analysis(
    target="192.168.1.100",
    timeframe="24h",
    correlation_threshold=0.8
)
```

### Comprehensive Vulnerability Assessment

```python
intelligent_vulnerability_assessment(
    target="example.com",
    assessment_type="comprehensive",
    use_ai_prioritization=True
)
```

## API Endpoints

### HexStrike Server (Port 8888)

- `GET /health` - Health check
- `POST /api/command` - Execute security tools
- `GET /api/status` - Server status

### RAG Integration Bridge (Port 8889)

- `GET /api/health` - Health check
- `POST /api/events` - Process security events
- `GET /api/query` - Query security intelligence
- `GET /api/stats` - System statistics
- `GET /api/export` - Export security reports

## Development

### Project Structure

```
Final_AI/
├── hexstrike-ai/                 # Core HexStrike AI components
│   ├── hexstrike_server.py      # Main server
│   └── assets/                  # UI assets
├── RAG_Integration/             # RAG system components
│   ├── rag_hexstrike.py        # Qdrant integration
│   └── hexstrike_ai_listener.py # AI listener
├── hexstrike_rag_integration.py # Integration bridge
├── hexstrike_rag_mcp.py        # MCP server
├── integrated_hexstrike_system.py # Complete system launcher
├── test_integration.py         # Test suite
├── integration_config.json     # Configuration
└── enhanced_requirements.txt   # Dependencies
```

### Adding New Tools

1. **Add tool to HexStrike server**
2. **Update RAG processing** in `rag_hexstrike.py`
3. **Add MCP tool** in `hexstrike_rag_mcp.py`
4. **Update configuration** in `integration_config.json`
5. **Add tests** in `test_integration.py`

### Testing

Run individual test categories:
```bash
# Test specific component
python -c "
import asyncio
from test_integration import IntegrationTester
tester = IntegrationTester()
asyncio.run(tester._test_qdrant_database())
"
```

## Troubleshooting

### Common Issues

1. **OpenRouter API Key Missing**:
   - Ensure `.env` file exists with valid API key
   - Check API key permissions and credits

2. **Port Conflicts**:
   - Verify ports 8888 and 8889 are available
   - Update configuration if needed

3. **Dependencies Issues**:
   - Run `pip install -r enhanced_requirements.txt --upgrade`
   - Check Python version (3.8+ required)

4. **Qdrant Connection Issues**:
   - Verify Qdrant client installation
   - Check memory availability for in-memory mode

### Logs

- **System logs**: `integrated_hexstrike_system.log`
- **Integration logs**: `hexstrike_rag_integration.log`
- **Test logs**: Console output and `integration_test_report.md`

### Performance Tuning

- **Batch size**: Adjust `batch_size` in configuration
- **Processing interval**: Modify `processing_interval` for real-time vs batch processing
- **Memory usage**: Monitor Qdrant memory consumption
- **API rate limits**: Configure OpenRouter API usage

## Security Considerations

- **API Keys**: Store securely in `.env` file, never commit to version control
- **Network Access**: Configure firewall rules for production deployment
- **Data Privacy**: Ensure compliance with data protection regulations
- **Access Control**: Implement proper authentication for production use

## Contributing

1. Fork the repository
2. Create a feature branch
3. Add tests for new functionality
4. Ensure all tests pass
5. Submit a pull request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Support

For support and questions:
- Create an issue in the repository
- Check the troubleshooting section
- Review the test reports for system status

---

**🚀 Ready to revolutionize your cybersecurity workflow with AI-powered intelligence!**
