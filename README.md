# AI Agent Framework

Framework ini dirancang untuk membangun berbagai AI agent modular yang fleksibel, scalable, dan maintainable menggunakan **LangChain** sebagai library utama. Dengan pendekatan **MVC**, **application factory pattern**, dan struktur modular, framework ini cocok untuk kolaborasi tim serta siap diintegrasikan dalam CI/CD pipeline.

---

## Fitur Utama

- **LangChain-First Architecture**: Chain, tools, memory, dan agent abstraction.
- **Modular AI Agents**: Setiap agent bisa dikembangkan terpisah dan digabung dengan orchestrator.
- **Prompt Engineering Friendly**: Prompt disimpan dalam template file, mudah dikustomisasi.
- **Application Factory Pattern**: Inisialisasi aplikasi yang fleksibel untuk testing, dev, dan production.
- **CI/CD Ready**: Struktur siap untuk testing, containerization, dan deployment otomatis.
- **REST API Ready**: Mudah diintegrasikan dengan Flask atau FastAPI.

---

## Struktur Folder

ai_agent_framework/
│
├── app/
│   ├── __init__.py                
│   ├── agents/                    
│   │   ├── base_agent.py
│   │   ├── researcher_agent.py
│   │   ├── coder_agent.py
│   │   └── planner_agent.py
│   │
│   ├── chains/                    
│   │   ├── base_chain.py
│   │   └── custom_chain.py
│   │
│   ├── tools/                     
│   │   ├── browser.py
│   │   ├── search.py
│   │   └── code_executor.py
│   │
│   ├── memory/                    
│   │   ├── base_memory.py
│   │   └── langchain_vectorstore.py
│   │
│   ├── prompts/                   
│   │   ├── planner_prompt.txt
│   │   └── coder_prompt.txt
│   │
│   ├── routes/                    
│   │   └── agents_api.py
│   │
│   ├── controllers/               
│   │   └── agent_controller.py
│   │
│   └── services/                  
│       ├── task_manager.py
│       └── agent_orchestrator.py
│
├── config/
│   ├── __init__.py
│   ├── default.py
│   ├── development.py
│   └── production.py
│
├── tests/                         
│   ├── test_agents/
│   ├── test_services/
│   └── test_routes/
│
├── scripts/                       
│   └── deploy.sh
│
├── .env                           
├── .gitignore
├── requirements.txt               
├── pyproject.toml                 
├── Dockerfile                     
├── docker-compose.yml             
├── main.py                        
└── README.md
---

## Instalasi & Setup

```bash
git clone https://github.com/username/ai-agent-framework.git
cd ai-agent-framework

# Setup environment
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt

# Copy env
cp .env.example .env


---

Menjalankan Aplikasi

python main.py


---

Struktur main.py

from app import create_app

app = create_app(config_name="development")

if __name__ == "__main__":
    app.run()


---

Testing

pytest tests/


---

CI/CD

Struktur mendukung CI/CD berbasis:

GitHub Actions / GitLab CI

Docker + docker-compose

Linting dan test coverage otomatis



---

Kontribusi

1. Fork repo ini


2. Buat branch fitur: git checkout -b fitur-anda


3. Commit perubahan: git commit -m 'fitur baru'


4. Push branch: git push origin fitur-anda


5. Buat pull request
