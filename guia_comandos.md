# 🧭 Guia Completo dos Comandos Essenciais do Terminal (Linux / Git Bash)

Este guia explica **os comandos fundamentais de navegação, arquivos e pastas**, com explicações detalhadas e exemplos — como quando explicamos o `~`.

---

# 📌 1. Onde estou? — `pwd`

```bash
pwd
```

**Significa:** *print working directory*  
**Função:** mostra o caminho completo da pasta atual.

Exemplo de saída no Git Bash (Windows):

```
/c/Users/ander
```

---

# 📌 2. Navegar entre pastas — `cd`

Significado: change directory (mudar de diretório).

O que faz: muda a pasta atual em que você está.

### Entrar em uma pasta:
```bash
cd nome_da_pasta
```

### Voltar uma pasta:
```bash
cd ..
```

### Ir para sua pasta de usuário (home):
```bash
cd ~
```

### Ir para a raiz do sistema:
```bash
cd /
```

### Símbolos importantes:
- `~` → sua pasta de usuário  
- `.` → a pasta atual  
- `..` → a pasta acima  

---

# 📌 3. Listar arquivos e pastas — `ls`

Significado: list.

O que faz: mostra o que existe dentro da pasta atual (ou de uma pasta específica).

### Listar conteúdo da pasta atual:
```bash
ls
```

### Listar com detalhes (permissões, tamanho, datas):
```bash
ls -l
```

### Listar arquivos ocultos:
```bash
ls -a
```

Faz: mostra arquivos ocultos (os que começam com .).

### Combinar opções:
```bash
ls -la
```

### Listar arquivos e pastas da sua pasta de usuário:
```bash
ls ~
```
---

# 📌 4. Criar pastas — `mkdir`

```bash
mkdir nova_pasta
```

Criar várias pastas de uma vez:

```bash
mkdir pasta1 pasta2 pasta3
```

---

# 📌 5. Criar arquivos — `touch`

```bash
touch arquivo.txt
```

- Cria um arquivo vazio se ele não existir.
- Atualiza a data de modificação se já existir.

---

# 📌 6. Apagar arquivos e pastas — `rm` e `rmdir`

### Apagar arquivo:
```bash
rm arquivo.txt
```

⚠ **Cuidado:** não vai para lixeira.

### Apagar pasta com tudo dentro:
```bash
rm -r nome_da_pasta
```

### Apagar pasta vazia:
```bash
rmdir pasta_vazia
```

---

# 📌 7. Mover ou renomear — `mv`

### Mover arquivo:
```bash
mv arquivo.txt pasta/
```

### Renomear arquivo:
```bash
mv antigo.txt novo.txt
```

---

# 📌 8. Copiar arquivos e pastas — `cp`

### Copiar arquivo:
```bash
cp arquivo.txt copia.txt
```

### Copiar pasta inteira:
```bash
cp -r pasta_original pasta_copia
```

---

# 📌 9. Ver conteúdo de arquivos — `cat` e `less`

### Mostrar conteúdo:
```bash
cat arquivo.txt
```

### Ver arquivo rolando:
```bash
less arquivo.txt
```

- Use `q` para sair do `less`.

---

# 📌 10. Limpar a tela — `clear`

```bash
clear
```

Apenas limpa a visualização do terminal.

---

# 📌 11. Procurar texto dentro de arquivos — `grep`

```bash
grep "texto" arquivo.txt
```

Mostra linhas que contêm o texto procurado.

---

# 📌 12. Conceitos de caminhos

### Caminho absoluto:
Começa na raiz:

```
/home/anderson/projetos
/c/Users/ander/Documents
```

### Caminho relativo:
Depende da pasta atual:

```
cd projetos/meu_app
```

### Símbolos:
- `~` → home  
- `.` → atual  
- `..` → acima  

---

# 📌 13. Comandos úteis para SSH (para referência)

### Criar chave SSH:
```bash
ssh-keygen -t ed25519 -C "seu-email"
```

### Ver chave pública:
```bash
cat ~/.ssh/id_ed25519.pub
```

### Testar conexão com GitHub:
```bash
ssh -T git@github.com
```

---

# 🎉 Fim do guia

Este é o conjunto essencial de comandos para trabalhar com Git, GitHub e terminal no dia a dia.
