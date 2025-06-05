# 🧬 KinAI-CareVault

> *Your Family's AI-Powered Health & Financial Guardian* 🛡️

[![GitHub Repo](https://img.shields.io/badge/GitHub-KinAI--CareVault-blue?logo=github)](https://github.com/Logulokesh/KinAI-CareVault)
[![Docker](https://img.shields.io/badge/Docker-Compose-2496ED?logo=docker)](https://docs.docker.com/compose/)
[![Telegram](https://img.shields.io/badge/Telegram-Bot-26A5E4?logo=telegram)](https://core.telegram.org/bots)

---

## 🌟 What is KinAI-CareVault?

KinAI-CareVault is an **intelligent family health & finance management system** that transforms how you handle medical documents, prescriptions, and financial records. Simply snap a photo via Telegram, and watch AI magic happen! 📸✨

### 🎯 Core Philosophy
- 🏠 **Family-First**: Centralized profiles for every family member
- 🤖 **AI-Driven**: Smart document classification and medical recommendations  
- 🔒 **Privacy-Focused**: Your data stays in your control
- 📱 **Telegram-Native**: No apps to download, just chat naturally

---

## ⚡ Key Features

### 📄 **Smart Document Processing**
> *Upload once, organize forever*

🔍 **Auto-Classification**: Receipts, prescriptions, lab reports - AI knows the difference  
💾 **Structured Storage**: PostgreSQL database with medical + financial separation  
📋 **Task Creation**: Auto-generates Vikunja tasks with attached images  
✅ **Instant Confirmation**: Telegram notifications with extracted details  

### 👨‍👩‍👧‍👦 **Family Health Profiles**
> *Complete medical history at your fingertips*

🏥 **Medical Conditions**: Track ongoing health issues per family member  
💊 **Current Medications**: Prescription management with dosage tracking  
🚨 **Allergy Management**: Safety-first medication recommendations  
📊 **Health Analytics**: Query patterns and medical summaries  

### 🧠 **AI-Powered Medication Assistant**
> *Safe recommendations, always*

🔬 **Smart Analysis**: Considers allergies, conditions, and current meds  
⚕️ **Dosage Guidance**: Age-appropriate recommendations with precautions  
🚑 **Emergency Protocols**: When to seek immediate medical attention  
👨‍⚕️ **Doctor Consultation**: Clear advice on when professional help is needed  

### 💰 **Financial Document Tracking**
> *Every receipt, every expense, organized*

🛒 **Vendor Recognition**: Auto-extracts store names and amounts  
📈 **Spending Analytics**: Built-in SQL queries for financial insights  
🗂️ **Category Management**: Smart tagging for groceries, medical, utilities  
💳 **Receipt Archive**: Never lose another important document  

---

## 🚀 Installation Guide (with Docker Compose)

### 1️⃣ Clone Repository
```bash
git clone https://github.com/Logulokesh/KinAI-CareVault.git
cd KinAI-CareVault
```

### 2️⃣ Prepare Document Schema
Ensure your schema file (`document_processing_schema.txt`) is present in the project root. This file will be applied automatically to PostgreSQL during container startup.

### 3️⃣ Start the System with Docker Compose
```bash
docker-compose up -d
```

This will launch:
- 🗄️ **PostgreSQL** (with medical + financial schema)
- ⚙️ **n8n** (workflow automation)  
- 📝 **Vikunja API + Frontend** (task manager)

### 4️⃣ Access Services
- 🔧 **n8n Workflow Editor**: http://localhost:5678
  - Username: `admin`
  - Password: `adminpass`
- 📋 **Vikunja Frontend**: http://localhost:3456

### 5️⃣ Import Workflows into n8n
1. Log into n8n at http://localhost:5678
2. Import workflow files:
   - `medical_enhanced_n8n_workflow (2).json`
   - `fixed_n8n_workflow.json`
3. Configure environment credentials under each node:
   - 📱 **Telegram Bot API**
   - 🗄️ **PostgreSQL DB connection**
   - 📝 **Vikunja API URL & token**
   - 🧠 **Ollama AI endpoint** (if using)

### 6️⃣ Vikunja Setup
- Login and create projects corresponding to categories (as per `categoryProjectMap`)
- Set up user, labels, and tokens via Vikunja UI or API
- Use API token in your n8n workflow for authenticated task creation

### 7️⃣ Test Your Setup
- 📤 Send a test document to your Telegram bot
- 🔍 Check n8n execution logs
- ✅ Verify:
  - Data saved in PostgreSQL
  - Task created in Vikunja  
  - Telegram confirmation received

---

## 🏗️ System Architecture

### 🔄 **High-Level System Overview**
*Main flows and interactions between core components*

```mermaid
%%{init: {'theme':'base', 'themeVariables': { 'primaryColor': '#4f46e5', 'primaryTextColor': '#1f2937', 'primaryBorderColor': '#6366f1', 'lineColor': '#374151', 'secondaryColor': '#f3f4f6', 'tertiaryColor': '#e5e7eb', 'background': 'transparent', 'mainBkg': 'transparent', 'secondBkg': 'transparent', 'tertiaryBkg': 'transparent'}}}%%
graph TD
    subgraph Main["🏠 KinAI-CareVault System"]
        direction TB
        A["📱 Telegram Input<br/>📄 Documents or 💬 Queries"]
        
        subgraph DocFlow["📋 Document Processing Workflow"]
            direction TB
            B["📄 Document Processing"]
            D["🧠 AI Analysis<br/>🔍 Classify & Extract"]
            E["🗄️ PostgreSQL Storage<br/>📊 Medical/Financial"]
            F["📋 Vikunja Task<br/>🖼️ Attach Image"]
            G["✅ Telegram Confirmation"]
            
            B --> D
            D --> E
            D --> F
            E --> G
        end
        
        subgraph MedFlow["🏥 Medical Query Workflow"]
            direction TB
            C["👨‍⚕️ Medical Profile Query"]
            H["🔍 Database Query<br/>👥 Fetch Profile"]
            I["🧠 AI Recommendation<br/>💊 Safe Medication"]
            J["📱 Telegram Response"]
            
            C --> H
            H --> I
            I --> J
        end
        
        subgraph Services["🔧 Core Services"]
            direction LR
            K["🤖 Ollama AI<br/>🧠 LLM Engine"]
            L["🗄️ PostgreSQL<br/>📊 Database"]
            M["📋 Vikunja<br/>📝 Task Manager"]
        end
        
        A -->|📄 Document| DocFlow
        A -->|💬 Query| MedFlow
        
        D -.->|🤖 Analyze| K
        I -.->|🤖 Recommend| K
        E -.->|💾 Store| L
        H -.->|🔍 Query| L
        F -.->|📋 Create| M
    end
    
    classDef telegram fill:#26a5e4,stroke:#1da1f2,stroke-width:2px,color:#ffffff
    classDef ai fill:#ff6b6b,stroke:#e63946,stroke-width:2px,color:#ffffff
    classDef database fill:#4ecdc4,stroke:#26a69a,stroke-width:2px,color:#ffffff
    classDef task fill:#95e1d3,stroke:#48cae4,stroke-width:2px,color:#1f2937
    classDef workflow fill:#f9ca24,stroke:#f0932b,stroke-width:2px,color:#1f2937
    
    class A telegram
    class K ai
    class L database
    class M task
    class DocFlow,MedFlow workflow
```

### 🔧 **Detailed Workflow Architecture**
*Node-by-node flow of n8n workflows with error handling*

```mermaid
%%{init: {'theme':'base', 'themeVariables': { 'primaryColor': '#4f46e5', 'primaryTextColor': '#1f2937', 'primaryBorderColor': '#6366f1', 'lineColor': '#374151', 'secondaryColor': '#f3f4f6', 'tertiaryColor': '#e5e7eb', 'background': 'transparent', 'mainBkg': 'transparent', 'secondBkg': 'transparent', 'tertiaryBkg': 'transparent'}}}%%
graph TD
    subgraph Main["🏠 KinAI-CareVault Detailed Workflows"]
        direction TB
        
        subgraph DocWorkflow["📋 Document Processing Workflow"]
            direction TB
            A["📱 Telegram Trigger<br/>📥 Receive Document"]
            B["📥 File Handler<br/>⬇️ Download Image"]
            C["🔄 Base64 Converter<br/>🖼️ Image Processing"]
            D["🔍 AI Classifier<br/>📄 Document Type"]
            E["✅ Data Validator<br/>🔍 Process Results"]
            F{"❓ Medical Check<br/>🏥 Document Type?"}
            G["🏥 Medical AI<br/>📊 Extract Details"]
            H["📋 Medical Processor<br/>✅ Validate Data"]
            I["👥 Family Manager<br/>📝 Upsert Member"]
            J["🔍 DB Checker<br/>✅ Verify Connection"]
            K["💾 Medical Storage<br/>🗄️ Store Records"]
            M["📋 Task Creator<br/>📝 Vikunja Task"]
            N["📤 Image Uploader<br/>🖼️ Attach to Task"]
            O["💰 Financial Storage<br/>🧾 Store Receipt"]
            P["✅ Success Message<br/>📱 Telegram Confirm"]
            L["❌ Error Handler<br/>🚨 Send Notification"]
            
            A --> B --> C --> D --> E --> F
            F -->|🏥 Medical| G --> H --> I --> J
            F -->|💰 Financial| M
            J --> K --> M
            J -->|❌ Error| L
            K -->|❌ Error| L
            M --> N --> O --> P
            O -->|❌ Error| L
        end
        
        subgraph MedWorkflow["🏥 Medical Query Workflow"]
            direction TB
            S["📱 Query Trigger<br/>💬 Text Message"]
            T["👥 Profile Fetcher<br/>🔍 Get Family Data"]
            U["🔍 Query Processor<br/>📝 Extract Patient"]
            V{"❓ Patient Matcher<br/>👤 Profile Found?"}
            X["🏥 AI Recommender<br/>💊 Generate Advice"]
            Z["✅ Response Processor<br/>📋 Validate Output"]
            AA["📱 Advice Sender<br/>💬 Send Recommendation"]
            W["❌ Error Handler<br/>🚨 Send Notification"]
            Y["❓ No Match Handler<br/>👤 Patient Not Found"]
            
            S --> T --> U --> V
            T -->|❌ Error| W
            V -->|✅ Found| X --> Z --> AA
            V -->|❌ Not Found| Y
            X -->|❌ Error| W
        end
        
        subgraph AIModels["🤖 AI Model Services"]
            direction LR
            Q["🔍 Primary Classifier<br/>📄 Document AI"]
            R["🏥 Medical Analyzer<br/>💊 Health AI"]
            AB["💬 Recommendation AI<br/>🧠 Advisory Model"]
        end
        
        subgraph DataServices["🗄️ Data & Task Services"]
            direction LR
            AC["🤖 Ollama Engine<br/>🧠 AI Runtime"]
            AD["🗄️ PostgreSQL<br/>📊 Database"]
            AE["📋 Vikunja API<br/>📝 Task Manager"]
        end
        
        %% Connections to AI Models
        D -.->|🔍 Classify| Q
        G -.->|🏥 Analyze| R
        X -.->|💬 Recommend| AB
        
        %% Connections to Services
        Q -.->|🤖| AC
        R -.->|🤖| AC
        AB -.->|🤖| AC
        I -.->|💾| AD
        K -.->|💾| AD
        O -.->|💾| AD
        T -.->|🔍| AD
        M -.->|📋| AE
        N -.->|📋| AE
    end
    
    classDef telegram fill:#26a5e4,stroke:#1da1f2,stroke-width:2px,color:#ffffff
    classDef ai fill:#ff6b6b,stroke:#e63946,stroke-width:2px,color:#ffffff
    classDef database fill:#4ecdc4,stroke:#26a69a,stroke-width:2px,color:#ffffff
    classDef task fill:#95e1d3,stroke:#48cae4,stroke-width:2px,color:#1f2937
    classDef medical fill:#a8e6cf,stroke:#56ab2f,stroke-width:2px,color:#1f2937
    classDef financial fill:#ffd93d,stroke:#f39c12,stroke-width:2px,color:#1f2937
    classDef error fill:#ff8a80,stroke:#f44336,stroke-width:2px,color:#ffffff
    classDef success fill:#81c784,stroke:#4caf50,stroke-width:2px,color:#1f2937
    classDef process fill:#b39ddb,stroke:#9c27b0,stroke-width:2px,color:#ffffff
    
    class A,S,P,AA telegram
    class Q,R,AB,AC ai
    class AD database
    class AE task
    class G,H,X,Z medical
    class O financial
    class L,W,Y error
    class P,AA success
    class B,C,D,E,I,J,T,U process
```

### 🏢 **Technology Stack**
- 🤖 **AI Engine**: Ollama (Local LLM)
- 🗄️ **Database**: PostgreSQL with optimized schema
- ⚙️ **Automation**: n8n workflow platform
- 📋 **Task Management**: Vikunja with image attachments
- 📱 **Interface**: Telegram Bot API
- 🐳 **Deployment**: Docker Compose

---

## 💬 Usage Examples

### 📤 **Upload a Medical Document**
```
👤 User: [Sends prescription image via Telegram]
🤖 Bot: ✅ Prescription processed for Sarah!
       💊 Medication: Amoxicillin 500mg
       📅 Duration: 7 days, twice daily
       👨‍⚕️ Prescribed by: Dr. Smith
       📋 Task created in Vikunja Medical project
```

### 🩺 **Get Medication Advice**
```
👤 User: "What medication for Sarah's fever?"
🤖 Bot: 🌡️ For Sarah's fever, considering her profile:
       
       ✅ SAFE OPTIONS:
       • Paracetamol: 250mg every 6 hours
       • Ibuprofen: 200mg every 8 hours
       
       ⚠️ AVOID: Aspirin (age under 16)
       🚨 SEEK DOCTOR IF: Fever >39°C or persists >3 days
```

### 🧾 **Financial Document Processing**
```
👤 User: [Sends grocery receipt image]
🤖 Bot: 🛒 Receipt processed!
       🏪 Store: SuperMart
       💰 Amount: $45.67
       📋 Task created in Groceries project
       🗂️ Stored in financial records
```

---

## 📊 Database Schema Highlights

### 👨‍👩‍👧‍👦 **Family Management**
```sql
family_members: Telegram-linked family profiles
medical_conditions: Ongoing health conditions per member  
current_medications: Active prescriptions with dosages
allergies: Safety-critical allergy information
```

### 🏥 **Medical Records**
```sql
medical_records: Lab reports, prescriptions, diagnoses
- Linked to family members via foreign keys
- Timestamped with creation/update tracking
- Document type classification for easy querying
```

### 💳 **Financial Tracking**
```sql
financial_records: Receipts, bills, expense tracking
- Vendor recognition and amount extraction
- Category-based organization
- Date-based filtering for analytics
```

---

## 🔒 Privacy & Security

### 🛡️ **Data Protection**
- 🏠 **Self-Hosted**: Your data never leaves your infrastructure
- 🔐 **Encrypted Storage**: PostgreSQL with proper access controls
- 🔑 **Secure APIs**: Token-based authentication for all services
- 📱 **Telegram Security**: End-to-end encrypted file transfers

### ⚠️ **Medical Disclaimer**
- 🩺 AI recommendations are **not medical advice**
- 👨‍⚕️ Always consult healthcare professionals for serious conditions
- 🚨 System provides **guidance only**, not diagnosis
- 📋 Maintain regular doctor visits and professional care

---

## 🤝 Contributing

We welcome contributions! Here's how to get involved:

### 🔧 **Development Setup**
1. 🍴 Fork the repository
2. 🌿 Create feature branch: `git checkout -b feature/amazing-feature`
3. 💻 Make your changes with proper testing
4. 📝 Commit: `git commit -m 'Add amazing feature'`
5. 🚀 Push: `git push origin feature/amazing-feature`
6. 🔀 Open a Pull Request

### 🎯 **Areas for Contribution**
- 🧠 **AI Model Improvements**: Better document classification
- 🎨 **UI/UX Enhancements**: Telegram bot interactions
- 🔍 **Analytics Features**: Health trend analysis
- 🌐 **Internationalization**: Multi-language support
- 📱 **Mobile App**: Native companion apps

---

## 📜 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

---

## 📞 Support & Community

### 🆘 **Getting Help**
- 📖 **Documentation**: Check this README and inline comments
- 🐛 **Bug Reports**: [Open an issue](https://github.com/Logulokesh/KinAI-CareVault/issues)
- 💡 **Feature Requests**: We'd love to hear your ideas!
- 💬 **Discussions**: Join our community conversations

### 📧 **Contact**
- 🐙 **GitHub**: [@Logulokesh](https://github.com/Logulokesh)
- 📧 **Email**: [your-email@example.com](mailto:your-email@example.com)
- 🌐 **Project**: [KinAI-CareVault](https://github.com/Logulokesh/KinAI-CareVault)

---

<div align="center">

### 🚀 Ready to revolutionize your family's health management?

**[⭐ Star this repo](https://github.com/Logulokesh/KinAI-CareVault)** • **[🍴 Fork & Contribute](https://github.com/Logulokesh/KinAI-CareVault/fork)** • **[📖 Read the Docs](https://github.com/Logulokesh/KinAI-CareVault/wiki)**

*Built with ❤️ by the KinAI-CareVault community*

</div>
