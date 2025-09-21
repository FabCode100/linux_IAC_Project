# 🖥️ Linux IaC — Automação de Usuários, Grupos e Diretórios

[![Tech Stack](https://img.shields.io/badge/Stack-Linux_IaC-blueviolet?style=for-the-badge)](https://www.linux.org/)
[![Bash Script](https://img.shields.io/badge/Scripting-Bash-black?style=for-the-badge&logo=gnu-bash&logoColor=white)](https://www.gnu.org/software/bash/)
[![License](https://img.shields.io/badge/license-MIT-green?style=for-the-badge)](LICENSE)
[![GitHub Repo Stars](https://img.shields.io/github/stars/FabCode100/linux_IAC_Project?style=for-the-badge)](https://github.com/FabCode100/linux_IAC_Project/stargazers)

**Linux IaC** é um projeto que automatiza a criação de usuários, grupos e diretórios em servidores Linux, aplicando permissões de forma padronizada e segura. Ideal para administradores de sistemas que buscam produtividade, consistência e segurança na gestão de servidores.

> ⚡ Desenvolvido com foco em **Infraestrutura como Código**, automação e boas práticas de segurança.

---

## 🚀 Funcionalidades

- 👤 Criação automática de usuários convidados (`guest10` a `guest13`)  
- 🗂️ Criação de diretórios estruturados (`/publico`, `/adm`, `/ven`, `/sec`)  
- 👥 Criação de grupos de usuários (`GRP_ADM`, `GRP_VEN`, `GRP_SEC`)  
- 🔐 Configuração de permissões de diretórios (`770` para grupos, `777` para público)  
- 🔑 Senhas criptografadas e expiração obrigatória no primeiro login  
- ♻️ Automação completa para replicação de ambientes Linux  

---

## 🛠️ Tecnologias Utilizadas

### 🖥️ Scripting
- [Bash](https://www.gnu.org/software/bash/) — Automação de tarefas no Linux  
- Comandos Linux: `useradd`, `groupadd`, `mkdir`, `chmod`, `chown`, `passwd`

### 🔐 Segurança
- Criptografia de senhas com `openssl passwd -crypt`  
- Política de expiração de senha (`passwd -e`)  

### ⚙️ Infraestrutura
- Linux Server — Ambiente de execução e testes  
- IaC — Facilita a replicação do ambiente em múltiplos servidores

---

## 💻 Como Rodar o Projeto Localmente

### ⚙️ Pré-requisitos

- Sistema Linux (Ubuntu, Debian, CentOS, etc.)  
- Acesso root ou sudo  

### 📥 Instalação e Execução

```bash
# Clone o repositório
git clone https://github.com/seuusuario/linux-iac.git
cd linux-iac
````

#### 🔧 Criação de usuários convidados

```bash
sudo chmod +x criar_usuarios_convidados.sh
sudo ./criar_usuarios_convidados.sh
```

#### 🔧 Criação de grupos e diretórios

```bash
sudo chmod +x criar_grupos_diretorios.sh
sudo ./criar_grupos_diretorios.sh
```

#### 🔍 Verificação

```bash
getent passwd      # Lista usuários
getent group       # Lista grupos
ls -l /            # Verifica diretórios e permissões
```

---

## 📁 Estrutura do Projeto

```bash
linux-iac/
├── criar_usuarios_convidados.sh   # Script de criação de usuários convidados
├── criar_grupos_diretorios.sh     # Script de criação de grupos e diretórios
└── README.md                      # Documentação do projeto
```

---

## 📈 Benefícios do IaC

* 🔄 **Automatização:** Sem intervenção manual para criar usuários e grupos
* ✅ **Padronização:** Mesmas regras aplicadas em todos os servidores
* 📦 **Reprodutibilidade:** Scripts podem ser replicados em novos servidores
* 🔐 **Segurança:** Senhas criptografadas e controle de acesso consistente

---

## 🧑‍💻 Autor

Desenvolvido por [**Seu Nome**](https://github.com/seuusuario)
💼 Administrador Linux | Apaixonado por automação, segurança e infraestrutura escalável

---

## ⭐ Contribua

Gostou do projeto?
Deixe uma ⭐ no repositório, abra *issues* ou envie *pull requests* para melhorias!
