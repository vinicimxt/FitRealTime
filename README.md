# FitRealTime
🏋️‍♂️ Sistema de Controle de Acesso para Academia

Este projeto simula uma catraca eletrônica com ESP32 e Arduino, permitindo o controle de entrada e saída de pessoas em uma academia. As informações são registradas em um banco de dados local e visualizadas em tempo real via uma interface web.

---

## 🎯 Objetivo

Criar uma solução local para academias que controle o acesso de usuários, forneça um painel de visualização e administre diferentes tipos de usuários (aluno e administrador), com foco em segurança e praticidade.

---

## ⚙️ Tecnologias Utilizadas

- **ESP32 + Arduino** – Leitura de sensor e envio dos dados via Wi-Fi
- **PHP + MySQL** – Backend local executado com Apache via XAMPP
- **HTML/CSS + JavaScript** – Interface gráfica e interação dinâmica
- **XAMPP** – Ambiente local com Apache e MySQL

---

## 📂 Estrutura do Projeto

```
FitRealTime/
│
├── config/              # Conexão com o banco de dados
│   └── db.php
│
├── estilizacao/         # Arquivos CSS e imagens
│   ├── style.css
│   └── logo.png
│
├── include/             # Componentes reutilizáveis
│   ├── cabecalho.php
│   ├── navbar.php
│   └── rodape.php
│
├── intermediarios/      # Lógica de login, cadastro e autenticação
│   ├── verificar_login.php
│   ├── inserir_usuario.php
│   └── inserir_admin.php
│
├── pages/               # Páginas principais da aplicação
│   ├── index.php
│   ├── login.php
│   ├── cadastro_usuario.php
│   ├── cadastro_admin.php
│   ├── contato.php
│   ├── sobre.php
│   ├── enviar_mensagem.php
│   ├── recuperar_senha.php
│   └── login_cadastro.php
│
│   └── auth/
│       ├── admin/       # Área restrita para administradores
│       │   ├── dashboard.php
│       │   └── detalhes_academia.php
│       └── user/        # Área restrita para usuários comuns
│           ├── favoritos.php
│           └── buscar_academias.php
```

---

## 📡 Como Funciona

1. O ESP32 se conecta ao Wi-Fi local e envia os dados para o servidor local (XAMPP/Apache).
2. O servidor processa a contagem de entrada e registra no banco de dados via PHP.
3. A interface web apresenta os dados atualizados e diferentes funções para usuários e administradores.

---

## 🔐 Funcionalidades

### 👤 Login e Cadastro

- Cadastro e login para **usuários comuns** e **administradores**
- Criptografia e verificação de acesso
- Redirecionamento baseado em perfil

### 📊 Painel do Administrador

- Visualização de acessos
- Gestão de usuários
- Acesso a relatórios

### 🧍 Painel do Usuário

- Visualização do próprio histórico
- Opção de atualizar dados pessoais

---

## 🚀 Como Executar o Projeto

1. Clone ou copie o projeto para a pasta `htdocs` do XAMPP:
```bash
C:\xampp\htdocs\controle-academia
```

2. Inicie o Apache e MySQL no painel do XAMPP.

3. Crie o banco de dados e importe a estrutura via phpMyAdmin usando o arquivo `Banco.txt` (não incluso aqui).Também é necessário o uso do firebase para atualização em tempo real do banco `npm install firebase` ID : 1:546497332413:web:9192f88305926aa4b1a3d4

4. Acesse no navegador:
```
http://localhost/FitRealTime/pages/index.php
```

5. Configure o ESP32 para enviar requisições HTTP para o seu servidor local (`http://<IP_LOCAL>/intermediarios/insert.php`).

---



## ✅ Considerações Finais

Este sistema é ideal para academias de pequeno e médio porte que buscam controle de acesso local, com possibilidade de expansão para nuvem, QR Code, limite de capacidade, notificações e muito mais.

