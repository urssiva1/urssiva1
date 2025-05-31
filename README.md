# 🏠 KinAI Vision
### *Advanced AI-Powered Smart Home Surveillance & Automation Platform*

<div align="center">

![KinAI Vision Banner](https://img.shields.io/badge/KinAI-Vision-4A90E2?style=for-the-badge&logo=home-assistant&logoColor=white)

**🔮 Intelligent Surveillance** • **🤖 Smart Automation** • **💬 Personalized Greetings** • **🎵 Music Control** • **🌤️ Weather Integration**

[![Python 3.9+](https://img.shields.io/badge/Python-3.9+-3776AB?style=flat-square&logo=python&logoColor=white)](https://python.org/)
[![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-336791?style=flat-square&logo=postgresql&logoColor=white)](https://postgresql.org/)
[![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)](https://docker.com/)
[![CUDA](https://img.shields.io/badge/CUDA-76B900?style=flat-square&logo=nvidia&logoColor=white)](https://developer.nvidia.com/cuda-zone)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](https://opensource.org/licenses/MIT)

</div>

---

## 🌟 What is KinAI Vision?

KinAI Vision transforms your home into an **intelligent living ecosystem** that recognizes you, welcomes you personally, and automatically adapts to your presence. Imagine walking through your front door and being greeted by name with current weather updates, while your lights illuminate, favorite music begins playing, and climate control adjusts to perfect comfort - all seamlessly automated! 

### 🎯 Perfect For:
- 👨‍👩‍👧‍👦 **Families** seeking personalized smart home experiences
- 🏠 **Smart Home Enthusiasts** wanting AI-powered automation
- 🔒 **Security-Conscious Users** requiring intelligent surveillance
- 🎵 **Music Lovers** enjoying automated ambiance control
- 🙏 **Devotional Families** following Hindu worship traditions
- 🏢 **Small Businesses** needing intelligent access monitoring

---

## ✨ Key Features

<table>
<tr>
<td width="50%">

### 👁️ **Advanced Facial Recognition**
- 🧠 **YOLOv8 + InsightFace**: Precise person detection & robust facial embedding
- 🎯 **High Accuracy**: Configurable thresholds for optimal performance
- 👥 **Family Profiles**: Multi-person recognition with group scenarios
- 🔍 **Visitor Tracking**: ULID-based unknown visitor identification
- 📸 **Dynamic Updates**: Easy addition of new family members

</td>
<td width="50%">

### 🏡 **Intelligent Home Automation**
- 💡 **Smart Lighting**: Sunset-aware illumination control via Home Assistant
- ❄️ **Climate Control**: Automated AC/thermostat adjustments
- 🎵 **Music Integration**: Jellyfin playlist automation based on presence
- 🙏 **Devotional Scheduling**: Hindu calendar-based spiritual music automation
- 🌅 **Astronomical Data**: Astral library for time-based automation
- ⚙️ **Adaptive Rules**: Dynamic automation based on detection patterns

</td>
</tr>
<tr>
<td width="50%">

### 💬 **Personalized AI Greetings**
- 🌤️ **Weather Integration**: Real-time OpenWeatherMap data inclusion
- 🤖 **LangChain + CrewAI**: Natural language greeting generation
- 👥 **Context Awareness**: Family history and preference incorporation
- 🕐 **Temporal Messaging**: Time-appropriate personalized greetings
- 📱 **Multi-Platform**: Smart displays and Telegram delivery

</td>
<td width="50%">

### 📊 **Comprehensive Monitoring**
- 📈 **Event Analytics**: Detailed detection and activity tracking
- 📸 **Photo Archive**: Organized detection images by date/identity
- 📝 **Audit Logging**: Complete system activity trail
- 🔔 **Real-time Alerts**: Telegram notifications for security events
- 📊 **Performance Metrics**: System health and efficiency monitoring

</td>
</tr>
</table>

---

## 🏗️ System Architecture

### 🔧 **Technology Stack**

<div align="center">

**🐍 Python 3.9+** • **🚀 FastAPI** • **🐘 PostgreSQL** • **🔄 Celery** • **📦 Redis** • **🐳 Docker** • **🧠 YOLOv8** • **👤 InsightFace** • **🤖 LangChain** • **⚡ CrewAI**

</div>

```mermaid
graph TB
    subgraph "🎥 Computer Vision Layer"
        A[📹 Video Input] --> B[🎯 YOLOv8 Detection]
        B --> C[👤 InsightFace Recognition]
        C --> D[🧮 Embedding Processing]
    end
    
    subgraph "🧠 AI Processing Layer"
        E[🔗 LangChain] --> F[⚡ CrewAI Agents]
        F --> G[🦙 Ollama Models]
        G --> H[🌤️ Weather API]
    end
    
    subgraph "⚡ Application Layer"
        I[🚀 FastAPI Server] --> J[🔄 Celery Workers]
        J --> K[📦 Redis Broker]
        K --> L[📅 Celery Beat]
    end
    
    subgraph "💾 Data Layer"
        M[🐘 PostgreSQL] --> N[🔗 SQLAlchemy ORM]
        N --> O[📊 JSONB Events]
    end
    
    D --> I
    H --> J
    L --> E
    O --> C
```

### 🐳 **Microservices Architecture**

| Service | Technology | Purpose | Port | Status |
|---------|------------|---------|------|--------|
| **🚀 FastAPI** | Python 3.9+ + Uvicorn | REST API & Webhooks | 8000 | ![Status](https://img.shields.io/badge/Active-green) |
| **👁️ Kinwatch Agent** | OpenCV + CUDA | Video Processing | - | ![Status](https://img.shields.io/badge/Active-green) |
| **⚡ Celery Worker** | Python + Redis | Async Task Processing | - | ![Status](https://img.shields.io/badge/Active-green) |
| **📅 Celery Beat** | Python + Redis | Scheduled Tasks | - | ![Status](https://img.shields.io/badge/Active-green) |
| **🐘 PostgreSQL** | PostgreSQL 15 | Primary Database | 5432 | ![Status](https://img.shields.io/badge/Active-green) |
| **📦 Redis** | Redis 7 | Message Broker & Cache | 6379 | ![Status](https://img.shields.io/badge/Active-green) |

---

## 🎬 How It Works

<div align="center">

```mermaid
graph LR
    A[📹 Camera Feed] --> B[🤖 AI Detection]
    B --> C[👤 Face Recognition]
    C --> D[💬 Greeting Generation]
    C --> E[🏠 Home Automation]
    C --> F[🙏 Devotional Music]
    D --> G[📱 Smart Display]
    E --> H[💡 Lights & Music]
    F --> I[🎵 Daily Worship Playlists]
    C --> J[📊 Event Logging]
    J --> K[📈 Analytics Dashboard]
```

</div>

### 🔄 **Processing Pipeline**

1. **📹 Video Capture**: Continuous monitoring of configured camera feeds
2. **🎯 Person Detection**: YOLOv8 identifies human subjects with configurable confidence
3. **👤 Face Recognition**: InsightFace generates 512-dimensional embeddings
4. **🔍 Identity Resolution**: Cosine similarity matching against stored profiles
5. **💬 Greeting Generation**: AI-powered personalized messages with weather context
6. **🏠 Automation Triggers**: Smart device control via Home Assistant webhooks
7. **🙏 Devotional Scheduling**: Hindu calendar-based spiritual music automation
8. **📊 Event Logging**: Comprehensive activity tracking and analytics

---

## 🎵 Enhanced Music Automation System

### 🙏 **Devotional Music Schedule**

KinAI Vision includes an intelligent **Hindu devotional music system** that automatically plays appropriate spiritual content based on:
- **Daily Deity Worship Calendar** (Monday-Sunday cycle)
- **Hindu Festival Calendar** (2025 South Indian festivals)
- **Family Presence Detection** (only triggers when someone is home)
- **Time-of-Day Awareness** (morning prayers, evening aarti, etc.)

---

### 🗓️ **Weekly Deity Worship Schedule**

<table>
<tr>
<th>Day</th>
<th>Deity Worshipped (English)</th>
<th>தேவதை (Tamil)</th>
<th>🎵 Playlist Theme Suggestion</th>
<th>⏰ Default Time</th>
</tr>
<tr>
<td><strong>Monday</strong></td>
<td>Lord Shiva</td>
<td>சிவபெருமான்</td>
<td>Shiva Bhajans (Om Namah Shivaya, Lingashtakam)</td>
<td>6:00 AM, 7:00 PM</td>
</tr>
<tr>
<td><strong>Tuesday</strong></td>
<td>Lord Murugan / Hanuman</td>
<td>முருகன் / ஹனுமான்</td>
<td>Murugan Padalgal, Hanuman Chalisa</td>
<td>6:00 AM, 7:00 PM</td>
</tr>
<tr>
<td><strong>Wednesday</strong></td>
<td>Lord Venkateswara / Krishna</td>
<td>வெங்கடேஸ்வரர் / கிருஷ்ணர்</td>
<td>Vishnu Sahasranamam, Krishna Bhajans</td>
<td>6:00 AM, 7:00 PM</td>
</tr>
<tr>
<td><strong>Thursday</strong></td>
<td>Guru (Brihaspati) / Dattatreya</td>
<td>குரு பகவான் / தத்தாத்திரேயர்</td>
<td>Guru Stotram, Dattatreya Bhajans</td>
<td>6:00 AM, 7:00 PM</td>
</tr>
<tr>
<td><strong>Friday</strong></td>
<td>Goddess Lakshmi / Durga</td>
<td>மகாலட்சுமி / துர்கை</td>
<td>Lakshmi Aarti, Kanakadhara Stotram, Devi Bhajans</td>
<td>6:00 AM, 7:00 PM</td>
</tr>
<tr>
<td><strong>Saturday</strong></td>
<td>Lord Shani / Narasimha</td>
<td>சனீஸ்வரர் / நரசிம்மர்</td>
<td>Shani Dev Songs, Narasimha Kavacham</td>
<td>6:00 AM, 7:00 PM</td>
</tr>
<tr>
<td><strong>Sunday</strong></td>
<td>Lord Surya (Sun God)</td>
<td>சூரிய பகவான்</td>
<td>Aditya Hridayam, Surya Gayatri Mantra</td>
<td>6:00 AM, 7:00 PM</td>
</tr>
</table>

---

### 🗓️ **South Indian Hindu Festivals (January – March 2025)**

<table>
<tr>
<th>📅 Date</th>
<th>Festival (English)</th>
<th>பண்டிகை (Tamil)</th>
<th>🎵 Playlist Theme Suggestion</th>
<th>🔔 Auto-Trigger</th>
</tr>
<tr>
<td><strong>January 10</strong></td>
<td>Vaikuntha Ekadashi</td>
<td>வைகுண்ட ஏகாதசி</td>
<td>Vishnu Sahasranamam, Govinda Namavali</td>
<td>5:30 AM - 8:00 AM</td>
</tr>
<tr>
<td><strong>January 13</strong></td>
<td>Bhogi</td>
<td>போகிப் பண்டிகை</td>
<td>Traditional Bhogi songs</td>
<td>All Day (when home)</td>
</tr>
<tr>
<td><strong>January 14</strong></td>
<td>Thai Pongal</td>
<td>தைப்பொங்கல்</td>
<td>Pongal celebration songs</td>
<td>All Day (when home)</td>
</tr>
<tr>
<td><strong>January 15</strong></td>
<td>Maattu Pongal</td>
<td>மாட்டுப் பொங்கல்</td>
<td>Folk songs honoring cattle</td>
<td>6:00 AM - 10:00 AM</td>
</tr>
<tr>
<td><strong>January 15</strong></td>
<td>Thiruvalluvar Day</td>
<td>திருவள்ளுவர் தினம்</td>
<td>Songs on Thirukkural and Thiruvalluvar</td>
<td>Morning Hours</td>
</tr>
<tr>
<td><strong>January 16</strong></td>
<td>Kaanum Pongal</td>
<td>காணும் பொங்கல்</td>
<td>Family and reunion songs</td>
<td>All Day (when home)</td>
</tr>
<tr>
<td><strong>January 16</strong></td>
<td>Uzhavar Thirunal</td>
<td>உழவர் திருநாள்</td>
<td>Songs celebrating farmers</td>
<td>Morning Hours</td>
</tr>
<tr>
<td><strong>January 29</strong></td>
<td>Thai Amavasai</td>
<td>தை அமாவாசை</td>
<td>Amavasya prayers and meditative chants</td>
<td>5:00 AM - 7:00 AM</td>
</tr>
<tr>
<td><strong>February 4</strong></td>
<td>Ratha Saptami</td>
<td>ரத சப்தமி</td>
<td>Surya Namaskar chants</td>
<td>Sunrise (6:30 AM)</td>
</tr>
<tr>
<td><strong>February 11</strong></td>
<td>Thai Poosam</td>
<td>தைப்பூசம்</td>
<td>Murugan devotional songs</td>
<td>4:00 AM - 8:00 AM</td>
</tr>
<tr>
<td><strong>February 26</strong></td>
<td>Maha Shivaratri</td>
<td>மஹா சிவராத்திரி</td>
<td>Shiva bhajans and Rudram chants</td>
<td>All Night (6:00 PM - 6:00 AM)</td>
</tr>
<tr>
<td><strong>March 12</strong></td>
<td>Masi Magam</td>
<td>மாசி மகம்</td>
<td>Temple procession songs</td>
<td>5:00 AM - 9:00 AM</td>
</tr>
<tr>
<td><strong>March 13</strong></td>
<td>Holi</td>
<td>ஹோலி</td>
<td>Holi festival songs</td>
<td>All Day (when home)</td>
</tr>
<tr>
<td><strong>March 14</strong></td>
<td>Karadaiyan Nombu</td>
<td>காரடையான் நோன்பு</td>
<td>Devotional songs for Savitri</td>
<td>4:30 AM - 7:00 AM</td>
</tr>
<tr>
<td><strong>March 30</strong></td>
<td>Ugadi (Telugu New Year)</td>
<td>உகாதி</td>
<td>Telugu New Year songs</td>
<td>Morning Hours</td>
</tr>
</table>

---

### 🎵 **Smart Devotional Music Logic**

#### 🏠 **Presence-Based Activation**
```python
async def trigger_devotional_music(detected_persons: List[str], current_time: datetime):
    """
    Intelligent devotional music activation based on:
    - Someone being home (face detection required)
    - Current day of week (deity-specific)
    - Special festival dates
    - Time of day (morning/evening prayers)
    """
    
    if not detected_persons:
        return  # No music if no one is home
    
    day_of_week = current_time.strftime('%A').lower()
    current_date = current_time.date()
    current_hour = current_time.hour
    
    # Check if it's a festival date
    festival_playlist = get_festival_playlist(current_date)
    if festival_playlist:
        await play_festival_music(festival_playlist, detected_persons)
        return
    
    # Regular daily deity worship
    deity_playlist = get_daily_deity_playlist(day_of_week, current_hour)
    
    # Personalize based on family member preferences
    if "Ila" in detected_persons:
        deity_playlist = customize_for_family_member(deity_playlist, "Ila")
    
    await play_devotional_music(deity_playlist, volume=0.3)

def get_daily_deity_playlist(day: str, hour: int) -> str:
    """Returns appropriate playlist based on day and time"""
    deity_map = {
        'monday': 'shiva_bhajans',
        'tuesday': 'murugan_hanuman_songs', 
        'wednesday': 'vishnu_krishna_bhajans',
        'thursday': 'guru_dattatreya_stotrams',
        'friday': 'lakshmi_devi_bhajans',
        'saturday': 'shani_narasimha_songs',
        'sunday': 'surya_mantras'
    }
    
    base_playlist = deity_map.get(day, 'general_devotional')
    
    # Morning prayers (5:30 AM - 8:00 AM)
    if 5 <= hour <= 8:
        return f"{base_playlist}_morning"
    # Evening aarti (6:00 PM - 8:00 PM)  
    elif 18 <= hour <= 20:
        return f"{base_playlist}_evening"
    else:
        return base_playlist

def get_festival_playlist(date: datetime.date) -> Optional[str]:
    """Returns special festival playlist if date matches"""
    festival_calendar = {
        datetime.date(2025, 1, 10): "vaikuntha_ekadashi",
        datetime.date(2025, 1, 14): "thai_pongal_celebrations",
        datetime.date(2025, 2, 11): "thai_poosam_murugan",
        datetime.date(2025, 2, 26): "maha_shivaratri_night",
        datetime.date(2025, 3, 13): "holi_celebrations",
        # Add more festivals...
    }
    
    return festival_calendar.get(date)
```

#### 📊 **Enhanced Database Schema for Devotional Music**

```sql
-- Devotional music scheduling table
CREATE TABLE devotional_schedule (
    id SERIAL PRIMARY KEY,
    day_of_week INTEGER,              -- 0=Monday, 6=Sunday
    deity_name VARCHAR(100),          -- Tamil and English deity names
    playlist_id VARCHAR(100),         -- Jellyfin playlist identifier
    start_time TIME,                  -- Morning prayer time
    end_time TIME,                    -- Evening prayer time
    is_active BOOLEAN DEFAULT TRUE,
    volume_level FLOAT DEFAULT 0.3,   -- Default volume for devotional music
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Festival-specific music calendar
CREATE TABLE festival_calendar (
    id SERIAL PRIMARY KEY,
    festival_date DATE,               -- Specific festival date
    festival_name_en VARCHAR(200),    -- English festival name
    festival_name_ta VARCHAR(200),    -- Tamil festival name  
    playlist_id VARCHAR(100),         -- Special festival playlist
    start_time TIME,                  -- Festival music start time
    end_time TIME,                    -- Festival music end time
    auto_trigger BOOLEAN DEFAULT TRUE, -- Whether to auto-play
    all_day BOOLEAN DEFAULT FALSE,    -- All-day festival music
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Family devotional preferences
CREATE TABLE devotional_preferences (
    id SERIAL PRIMARY KEY,
    person_name VARCHAR(100),         -- Family member name
    preferred_deity VARCHAR(100),     -- Favorite deity
    preferred_playlist VARCHAR(100),  -- Personal devotional playlist
    morning_volume FLOAT DEFAULT 0.2, -- Preferred morning volume
    evening_volume FLOAT DEFAULT 0.4, -- Preferred evening volume
    enable_auto_play BOOLEAN DEFAULT TRUE,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

#### 🔔 **Smart Notification Integration**

```python
async def send_devotional_notification(event_type: str, details: dict):
    """Send devotional music notifications"""
    
    notifications = {
        "daily_deity": f"🙏 {details['deity_name']} devotional music started - {details['playlist_name']}",
        "festival_music": f"🎉 {details['festival_name']} celebration music playing automatically",
        "morning_prayer": f"🌅 Morning prayer time - {details['deity_name']} bhajans started",
        "evening_aarti": f"🪔 Evening aarti time - {details['deity_name']} songs playing",
        "shivaratri_night": f"🌙 Maha Shivaratri - All-night Shiva bhajans activated"
    }
    
    message = notifications.get(event_type, f"🎵 Devotional music update: {details}")
    
    # Send to family members via Telegram
    await send_telegram_message({
        "chat_id": FAMILY_CHAT_ID,
        "text": message,
        "parse_mode": "HTML"
    })
```

---

## 🚀 Quick Start Guide

### 📋 **Prerequisites**

<table>
<tr>
<td width="50%">

#### 🖥️ **System Requirements**
- 🐳 Docker & Docker Compose
- 🎮 NVIDIA GPU (CUDA 11.8+)
- 💾 10GB+ disk space
- 🌐 Internet connection
- 🎥 USB/IP camera

</td>
<td width="50%">

#### 🔑 **API Keys Needed**
- 🌤️ OpenWeatherMap API key
- 🏠 Home Assistant access (optional)
- 📱 Telegram Bot token (optional)
- 🎵 Jellyfin server (optional)

</td>
</tr>
</table>

### 🛠️ **Installation Steps**

#### 1️⃣ **Clone Repository**
```bash
git clone https://github.com/yourusername/KinAI-Vision.git
cd KinAI-Vision
```

#### 2️⃣ **Environment Configuration**
```bash
# Create environment file
touch .env
```

```env
# Database Configuration
DATABASE_URL=postgresql://user:password@172.17.0.1:5432/kinai
SQLALCHEMY_POOL_SIZE=20
SQLALCHEMY_MAX_OVERFLOW=30

# Celery Configuration
CELERY_BROKER_URL=redis://172.17.0.1:6379/0
CELERY_RESULT_BACKEND=redis://172.17.0.1:6379/0
CELERY_TASK_SERIALIZER=json

# AI Model Configuration
OLLAMA_BASE_URL=http://host.docker.internal:11434
OLLAMA_MODEL=granite3.2:latest
OPENWEATHERMAP_API_KEY=your_openweathermap_api_key

# Webhook Configuration
WEBHOOK_URL=http://your_webhook_endpoint

# CUDA Configuration
CUDA_VISIBLE_DEVICES=0
TORCH_CUDA_ARCH_LIST="7.5;8.0;8.6"
```

#### 3️⃣ **Model Setup**
```bash
# Download YOLOv8 model
mkdir -p models
wget -O models/yolov8n.pt https://github.com/ultralytics/assets/releases/download/v0.0.0/yolov8n.pt

# Setup InsightFace (buffalo_l directory should exist in models/)
mkdir -p models/buffalo_l
```

#### 4️⃣ **Configuration File**
```bash
# Edit configs/config.ini
nano configs/config.ini
```

```ini
[Paths]
FOOTAGE_DIR = /app/footage
MODELS_DIR = /app/models
DETECTED_FACES_DIR = /app/detected_faces

[Settings]
THRESHOLD = 0.6                    # Facial recognition threshold
MIN_CONFIDENCE = 0.5               # YOLOv8 detection confidence
COOLDOWN_PERIOD = 30               # Seconds between identical detections
DETECTION_SIZE = 320               # Input size for face detection

[Cameras]
CAMERA_0 = /dev/video4             # USB Camera device
CAMERA_1 = rtsp://192.168.1.100    # IP Camera stream

[Webhooks]
SINGLE_KNOWN = http://fastapi:8000/webhook/single_known
FAMILY_PROFILE = http://fastapi:8000/webhook/family_profile
UNKNOWN_WITH_KNOWN = http://fastapi:8000/webhook/unknown_with_known
TRACK_SUSPECT = http://fastapi:8000/webhook/track_suspect
NO_DETECTION = http://fastapi:8000/webhook/no_detection

[Logging]
LOG_DIR = /app/logs
LOG_LEVEL = DEBUG

[ModelSettings]
YOLO_CONFIDENCE = 0.5              # Person detection threshold
YOLO_IOU = 0.45                    # Non-maximum suppression IOU
FACE_CONFIDENCE = 0.6              # Face detection threshold

[DevotionalMusic]
ENABLE_DEVOTIONAL = true           # Enable devotional music automation
MORNING_START_TIME = 06:00         # Daily morning prayer time
EVENING_START_TIME = 19:00         # Daily evening prayer time
DEFAULT_VOLUME = 0.3               # Default devotional music volume
FESTIVAL_VOLUME = 0.5              # Special festival music volume
AUTO_STOP_EMPTY_HOME = true        # Stop music when no one is home
```

#### 5️⃣ **Launch System**
```bash
# Build and start all services
docker-compose up --build -d

# Verify containers are running
docker ps
```

#### 6️⃣ **Initialize Database**
```bash
# Database initialization (runs automatically)
docker exec -it kinai-vision_postgres psql -U user -d kinai -c "\dt"
```

#### 7️⃣ **Train Face Recognition**
```bash
# Add training footage to footage/ directory
cp /path/to/family/videos/*.mp4 footage/

# Train facial embeddings
docker-compose exec kinwatch python3 /app/src/train_faces.py
```

#### 8️⃣ **Setup Devotional Playlists**
```bash
# Configure Jellyfin devotional playlists
curl -X POST http://localhost:8000/devotional/setup \
  -H "Content-Type: application/json" \
  -d '{
    "jellyfin_server": "http://192.168.1.100:8096",
    "api_key": "your_jellyfin_api_key",
    "playlists": {
      "shiva_bhajans_morning": "playlist_id_1",
      "murugan_padalgal_evening": "playlist_id_2",
      "thai_pongal_celebrations": "playlist_id_3"
    }
  }'
```

#### 9️⃣ **Verify System**
```bash
# Check API health
curl http://localhost:8000/health

# Monitor system logs
docker-compose logs --tail=50 kinwatch

# View detected faces
ls detected_faces/camera_0/$(date +%Y%m%d)/

# Test devotional music
curl -X POST http://localhost:8000/devotional/test \
  -H "Content-Type: application/json" \
  -d '{"person_name": "Ila", "test_deity": "Murugan"}'
```

---

## 🗂️ Project Structure

```
KinAI-Vision/
├── 📁 src/                          # 🧠 Core Application Code
│   ├── 🚀 main.py                   # FastAPI application entry point
│   ├── 🔄 celery_config.py          # Celery worker configuration
│   ├── ⚡ tasks.py                  # Asynchronous task definitions
│   ├── 🗄️ models.py                # SQLAlchemy ORM data models
│   ├── 👁️ kinwatch_agent.py        # Video processing surveillance service
│   ├── 📡 surveillance_agent.py     # Webhook trigger service
│   ├── 🔗 chains.py                 # LangChain implementation
│   ├── 🤖 agents.py                 # CrewAI agent definitions
│   ├── 👥 family_profiles.py        # Family group detection logic
│   ├── 🕵️ visitor_tracker.py        # Unknown visitor handling
│   └── 🎓 train_faces.py            # Facial embedding training script
├── 📁 configs/                      # ⚙️ Configuration Files
│   └── ⚙️ config.ini               # Main application configuration
├── 📁 models/                       # 🧠 AI Model Files
│   ├── 🎯 yolov8n.pt               # YOLOv8 person detection model
│   └── 📁 buffalo_l/               # InsightFace model directory
├── 📁 footage/                      # 🎬 Training Video Data
├── 📁 detected_faces/               # 📸 Detection Image Archive
│   └── 📁 camera_X/YYYYMMDD/       # Organized by camera/date
├── 📁 logs/                         # 📝 Application Log Files
├── 📁 docker/                       # 🐳 Docker Configuration
│   └── 📋 requirements.txt         # Surveillance service dependencies
├── 🐳 Dockerfile                    # Container image definition
├── 🐙 docker-compose.yml           # Multi-service orchestration
├── 🗄️ init_db.sql                  # PostgreSQL database initialization
├── 🌍 .env                         # Environment variables
├── 📋 requirements.txt              # Main Python dependencies
└── 📖 README.md                    # This comprehensive documentation
```

---

## 🧠 AI/ML Components Deep Dive

### 🎯 **Computer Vision Pipeline**

<div align="center">

```mermaid
graph TD
    A[📹 Video Frame] --> B[🔄 Preprocessing]
    B --> C[🎯 YOLOv8 Detection]
    C --> D{👤 Person Found?}
    D -->|No| E[📝 Log No Detection]
    D -->|Yes| F[✂️ Face Extraction]
    F --> G[👤 InsightFace Processing]
    G --> H[🧮 512-D Embedding]
    H --> I[📊 Similarity Matching]
    I --> J{🔍 Match Found?}
    J -->|Yes| K[✅ Known Person]
    J -->|No| L[❓ Unknown Visitor]
    K --> M[📡 Webhook Trigger]
    L --> N[🆔 ULID Assignment]
    N --> M
```

</div>

#### 🔧 **YOLOv8 Configuration**
```python
# Person detection with optimized parameters
model = YOLO('yolov8n.pt')
results = model(
    frame, 
    conf=0.5,           # Confidence threshold
    classes=[0],        # Person class only
    device='cuda:0'     # GPU acceleration
)
```

#### 👤 **InsightFace Integration**
```python
# High-accuracy facial recognition
app = FaceAnalysis(
    name='buffalo_l',
    providers=['CUDAExecutionProvider', 'CPUExecutionProvider']
)
faces = app.get(cv2_image)
embedding = faces[0].embedding  # 512-dimensional feature vector
```

### 🤖 **Natural Language Processing**

#### 🔗 **LangChain + CrewAI Workflow**
```python
# Intelligent greeting generation
weather_agent = Agent(
    role='Weather Specialist',
    goal='Provide contextual weather information',
    llm=Ollama(model="granite3.2:latest"),
    backstory="Expert in weather data interpretation"
)

greeting_task = Task(
    description="Generate personalized greeting with weather context",
    agent=weather_agent,
    expected_output="Warm, personalized welcome message"
)

crew = Crew(agents=[weather_agent], tasks=[greeting_task])
result = crew.kickoff()
```

---

## 💾 Database Architecture

### 🗄️ **PostgreSQL Schema Design**

<div align="center">

```mermaid
erDiagram
    EVENT_LOG {
        int id PK
        varchar event_type
        jsonb payload
        timestamp created_at
    }
    
    FACES {
        int id PK
        varchar person_name
        bytea embedding
        timestamp created_at
    }
    
    UNKNOWN_VISITORS {
        int id PK
        varchar visitor_ulid UK
        bytea embedding
        timestamp first_seen
        timestamp last_seen
        int detection_count
    }
    
    FAMILY_PROFILES {
        int id PK
        varchar profile_name
        jsonb member_names
        timestamp created_at
    }
    
    MUSIC_SCHEDULE {
        int id PK
        varchar playlist_id
        time start_time
        time end_time
        varchar required_person
    }
    
    EVENT_LOG ||--o{ FACES : references
    UNKNOWN_VISITORS ||--o{ EVENT_LOG : tracks
    FAMILY_PROFILES ||--o{ EVENT_LOG : groups
```

</div>

#### 📊 **Core Tables**

<table>
<tr>
<td width="50%">

**📝 Event Logging**
```sql
CREATE TABLE event_log (
    id SERIAL PRIMARY KEY,
    event_type VARCHAR(50) NOT NULL,
    payload JSONB,
    camera_id INTEGER,
    timestamp TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    processed BOOLEAN DEFAULT FALSE
);

-- Indexes for performance
CREATE INDEX idx_event_log_timestamp ON event_log(timestamp);
CREATE INDEX idx_event_log_type ON event_log(event_type);
CREATE INDEX idx_event_log_payload ON event_log USING GIN(payload);
```

</td>
<td width="50%">

**👤 Facial Recognition**
```sql
CREATE TABLE faces (
    id SERIAL PRIMARY KEY,
    person_name VARCHAR(100) NOT NULL,
    embedding BYTEA NOT NULL,
    confidence FLOAT DEFAULT 1.0,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Efficient similarity search preparation
CREATE INDEX idx_faces_person ON faces(person_name);
CREATE INDEX idx_faces_created ON faces(created_at);
```

</td>
</tr>
<tr>
<td width="50%">

**🕵️ Visitor Tracking**
```sql
CREATE TABLE unknown_visitors (
    id SERIAL PRIMARY KEY,
    visitor_ulid VARCHAR(26) UNIQUE NOT NULL,
    embedding BYTEA NOT NULL,
    first_seen TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    last_seen TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    detection_count INTEGER DEFAULT 1,
    is_flagged BOOLEAN DEFAULT FALSE
);
```

</td>
<td width="50%">

**🎵 Music Automation**
```sql
CREATE TABLE music_schedule (
    id SERIAL PRIMARY KEY,
    playlist_id VARCHAR(100) NOT NULL,
    start_time TIME NOT NULL,
    end_time TIME NOT NULL,
    required_person VARCHAR(100),
    is_active BOOLEAN DEFAULT TRUE,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

</td>
</tr>
</table>

---

## 🔗 API Documentation

### 🚀 **FastAPI Endpoints**

#### 📡 **Webhook Endpoints**

<table>
<tr>
<th>Endpoint</th>
<th>Method</th>
<th>Description</th>
<th>Payload</th>
</tr>
<tr>
<td><code>/webhook/single_known</code></td>
<td>🟢 POST</td>
<td>Single known person detected</td>
<td><code>SingleKnownRequest</code></td>
</tr>
<tr>
<td><code>/webhook/family_profile</code></td>
<td>🟢 POST</td>
<td>Family group detection</td>
<td><code>FamilyProfileRequest</code></td>
</tr>
<tr>
<td><code>/webhook/unknown_with_known</code></td>
<td>🟢 POST</td>
<td>Unknown person with known family</td>
<td><code>MixedDetectionRequest</code></td>
</tr>
<tr>
<td><code>/webhook/track_suspect</code></td>
<td>🟢 POST</td>
<td>New unknown visitor tracking</td>
<td><code>SuspectRequest</code></td>
</tr>
<tr>
<td><code>/webhook/no_detection</code></td>
<td>🟢 POST</td>
<td>No persons detected event</td>
<td><code>NoDetectionRequest</code></td>
</tr>
</table>

#### 🛠️ **Management Endpoints**

<table>
<tr>
<th>Endpoint</th>
<th>Method</th>
<th>Description</th>
<th>Response</th>
</tr>
<tr>
<td><code>/health</code></td>
<td>🔵 GET</td>
<td>Basic system health check</td>
<td><code>{"status": "healthy"}</code></td>
</tr>
<tr>
<td><code>/health/detailed</code></td>
<td>🔵 GET</td>
<td>Detailed component status</td>
<td>Component-wise health report</td>
</tr>
<tr>
<td><code>/metrics</code></td>
<td>🔵 GET</td>
<td>Prometheus metrics endpoint</td>
<td>Performance metrics</td>
</tr>
<tr>
<td><code>/faces/train</code></td>
<td>🟢 POST</td>
<td>Trigger face model training</td>
<td>Training status</td>
</tr>
<tr>
<td><code>/config/reload</code></td>
<td>🟢 POST</td>
<td>Reload system configuration</td>
<td>Reload confirmation</td>
</tr>
</table>

#### 📋 **Request/Response Schemas**

```python
# Base detection event model
class DetectionEvent(BaseModel):
    camera_id: int
    timestamp: datetime
    confidence: float
    bounding_box: List[float]
    face_image: str  # Base64 encoded image
    
# Known person detection
class KnownPersonEvent(DetectionEvent):
    person_name: str
    recognition_confidence: float
    greeting_message: Optional[str]
    
# Unknown visitor detection
class UnknownVisitorEvent(DetectionEvent):
    visitor_ulid: str
    is_recurring: bool = False
    threat_level: str = "low"
    
# Family profile detection
class FamilyProfileEvent(DetectionEvent):
    profile_name: str
    detected_members: List[str]
    group_confidence: float
```

---

## 📱 Smart Home Integrations

### 🏠 **Home Assistant Integration**

```yaml
# configuration.yaml
automation:
  - alias: "KinAI Welcome Home"
    trigger:
      platform: webhook
      webhook_id: kinai_person_detected
    action:
      - service: light.turn_on
        target:
          entity_id: light.living_room
      - service: climate.set_temperature
        target:
          entity_id: climate.main_ac
        data:
          temperature: 22
      - service: notify.mobile_app
        data:
          message: "{{ trigger.json.greeting_message }}"
```

### 🎵 **Jellyfin Music Control**

```python
# Automated playlist management
async def trigger_music_playbook(person_name: str, time_of_day: str):
    playlist_mapping = {
        "morning": "energetic_morning_playlist",
        "evening": "relaxing_evening_playlist",
        "Ila": "ila_favorite_playlist",
        "family": "family_friendly_playlist"
    }
    
    playlist_id = playlist_mapping.get(person_name, playlist_mapping.get(time_of_day))
    
    jellyfin_webhook = {
        "action": "play_playlist",
        "playlist_id": playlist_id,
        "shuffle": True,
        "volume": 0.7
    }
    
    await send_jellyfin_command(jellyfin_webhook)
```

### 📱 **Telegram Notifications**

```python
# Smart notification system
async def send_telegram_alert(event_type: str, details: dict):
    messages = {
        "unknown_visitor": f"🚨 Unknown visitor detected at {details['timestamp']}",
        "family_arrived": f"🏠 {details['person_name']} arrived home",
        "security_alert": f"⚠️ Security event: {details['description']}"
    }
    
    message = messages.get(event_type, "📊 KinAI system update")
    
    telegram_payload = {
        "chat_id": TELEGRAM_CHAT_ID,
        "text": message,
        "parse_mode": "HTML"
    }
    
    if details.get('image'):
        # Send photo with caption
        telegram_payload["photo"] = details['image']
```

---

## ⚙️ Configuration Management

### 📋 **config.ini Complete Reference**

```ini
[Paths]
FOOTAGE_DIR = /app/footage                    # Training video directory
MODELS_DIR = /app/models                      # AI model storage
DETECTED_FACES_DIR = /app/detected_faces      # Detection image archive
LOG_DIR = /app/logs                           # System logs directory

[Settings]
THRESHOLD = 0.6                               # Facial recognition similarity threshold
MIN_CONFIDENCE = 0.5                          # Minimum detection confidence
COOLDOWN_PERIOD = 30                          # Seconds between duplicate detections
DETECTION_SIZE = 320                          # Face detection input resolution
MAX_FACES_PER_FRAME = 10                      # Maximum faces to process per frame
FRAME_SKIP = 1                                # Process every N frames (performance)

[Cameras]
CAMERA_0 = /dev/video4                        # Primary USB camera
CAMERA_1 = rtsp://192.168.1.100:554/stream   # IP camera RTSP stream
CAMERA_2 = http://192.168.1.101/mjpeg         # HTTP MJPEG stream
ENABLE_CAMERA_0 = true                        # Enable/disable specific cameras
ENABLE_CAMERA_1 = true
ENABLE_CAMERA_2 = false

[Webhooks]
SINGLE_KNOWN = http://fastapi:8000/webhook/single_known
FAMILY_PROFILE = HTTP://fastapi:8000/webhook/family_profile
UNKNOWN_WITH_KNOWN = http://fastapi:8000/webhook/unknown_with_known
TRACK_SUSPECT = http://fastapi:8000/webhook/track_suspect
NO_DETECTION = http://fastapi:8000/webhook/no_detection
TIMEOUT = 10                                  # Webhook timeout in seconds
RETRY_ATTEMPTS = 3                            # Failed webhook retry count

[Logging]
LOG_DIR = /app/logs                           # Log file directory
LOG_LEVEL = DEBUG                             # DEBUG, INFO, WARNING, ERROR
MAX_LOG_SIZE = 100MB                          # Maximum individual log file size
LOG_RETENTION_DAYS = 30                       # Days to keep old logs
ENABLE_CONSOLE_LOGGING = true                 # Console output for debugging

[ModelSettings]
YOLO_CONFIDENCE = 0.5                         # YOLOv8 person detection threshold
YOLO_IOU = 0.45                              # Non-maximum suppression threshold
FACE_CONFIDENCE = 0.6                         # InsightFace detection threshold
EMBEDDING_DIMENSION = 512                     # Facial embedding dimensions
SIMILARITY_METRIC = cosine                    # cosine, euclidean, manhattan
GPU_MEMORY_FRACTION = 0.8                     # GPU memory allocation limit

[Automation]
ENABLE_LIGHTS = true                          # Smart lighting control
ENABLE_MUSIC = true                           # Automated music playback
ENABLE_CLIMATE = true                         # Climate control automation
ENABLE_NOTIFICATIONS = true                   # Push notifications
SUNSET_OFFSET_MINUTES = -30                   # Trigger automation before/after sunset
MAX_AUTOMATION_FREQUENCY = 300                # Seconds between automation triggers

[Security]
UNKNOWN_VISITOR_ALERT = true                  # Alert on unknown visitors
SUSPICIOUS_ACTIVITY_THRESHOLD = 5             # Multiple unknowns threshold
VISITOR_TRACKING_DAYS = 30                    # Days to track unknown visitors
ENABLE_PHOTO_ARCHIVE = true                   # Save detection photos
PHOTO_RETENTION_DAYS = 90                     # Days to keep detection photos
```

### 🌍 **Environment Variables Reference**

```bash
# Database Configuration
DATABASE_URL=postgresql://kinai_user:secure_password@172.17.0.1:5432/kinai
SQLALCHEMY_POOL_SIZE=20                       # Connection pool size
SQLALCHEMY_MAX_OVERFLOW=30                    # Additional connections beyond pool
SQLALCHEMY_POOL_TIMEOUT=30
