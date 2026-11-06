\# Self-Hosted Local LLM Stack



A GPU-accelerated local AI chat service built with Docker Compose on WSL2.



\## Architecture

\- \*\*Ollama\*\*: model server with NVIDIA GPU passthrough

\- \*\*Open WebUI\*\*: browser chat interface with built-in document upload (basic RAG)

\- Named volumes for persistent models and chat data

\- `restart: unless-stopped` for service-style reliability



\## Hardware

Ryzen 7 5800U, 16 GB RAM, RTX 3050 Ti (4 GB VRAM), Windows 11 + WSL2



\## Run it

&#x20;   docker compose up -d

&#x20;   docker exec -it ai-ollama-1 ollama pull llama3.2:3b

Then open http://localhost:3000



\## Results

\- GPU passthrough verified with `nvidia-smi` (screenshot below)

\- llama3.2:3b loaded at 80% GPU / 20% CPU on 4 GB VRAM

\- Resume-bullet test: model followed a "no invented facts" constraint



\## What I learned

\- How container networking lets services find each other by name

\- Why named volumes matter for persistence

\- How VRAM limits affect model offload



\## Screenshots

!\[nvidia-smi](screenshots/nvidia-smi.png)

