# Agendador de Horários / Appointment Scheduler

Complete appointment scheduling API developed with Java Spring Boot featuring layered architecture and conflict validation.

API completa de agendamento de horários desenvolvida em Java Spring Boot com arquitetura em camadas e validação de conflitos.

## 📋 About the Project / Sobre o Projeto
Backend system for managing service appointments, ensuring that each time slot is unique for a given professional. Prevents double-booking and provides a clean RESTful interface for scheduling.

Sistema backend para gerenciar agendamentos de serviços, garantindo que cada horário seja único para um determinado profissional. Previne duplicidade de reservas e fornece uma interface RESTful clara para agendamento.

## 🛠️ Technologies / Tecnologias
- **Java 21**
- **Spring Boot 4.0.5**
- **Spring Data JPA**
- **H2 Database** (in-memory for testing/demo)
- **Maven**
- **Hibernate**
- **Lombok**

## 🏗️ Architecture / Arquitetura
- Layered architecture (Controller → Service → Repository)
- Arquitetura em camadas (Controller → Service → Repository)
- RESTful API
- Business logic validation (conflict checking)
- Validação de regras de negócio (verificação de conflitos)
- JPA/Hibernate for persistence

## 🖼️ API Demonstration / Demonstração da API

### Successful Appointment Creation / Criação de Agendamento com Sucesso
![Successful creation](https://res.cloudinary.com/dfqbfplrb/image/upload/v1775347525/teste1certo_rqws8b.png)

### Conflict Validation / Validação de Conflito
*Attempting to book an already occupied time slot returns a `RuntimeException: Horário já está preenchido`.*

![Conflict error](https://res.cloudinary.com/dfqbfplrb/image/upload/v1775347764/testerro1_vm2yes.png)
![Error details](https://res.cloudinary.com/dfqbfplrb/image/upload/v1775347853/testerro2_fmwdnu.png)

### Booking a Free Time Slot / Agendando um Horário Livre
![Booking new time](https://res.cloudinary.com/dfqbfplrb/image/upload/v1775347914/test2certo_dwubdp.png)

## 📡 Main Endpoints / Endpoints Principais

### Appointments / Agendamentos
| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/agendamentos` | Create a new appointment / Criar novo agendamento |
| `GET` | `/agendamentos` | List all appointments / Listar todos agendamentos |
| `GET` | `/agendamentos/{id}` | Find appointment by ID / Buscar agendamento por ID |
| `PUT` | `/agendamentos/{id}` | Update appointment / Atualizar agendamento |
| `DELETE` | `/agendamentos/{id}` | Delete appointment / Deletar agendamento |

### Request Body Example (POST/PUT)
```json
{
  "servico": "Cabelo",
  "profissional": "Keven",
  "dataHoraAgendamento": "2026-04-05T11:00:00",
  "cliente": "Italo",
  "telefoneCliente": "8592738919"
}
```

🚀 How to Run / Como Executar
Clone the repository / Clone o repositório:

bash
git clone https://github.com/eaeitalo/agendador-horarios.git
cd agendador-horarios
Run the application / Execute a aplicação:

bash
mvn spring-boot:run
Access:

API: http://localhost:8080/agendamentos

H2 Console: http://localhost:8080/h2-console

JDBC URL: jdbc:h2:mem:agendamentos-db

User Name: sa

Password: (leave empty)

📊 Features / Funcionalidades
✅ Create, Read, Update, Delete appointments (CRUD)

✅ Conflict validation – prevents double-booking the same time slot for the same professional

✅ In-memory H2 database for easy testing

✅ Layered architecture following best practices
```
👨‍💻 Developer / Desenvolvedor
Italo - @eaeitalo

### ✅ What you need to do:

1. **Save the text above** as a new file called `README.md` in the root of your project folder.
2. **Place your screenshots** inside a folder like `images/` or directly in the root. Then update the image paths in the README (e.g., change `/imagem_2026-04-04_205304979.png` to `images/imagem_2026-04-04_205304979.png` if you use a subfolder).
3. **Commit and push** to GitHub:
   ```bash
   git add README.md images/
   git commit -m "docs: add professional README with API demonstration"
   git push origin main
