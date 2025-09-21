# Projeto Linux IaC: Criação de Usuários, Grupos e Diretórios

Este projeto implementa **Infraestrutura como Código (IaC)** em Linux, automatizando a criação de usuários, grupos, diretórios e permissões.

---

## Objetivo

Automatizar a configuração de servidores Linux para gestão de usuários e permissões de diretórios, garantindo:

- Criação rápida e padronizada de usuários e grupos.
- Aplicação consistente de permissões de acesso.
- Facilidade de replicação do ambiente em outros servidores.
- Segurança, com senhas criptografadas e obrigatoriedade de troca no primeiro login.

---

## Funcionalidades

1. **Usuários convidados**
   - `guest10`, `guest11`, `guest12`, `guest13`
   - Senha padrão: `Senha123` (expirada no primeiro login)
   - Shell padrão: `/bin/bash`

2. **Diretórios**
   - `/publico` – acesso total (777)
   - `/adm` – acesso grupo ADM (770)
   - `/ven` – acesso grupo Vendas (770)
   - `/sec` – acesso grupo Segurança (770)

3. **Grupos**
   - `GRP_ADM` – administrativo
   - `GRP_VEN` – vendas
   - `GRP_SEC` – segurança

4. **Usuários vinculados a grupos**
   - **ADM:** `carlos`, `maria`, `joao`
   - **VEN:** `debora`, `sebastiana`, `roberto`
   - **SEC:** `josefina`, `amanda`, `rogerio`

5. **Segurança**
   - Senhas criptografadas com `openssl passwd -crypt`.
   - Expiração de senha no primeiro login (`passwd -e`).

---

## Estrutura do Projeto

```

projeto-linux-iac/
│
├─ criar\_usuarios\_convidados.sh   # Script de criação de usuários convidados
├─ criar\_grupos\_diretorios.sh     # Script de criação de grupos e diretórios
└─ README.md                      # Documentação do projeto

````

---

## Como Executar

1. Dê permissão de execução aos scripts:

```bash
chmod +x criar_usuarios_convidados.sh
chmod +x criar_grupos_diretorios.sh
````

2. Execute os scripts como root:

```bash
sudo ./criar_usuarios_convidados.sh
sudo ./criar_grupos_diretorios.sh
```

3. Verifique usuários, grupos e permissões:

```bash
getent passwd
getent group
ls -l /
```

---

## Permissões dos Diretórios

| Diretório | Grupo    | Permissão | Acesso           |
| --------- | -------- | --------- | ---------------- |
| /publico  | -        | 777       | Todos            |
| /adm      | GRP\_ADM | 770       | root + Grupo ADM |
| /ven      | GRP\_VEN | 770       | root + Grupo VEN |
| /sec      | GRP\_SEC | 770       | root + Grupo SEC |

---

## Benefícios do IaC

* **Automatização:** Criação de usuários, grupos e permissões sem intervenção manual.
* **Padronização:** Mesmas regras aplicadas em qualquer servidor.
* **Reprodutibilidade:** Scripts podem ser executados em novos servidores para criar o mesmo ambiente.
* **Segurança:** Senhas criptografadas e controle de acesso consistente.

---

## Autor

**Fabrício Bastos Cardoso**
Email: [fabriciobc47@gmail.com](mailto:fabriciobc47@gmail.com)
GitHub: [FabCode100](https://github.com/FabCode100)
