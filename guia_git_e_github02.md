# 📘 Guia 2 — Staging Area e Commits Avançados

Este guia aprofunda o funcionamento da **staging area**, explica como o Git registra mudanças e apresenta comandos essenciais para trabalhar com commits de forma mais avançada.

---

# 🧠 1. O que é a Staging Area (de verdade)

A *staging area* é uma área intermediária entre:

- os arquivos do seu projeto (working directory)
- o commit que você vai criar (repositório Git)

Ela funciona como uma **bandeja de supermercado**:

- você coloca itens nela (`git add`)
- depois passa tudo no caixa de uma vez (`git commit`)

Isso permite:

- escolher exatamente o que vai entrar no commit  
- separar mudanças diferentes em commits diferentes  
- evitar salvar coisas por engano  
- criar commits limpos e organizados

Você vê o que está na staging area usando:

```bash
git status
```

Exemplo:

```bash
Changes to be committed:
  new file:   script.py
```

---

# 📁 2. Estados dos arquivos no Git

Um arquivo pode estar em um destes estados:

---

## 2.1. `untracked` — não rastreado

```bash
git status
```

Saída:

```bash
Untracked files:
        script.py
```

---

## 2.2. `modified` — modificado, mas não preparado

```bash
git status
```

Saída:

```bash
Changes not staged for commit:
        modified:   app.py
```

---

## 2.3. `staged` — preparado para commit

```bash
git add app.py
git status
```

Saída:

```bash
Changes to be committed:
        modified:   app.py
```

---

## 2.4. `committed` — registrado no histórico

```bash
git commit -m "Atualiza app"
git status
```

Saída:

```bash
On branch main
nothing to commit, working tree clean
```

---

# ➕ 3. Adicionando mudanças de forma avançada

## ✔ 3.1. Adicionar um arquivo específico

```bash
git add arquivo.py
```

Saída:

```bash
Changes to be committed:
        new file:   arquivo.py
```

---

## ✔ 3.2. Adicionar todos os arquivos modificados

```bash
git add .
```

Saída:

```bash
Changes to be committed:
        modified:   app.py
        new file:   utils.py
        deleted:    old_config.json
```

---

## ✔ 3.3. Adicionar apenas parte de um arquivo (interativo)

```bash
git add -p arquivo.py
```

Saída típica:

```bash
diff --git a/arquivo.py b/arquivo.py
@@ -1,4 +1,7 @@
 def soma(a, b):
     return a + b

+def sub(a, b):
+    return a - b

Stage this hunk [y,n,q,a,d,j,J,g,/,e,?]?
```

---

## ✔ 3.4. Ver o que está na staging area

```bash
git diff --staged
```

---

## ✔ 3.5. Remover algo da staging area

```bash
git restore --staged arquivo.py
```

Saída:

```bash
Changes not staged for commit:
        modified:   arquivo.py
```

---

# 💾 4. Commits avançados

## ✔ 4.1. Editar o último commit (`--amend`)

```bash
git commit --amend
```

Saída típica:

```bash
[main 3f2a1b7] Adiciona função soma e utilidades
 2 files changed, 10 insertions(+)
```

---

## ✔ 4.2. Commit com título + descrição

```bash
git commit -m "Implementa login" -m "Adiciona validação de senha."
```

---

## ✔ 4.3. Criar commits vazios

```bash
git commit --allow-empty -m "Commit vazio"
```

---

# 🔍 5. Ver diferenças antes de commitar

## ✔ Working directory (não adicionado)

```bash
git diff
```

Saída:

```diff
+def sub(a, b):
+    return a - b
```

---

## ✔ Staging area (será commitado)

```bash
git diff --staged
```

---

# 🗑️ 6. Remover arquivos da staging area

```bash
git restore --staged arquivo.py
```

Saída:

```bash
Changes not staged for commit:
        modified:   arquivo.py
```

---

# 🧹 7. Desfazendo commits (com segurança)

## ✔ 7.1. Desfazer commit criando outro (seguro)

```bash
git revert <hash>
```

Saída:

```bash
[main 7f8e9d1] Revert "Adiciona função soma"
```

---

## ✔ 7.2. Voltar no tempo apagando commits (perigoso)

```bash
git reset --hard <hash>
```

Saída:

```bash
HEAD is now at 0f9e8d7 Cria arquivo inicial
```

---

# 🎯 8. Resumo do fluxo avançado

```
git status              → veja o estado
git diff                → veja o que mudou
git add -p              → adicione trechos específicos
git commit -m "msg"     → commit claro
git log --oneline       → revise o histórico
git revert <hash>       → desfaça commits com segurança
```

---

# 🎉 Fim do Guia 2 — Staging Area e Commits Avançados

Agora você entende:

- como funciona a staging area  
- como escolher o que entra no commit  
- como adicionar trechos específicos (`git add -p`)  
- como editar commits (`--amend`)  
- como ver diferenças (`git diff`)  
- como desfazer mudanças com segurança (`git revert`)  
- como evitar reescrever histórico acidentalmente  
- como trabalhar com commits de forma profissional  

Esse conhecimento é essencial para manter um histórico limpo, organizado e fácil de entender.
