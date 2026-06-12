# 📘 Guia 1 — Git Básico + Configurações

Este guia ensina Git **do zero**, com explicações claras, exemplos reais e saídas do terminal comentadas.  
Ideal para quem está começando e quer entender **o que está fazendo** em cada comando.

---

# 🧠 1. O que é Git (em poucas palavras)

Git é um **sistema de controle de versão distribuído**.  
Ele registra o histórico completo do seu projeto e permite voltar no tempo, comparar versões e trabalhar com segurança — tudo isso **sem depender de internet**.

Quando você usa Git em uma pasta, ele cria uma pasta oculta chamada:

```
.git
```

Essa pasta transforma uma pasta comum em um **repositório Git** e guarda:

- histórico de commits  
- branches  
- configurações  
- referências internas  
- metadados  
- objetos compactados do Git  

> **Nunca mexa manualmente dentro da pasta `.git`.**  
> Ela é o “cérebro” do repositório — alterar algo ali pode corromper todo o histórico.

Git funciona registrando **snapshots** (fotos) do estado do projeto a cada commit.  
Ele não salva arquivos inteiros repetidamente — salva **apenas as diferenças**, o que o torna rápido e eficiente.

**Analogia:**  
Pense no Git como um “histórico infinito” do seu projeto, onde cada commit é uma foto do momento.

---

# ⚙️ 2. Configurações do Git — system, global e local

Git possui **3 níveis de configuração**, cada um armazenado em um arquivo diferente:

| Nível | Afeta quem? | Arquivo onde fica |
|------|-------------|-------------------|
| **system** | todos os usuários da máquina | `/etc/gitconfig` |
| **global** | apenas o usuário atual | `~/.gitconfig` |
| **local** | apenas o repositório atual | `.git/config` |

### ✔ Ordem de prioridade

```
local > global > system
```

> Se uma configuração existe no nível local, ela sobrescreve a global e a system.

---

## 🧾 2.1. Ver configurações

### Ver todas as configurações ativas

```bash
git config --list
```

### Ver apenas as globais

```bash
git config --global --list
```

### Ver apenas as locais

```bash
git config --local --list
```

### Ver de onde vem cada configuração

```bash
git config --show-origin --list
```

Exemplo:

```
file:C:/Users/ander/.gitconfig   user.name=Anderson
file:.git/config                 user.email=local@exemplo.com
```

---

## 🧑‍💻 2.2. Definir nome e e-mail

### Global (recomendado)

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seu-email@exemplo.com"
```

### Local (somente no repositório atual)

```bash
git config user.name "Nome Local"
git config user.email "email-local@exemplo.com"
```

---

## ❌ 2.3. Remover (unset) configurações

### Local

```bash
git config --unset user.name
git config --unset user.email
```

### Global

```bash
git config --global --unset user.name
git config --global --unset user.email
```

### System (raro, exige permissões elevadas)

```bash
git config --system --unset user.name
git config --system --unset user.email
```

---

## 🧩 2.4. Outras configurações úteis

### Branch padrão como `main`

```bash
git config --global init.defaultBranch main
```

### Editor padrão (VS Code)

```bash
git config --global core.editor "code --wait"
```

### Ativar cores

```bash
git config --global color.ui auto
```

### `.gitignore` global

```bash
git config --global core.excludesfile ~/.gitignore_global
```

---

# 🧾 3. Configurar nome e e-mail

Git precisa saber **quem está fazendo os commits**.

### Global

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seu-email@exemplo.com"
```

### Local

```bash
git config user.name "Nome Local"
git config user.email "email-local@exemplo.com"
```

### Ver origem das configurações

```bash
git config --show-origin --list
```

Exemplo:

```
file:C:/Users/ander/.gitconfig   user.name=Anderson
file:.git/config                 user.email=local@exemplo.com
```

### Remover

Global:

```bash
git config --global --unset user.name
```

Local:

```bash
git config --unset user.name
```

---

# 📂 4. Iniciando um repositório — `git init`

Para começar a versionar uma pasta:

```bash
git init
```

Saída típica:

```
Initialized empty Git repository in C:/Users/ander/exemplo/.git/
```

Isso significa:

- Git criou um repositório vazio  
- A pasta `.git` foi criada  

Verificando:

```bash
ls -a
```

```
.  ..  .git  arquivo1.py
```

### Quando usar `git init`?

- quando você cria um projeto do zero

### Quando **não** usar?

- ao clonar um repositório (o Git já cria `.git` automaticamente)

---

# 🔍 5. Ver o estado do repositório — `git status`

```bash
git status
```

Exemplo:

```
On branch main
No commits yet
Untracked files:
  script.py
```

Significa:

- você está na branch `main`  
- não há commits  
- `script.py` não está sendo rastreado  

Outros estados importantes:

- **Changes not staged for commit** → arquivo modificado, mas não adicionado  
- **Changes to be committed** → arquivo na staging area  
- **working tree clean** → nada a fazer  

---

# 📁 6. Adicionar arquivos — `git add`

Adicionar um arquivo:

```bash
git add script.py
```

Adicionar todos:

```bash
git add .
```

Verificando:

```bash
git status
```

```
Changes to be committed:
  new file: script.py
```

### A *staging area* é como uma bandeja de supermercado:

- você coloca itens nela (`git add`)  
- passa tudo no caixa (`git commit`)  

---

# 💾 7. Salvar uma versão — `git commit`

```bash
git commit -m "Mensagem clara"
```

Exemplo:

```
[main (root-commit) 1a2b3c4] Adiciona script inicial
 1 file changed, 10 insertions(+)
 create mode 100644 script.py
```

Significa:

- **root-commit** → primeiro commit  
- **1a2b3c4** → hash do commit  
- **10 insertions** → 10 linhas adicionadas  

Boas práticas:

- mensagens claras  
- verbos no imperativo  
- explique o que foi feito  

---

# 🗂️ 8. `.gitignore` — ignorando arquivos

Criar:

```bash
touch .gitignore
```

Exemplo:

```
__pycache__/
.env
*.log
```

Ignorar arquivo já rastreado:

```bash
git rm --cached arquivo.txt
```

`.gitignore` global:

```bash
git config --global core.excludesfile ~/.gitignore_global
```

---

# 🧭 9. Ver histórico — `git log`

```bash
git log
```

Exemplo:

```
commit 1a2b3c4
Author: Anderson
Date: Tue Jan 1

    Adiciona script inicial
```

Versão resumida:

```bash
git log --oneline
```

Sair do log:

```
q
```

---

# 🔁 10. Fluxo básico de trabalho (local)

```
git init
git config --global user.name "Nome"
git config --global user.email "Email"
git status
git add .
git commit -m "mensagem"
git log --oneline
```

---

# 🎉 Fim do Guia 1 — Git Básico + Configurações

Agora você entende:

- como iniciar um repositório  
- como configurar o Git  
- como interpretar saídas do terminal  
- como adicionar arquivos  
- como fazer commits  
- como ignorar arquivos  
- como ver o histórico  
- como seguir o fluxo básico de trabalho  

Esse é o alicerce para todos os próximos guias.
