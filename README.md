# 🌡️ EMS AlgaSensors Meta

Sistema distribuído para **monitoramento de sensores de temperatura**, desenvolvido com **Java 21**, **Spring Boot 3** e **RabbitMQ**.  
O projeto segue uma arquitetura de **microsserviços** voltada à **resiliência**, **desacoplamento** e **boas práticas de mensageria assíncrona**.

---

## 🧩 Arquitetura do Projeto

A aplicação é composta por três microsserviços independentes, que se comunicam entre si através do **RabbitMQ**, garantindo **tolerância a falhas**, **alta disponibilidade** e **comunicação desacoplada**:

| Microsserviço | Função Principal |
|----------------|------------------|
| 🖥️ `device-management` | Gerencia o cadastro e status dos dispositivos sensores. |
| 🌡️ `temperature-monitoring` | Gera e publica medições de temperatura em intervalos definidos. |
| ⚙️ `temperature-processing` | Consome, valida e armazena as leituras recebidas via RabbitMQ. |

---

## 🚀 Tecnologias Utilizadas

- **Java 21 LTS**
- **Spring Boot 3**
- **Gradle**
- **RabbitMQ**
- **Docker & Docker Compose**
- **YAML Config**
- **Lombok**
- **Spring RestClient**
- **Spring AMQP**

---

## 🧠 Habilidades e Princípios Aplicados

- **Clean Code**: código claro, coeso e de fácil manutenção.  
- **Microsserviços**: modularidade e isolamento de responsabilidades.  
- **Resiliência**: tratamento de falhas e reconexões automáticas com RabbitMQ.  
- **Desacoplamento**: comunicação assíncrona entre serviços.  
- **Boas práticas com Mensageria**: uso de filas e tópicos de forma eficiente.  
- **Escalabilidade horizontal** com containers independentes.  

---

## ⚙️ Execução do Projeto com Docker

### Pré-requisitos
- Docker e Docker Compose instalados  
- Porta `5672` (RabbitMQ) disponível  

### Comandos

```bash
# 1. Clonar o repositório principal
git clone --recurse-submodules https://github.com/EderSantos10/ems-algasensors-meta.git
cd ems-algasensors-meta

# 2. Subir os containers
docker-compose up --build
