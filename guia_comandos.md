# 🧭 Guia rápido dos comandos essenciais do terminal (Linux / Git Bash)

Este guia explica os comandos fundamentais de **navegação, arquivos, pastas e permissões**, com exemplos reais de saída e analogias simples.

Funciona tanto em **Linux** quanto em **Git Bash no Windows**.

---

# 🌍 1. Onde estou? — `pwd`

```bash
pwd
```

**Função:** mostra o caminho completo da pasta atual.

Exemplo:

```
/c/Users/ander/OneDrive/Área de Trabalho
```

---

# 📂 2. Navegar entre pastas — `cd`

### Entrar em uma pasta
```bash
cd projetos
```

### Voltar uma pasta
```bash
cd ..
```

### Ir para a home
```bash
cd ~
```

### Ir para a raiz
```bash
cd /
```

### Símbolos
- `~` → home  
- `.` → atual  
- `..` → acima  

---

# 📋 3. Listar arquivos e pastas — `ls`

### Listar conteúdo
```bash
ls
```

### Listar com detalhes
```bash
ls -l
```

Exemplo:

```
-rw-r--r-- 1 anderson users 1024 Jun 12 09:00 notas.txt
drwxr-xr-x 2 anderson users 4096 Jun 12 08:50 projetos
```

### Listar ocultos
```bash
ls -a
```

### Combinar
```bash
ls -la
```

---

# 🏗️ 4. Criar pastas — `mkdir`

```bash
mkdir nova_pasta
```

Criar várias:

```bash
mkdir pasta1 pasta2 pasta3
```

---

# 📄 5. Criar arquivos — `touch`

```bash
touch arquivo.txt
```

Cria arquivo vazio ou atualiza data de modificação.

---

# 🗑️ 6. Apagar arquivos e pastas — `rm` e `rmdir`

### Apagar arquivo
```bash
rm arquivo.txt
```

### Apagar pasta com tudo dentro
```bash
rm -r nome_da_pasta
```

### Apagar pasta vazia
```bash
rmdir pasta_vazia
```

---

# 🔀 7. Mover ou renomear — `mv`

### Mover
```bash
mv arquivo.txt pasta/
```

### Renomear
```bash
mv antigo.txt novo.txt
```

---

# 📑 8. Copiar arquivos e pastas — `cp`

### Copiar arquivo
```bash
cp arquivo.txt copia.txt
```

### Copiar pasta inteira
```bash
cp -r pasta_original pasta_copia
```

---

# 📖 9. Ver conteúdo de arquivos — `cat` e `less`

### Mostrar conteúdo
```bash
cat arquivo.txt
```

### Ver arquivo rolando
```bash
less arquivo.txt
```

Use `q` para sair.

---

# 🧼 10. Limpar a tela — `clear`

```bash
clear
```

---

# 🔍 11. Procurar texto dentro de arquivos — `grep`

```bash
grep "texto" arquivo.txt
```

Exemplo:

```
Anderson: lembrete de reunião às 10h
```

---

# 🧩 12. Conceitos de caminhos

### Caminho absoluto
```
/home/anderson/projetos
/c/Users/ander/Documents
```

### Caminho relativo
```bash
cd projetos/meu_app
```

### Símbolos
- `~` → home  
- `.` → atual  
- `..` → acima  

---

# 🔐 13. Permissões no Linux (r, w, x)

Exemplo de `ls -l`:

```
-rwxr-xr-- 1 anderson users 1024 Jun 12 09:00 script.sh
```

### Significado
- **r** → read  
- **w** → write  
- **x** → execute  

### Para pastas
- `r` → listar  
- `w` → criar/apagar  
- `x` → entrar  

---

# 🔧 14. Alterar permissões — `chmod`

### Dar permissão de execução
```bash
chmod +x script.sh
```

### Remover permissão de escrita
```bash
chmod -w arquivo.txt
```

### Modo numérico
```
r = 4
w = 2
x = 1
```

Exemplo:

```bash
chmod 755 arquivo.sh
```

---

# 🎉 Fim do guia

Comandos essenciais para navegar, manipular arquivos e entender permissões no terminal.
