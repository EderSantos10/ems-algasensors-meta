# 🌡️ EMS AlgaSensors - Meta

Sistema de **monitoramento de sensores ambientais** desenvolvido em **Java 21** com **Spring Boot 3**, aplicando **arquitetura de microsserviços** e **mensageria com RabbitMQ**.  
O projeto simula dispositivos de medição que enviam dados de temperatura para uma cadeia de processamento resiliente, distribuída e escalável.

---

## 🚀 Visão Geral

O **EMS AlgaSensors** é composto por três microsserviços principais:

| Microsserviço | Função Principal |
|---------------|------------------|
| 🧩 **device-management** | Gerencia os dispositivos sensores (registro, status e informações técnicas). |
| 🌡️ **temperature-monitoring** | Publica periodicamente leituras de temperatura simuladas. |
| ⚙️ **temperature-processing** | Consome, valida e persiste os dados recebidos via RabbitMQ. |

Esses serviços se comunicam de forma **assíncrona** através do **RabbitMQ**, garantindo **resiliência**, **desacoplamento** e **tolerância a falhas**.

---

## 🏗️ Arquitetura

A arquitetura é baseada em **microsserviços independentes**, cada um com seu próprio ciclo de vida, configuração e responsabilidades bem definidas.

``mermaid
graph LR
A[Device Management] -->|HTTP/REST| B[Temperature Monitoring]
B -->|Mensagem via RabbitMQ| C[Temperature Processing]
C --> D[(Banco de Dados)]
Mensageria: RabbitMQ garante que mensagens não se percam, mesmo em caso de falhas temporárias.

Escalabilidade: Cada microsserviço pode ser escalado independentemente.

Resiliência: Implementa estratégias de retry e fila de dead-letter (DLQ).

⚙️ Tecnologias Utilizadas

☕ Java 21

🧩 Spring Boot 3

🐇 RabbitMQ

🧱 Gradle

🐳 Docker & Docker Compose

🧠 Spring RestClient

🧰 Lombok

📜 YAML Configurations

🧠 Princípios e Habilidades Aplicadas

✅ Clean Code – Código claro, coeso e de fácil manutenção.

🔄 Resiliência – Tolerância a falhas e recuperação automática de filas.

🧩 Desacoplamento – Comunicação via mensageria, reduzindo dependências diretas.

🧠 Arquitetura de Microsserviços – Independência entre serviços e implantação modular.

⚙️ Boas práticas com RabbitMQ – Exchanges, bindings e filas de dead-letter.

📦 Configuração via YAML – Facilita parametrização e ambiente customizado.

🧪 Execução com Docker Compose

Para executar todo o ambiente:

# Subir os containers
docker-compose up -d --build

# Parar e remover containers
docker-compose down


O RabbitMQ ficará disponível em:

Painel Web: http://localhost:15672

(usuário: guest, senha: guest)

📂 Estrutura de Pastas
ems-algasensors-meta/
├── configs/                 # Configurações do RabbitMQ
├── microservices/
│   ├── device-management/   # Gerenciamento de dispositivos
│   ├── temperature-monitoring/  # Publicação de dados
│   └── temperature-processing/  # Processamento de dados
├── docker-compose.yml
└── README.md

👨‍💻 Autor

Eder Santos
Desenvolvedor Java | Entusiasta em Microsserviços, Automação e IA
📧 Contato: github.com/EderSantos10


---
