# AgendaEsteticaAutomotiva

Sistema Web desenvolvido em Java com Spring Boot e MongoDB Atlas para gerenciamento de clientes, serviços e agendamentos em uma estética automotiva.

---

## Objetivo

O sistema permite que clientes realizem seus próprios agendamentos de serviços automotivos, enquanto gestores podem administrar clientes, serviços e a agenda de atendimentos.

---

## Tecnologias Utilizadas

- Java 17
- Spring Boot 3.2.5
- Maven
- Thymeleaf
- MongoDB Atlas
- BCrypt
- HTML5

---

## Funcionalidades

### Autenticação

- Login de usuários
- Senhas armazenadas com BCrypt
- Controle de perfil CLIENTE e GESTOR
- Logout

### Gestão de Clientes

- Cadastro de clientes
- Listagem de clientes
- Edição de clientes
- Exclusão definitiva de clientes
- Máscara de CPF, telefone e e-mail para adequação à LGPD

### Gestão de Serviços

- Cadastro de tipos de serviços
- Listagem de serviços
- Desativação de serviços

### Gestão de Agendamentos

- Agendamento de serviços
- Edição de agendamentos
- Cancelamento de agendamentos
- Conclusão de agendamentos
- Controle de conflitos de horário
- Agenda diária
- Agenda semanal

---

## Estrutura do Projeto

```text
src/main/java/br/com/estetica

├── config
│   └── AdminInitializer
│
├── controller
│   ├── AuthController
│   ├── ClienteController
│   ├── HomeController
│   ├── TipoServicoController
│   └── AgendamentoController
│
├── model
│   ├── Usuario
│   ├── Cliente
│   ├── Veiculo
│   ├── TipoServico
│   ├── Agendamento
│   ├── PerfilUsuario
│   └── StatusAgendamento
│
├── repository
│   ├── UsuarioRepository
│   ├── ClienteRepository
│   ├── TipoServicoRepository
│   └── AgendamentoRepository
│
├── security
│   └── PasswordUtil
│
└── service
    ├── AuthService
    ├── ClienteService
    ├── TipoServicoService
    └── AgendamentoService
```

---

## Banco de Dados

O sistema utiliza MongoDB Atlas.

Configuração realizada no arquivo:

```properties
spring.data.mongodb.uri=mongodb+srv://USUARIO:SENHA@cluster.mongodb.net/agenda_estetica
```

---

## Usuário Gestor Padrão

O sistema cria automaticamente um gestor caso ele não exista.

```text
Email: admin@admin.com
Senha: admin123
```

---

## Como Executar

### 1. Clonar o projeto

```bash
git clone URL_DO_REPOSITORIO
```

### 2. Entrar na pasta

```bash
cd AgendaEsteticaAutomotiva
```

### 3. Configurar o MongoDB Atlas

Editar o arquivo:

```text
src/main/resources/application.properties
```

Inserindo a string de conexão do MongoDB Atlas.

### 4. Executar

Pelo NetBeans:

```text
Clean and Build
Run Project
```

Ou pelo Maven:

```bash
mvn spring-boot:run
```

### 5. Acessar

```text
http://localhost:8080
```

---

## Arquitetura

O projeto segue arquitetura em camadas:

- Controller Layer
- Service Layer
- Repository Layer
- MongoDB Atlas

Essa abordagem melhora a organização, manutenção e escalabilidade da aplicação.

---

## Segurança

- Senhas protegidas por BCrypt
- Controle de acesso por perfil
- Aplicação dos princípios da LGPD
- Dados sensíveis mascarados em listagens administrativas

---

## Diagramas UML

O projeto possui:

- Diagrama de Classes
- Diagrama de Sequência

Desenvolvidos para representar a estrutura do sistema e o fluxo de agendamento de serviços.

---



**João Gabriel Santos**  
Curso de Sistemas de Informação
