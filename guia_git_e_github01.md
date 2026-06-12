# 📘 Guia 1 — Git Básico: Repositório Local (sem GitHub)

Este guia é para quem está começando **do zero** com Git e quer entender, de forma prática e comentada, como funciona o **versionamento local** — ou seja, tudo que acontece **no seu computador**, sem envolver GitHub ainda.

A ideia é: você termina este guia entendendo **o que é um repositório**, **como iniciar**, **como configurar**, **como salvar versões** e **como ver o estado do seu projeto**.

---

## 🧠 1. O que é Git (em poucas palavras)

Git é um **sistema de controle de versão**.

Em vez de você ficar com:

- `projeto_final_v1`
- `projeto_final_v2`
- `projeto_final_definitivo`
- `projeto_final_definitivo_mesmo`

Git guarda **o histórico de mudanças** dentro de uma pasta oculta chamada `.git`.

Você não precisa criar cópias do projeto — o Git faz isso por você, de forma inteligente.

---

## 📂 2. Iniciando um repositório — `git init`

### Quando usar?

Quando você tem uma pasta com arquivos (por exemplo, um projeto Python) e quer começar a versionar com Git.

### Comando:

```bash
git init
```

### O que acontece?

- Git cria uma pasta oculta chamada `.git` dentro da pasta atual.
- Essa pasta guarda **todo o histórico**, **configurações** e **metadados** do repositório.

### Como verificar?

```bash
ls -a
```

Você verá:

```
.git
```

> **Importante:**  
> Nunca mexa manualmente dentro da pasta `.git`.  
> Ela é o “cérebro” do Git.

---

## 🧾 3. Configurações do Git — `git config` (global e local)

Git precisa saber **quem é você**, para registrar seus commits com nome e e-mail.

### Configuração global (vale para todos os repositórios do seu usuário)

```bash
git config --global user.name "Seu Nome"
git config --global user.email "seu-email@exemplo.com"
```

Isso grava seu nome e e-mail no arquivo de configuração global do Git.

### Ver configurações globais:

```bash
git config --global --list
```

### Configuração local (vale só para o repositório atual)

Se você quiser usar um nome/e-mail diferente em um projeto específico:

```bash
git config user.name "Outro Nome"
git config user.email "outro-email@exemplo.com"
```

### Ver configurações locais:

```bash
git config --list
```

> **Resumo:**
> - `--global` → vale para todos os repositórios do seu usuário.
> - sem `--global` → vale só para o repositório atual.

---

## 🔍 4. Ver o estado do repositório — `git status`

Esse é um dos comandos mais importantes.

### Comando:

```bash
git status
```

### O que ele mostra?

- em qual branch você está (por padrão, `main` ou `master`)
- quais arquivos foram modificados
- quais arquivos estão prontos para commit (staging)
- quais arquivos não estão sendo rastreados (untracked)

Exemplo de saída:

```text
On branch main
Untracked files:
  (use "git add <file>..." to include in what will be committed)
    script.py
```

> **Dica:**  
> Use `git status` o tempo todo.  
> Ele é seu “painel de controle”.

---

## 📁 5. Adicionar arquivos ao controle de versão — `git add`

Antes de salvar uma versão (commit), você precisa dizer ao Git **quais arquivos** farão parte dessa versão.  
Isso é feito com o `git add`, que coloca arquivos na **staging area**.

### Adicionar um arquivo específico:

```bash
git add script.py
```

### Adicionar todos os arquivos modificados:

```bash
git add .
```

### O que é a staging area?

É uma “área de preparação” onde você coloca os arquivos que vão entrar no próximo commit.

> **Analogia:**  
> Pense na staging area como uma bandeja de coisas que você vai levar para o caixa.  
> Você escolhe o que entra na bandeja (`git add`), e depois fecha a compra (`git commit`).

---

## 💾 6. Salvar uma versão — `git commit`

Depois de adicionar arquivos com `git add`, você salva uma versão com `git commit`.

### Comando básico:

```bash
git commit -m "Mensagem do commit"
```

### O que acontece?

- Git cria um **snapshot** (foto) do estado dos arquivos que estavam na staging area.
- Essa foto é registrada com:
  - autor (seu nome/e-mail)
  - data
  - mensagem
  - identificador único (hash)

### Exemplo:

```bash
git add script.py
git commit -m "Adiciona script inicial"
```

> **Importante:**  
> A mensagem do commit deve explicar **o que foi feito**, não “o que você sentiu”.  
> Exemplo bom: `"Implementa função de login"`  
> Exemplo ruim: `"mexendo aí"`.

---

## 🗂️ 7. `.gitignore` — ignorando arquivos

Nem tudo deve ser versionado.

Exemplos:

- arquivos temporários  
- pastas de build  
- arquivos de configuração locais  
- `.env` com senhas  

Para isso, existe o arquivo `.gitignore`.

### Criar um `.gitignore`:

```bash
touch .gitignore
```

### Exemplo de conteúdo:

```text
__pycache__/
.env
*.log
```

Isso diz ao Git:

- ignore a pasta `__pycache__/`
- ignore o arquivo `.env`
- ignore qualquer arquivo `.log`

> **Dica:**  
> Sempre tenha um `.gitignore` em projetos reais.

---

## 🧭 8. Ver histórico de commits — `git log`

Depois de alguns commits, você pode ver o histórico:

```bash
git log
```

Exemplo de saída:

```text
commit 123abc456def
Author: Anderson <anderson@exemplo.com>
Date:   2025-01-01 12:00:00

    Adiciona script inicial

commit 789xyz000aaa
Author: Anderson <anderson@exemplo.com>
Date:   2025-01-02 09:30:00

    Implementa função de login
```

### Versão resumida:

```bash
git log --oneline
```

Exemplo:

```text
123abc4 Adiciona script inicial
789xyz0 Implementa função de login
```

---

## 🔁 9. Fluxo básico de trabalho com Git local

Aqui está o fluxo típico:

1. **Iniciar repositório:**
   ```bash
   git init
   ```

2. **Configurar nome e e-mail (uma vez):**
   ```bash
   git config --global user.name "Seu Nome"
   git config --global user.email "seu-email@exemplo.com"
   ```

3. **Ver estado:**
   ```bash
   git status
   ```

4. **Adicionar arquivos:**
   ```bash
   git add .
   ```

5. **Salvar versão:**
   ```bash
   git commit -m "Mensagem clara do que foi feito"
   ```

6. **Ver histórico:**
   ```bash
   git log --oneline
   ```

---

## 🧩 10. Resumo rápido (para colar na parede)

```text
git init
    → transforma uma pasta comum em repositório Git

git config --global user.name "Nome"
git config --global user.email "email"
    → define quem é você (para todos os repositórios)

git status
    → mostra o estado atual (arquivos modificados, rastreados, etc.)

git add arquivo / git add .
    → coloca arquivos na staging area (preparação para commit)

git commit -m "mensagem"
    → salva uma versão (snapshot) dos arquivos na staging area

.gitignore
    → lista de arquivos/pastas que o Git deve ignorar

git log / git log --oneline
    → mostra o histórico de commits
```

---

## 🎉 Fim do Guia 1 — Git Básico: Repositório Local

Depois de dominar este guia, você está pronto para:

- aprofundar em **staging area e commits**  
- aprender **branches**  
- começar a conectar seu repositório local com o GitHub  

Nos próximos guias, vamos construir em cima disso, sem pular etapas.
