# 🧭 Guia Completo e Detalhado dos Comandos Essenciais do Terminal (Linux / Git Bash)

Este guia explica **os comandos fundamentais de navegação, arquivos, pastas e permissões**, com explicações detalhadas, exemplos e analogias.

Ele serve tanto para **Linux** quanto para **Git Bash no Windows**, pois ambos usam os mesmos comandos básicos.

---

# 🌍 1. Onde estou? — `pwd`

```bash
pwd
```

**Significa:** *print working directory*  
**Função:** mostra o caminho completo da pasta atual.

É como perguntar ao terminal:  
> “Em qual pasta eu estou agora?”

Exemplo de saída no Git Bash:

```
/c/Users/ander
```

---

# 📂 2. Navegar entre pastas — `cd`

**Significa:** *change directory*  
**Função:** muda a pasta atual.

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

**Analogia:**  
Pense no terminal como um explorador de arquivos sem janelas.  
O `cd` é como clicar duas vezes em uma pasta.

---

# 📋 3. Listar arquivos e pastas — `ls`

**Significa:** *list*  
**Função:** mostra o conteúdo da pasta atual.

### Listar conteúdo:
```bash
ls
```

### Listar com detalhes:
```bash
ls -l
```

Mostra:
- permissões  
- dono  
- grupo  
- tamanho  
- data  
- nome  

### Listar arquivos ocultos:
```bash
ls -a
```

Arquivos ocultos começam com `.` (ex: `.ssh`, `.git`).

### Combinar opções:
```bash
ls -la
```

---

# 🏗️ 4. Criar pastas — `mkdir`

**Significa:** *make directory*  
**Função:** cria uma nova pasta.

```bash
mkdir nova_pasta
```

Criar várias de uma vez:

```bash
mkdir pasta1 pasta2 pasta3
```

---

# 📄 5. Criar arquivos — `touch`

```bash
touch arquivo.txt
```

- Cria um arquivo vazio se ele não existir.  
- Atualiza a data de modificação se já existir.

É muito usado para criar arquivos rapidamente.

---

# 🗑️ 6. Apagar arquivos e pastas — `rm` e `rmdir`

### Apagar arquivo:
```bash
rm arquivo.txt
```

⚠ **Cuidado:** não vai para lixeira.

### Apagar pasta com tudo dentro:
```bash
rm -r nome_da_pasta
```

- `-r` → *recursive* (apaga tudo dentro da pasta).

### Apagar pasta vazia:
```bash
rmdir pasta_vazia
```

---

# 🔀 7. Mover ou renomear — `mv`

### Mover arquivo:
```bash
mv arquivo.txt pasta/
```

### Renomear arquivo:
```bash
mv antigo.txt novo.txt
```

**Analogia:**  
É como arrastar um arquivo para outra pasta ou renomeá-lo no Explorer.

---

# 📑 8. Copiar arquivos e pastas — `cp`

### Copiar arquivo:
```bash
cp arquivo.txt copia.txt
```

### Copiar pasta inteira:
```bash
cp -r pasta_original pasta_copia
```

- `-r` → copia recursivamente (incluindo subpastas).

---

# 📖 9. Ver conteúdo de arquivos — `cat` e `less`

### Mostrar conteúdo:
```bash
cat arquivo.txt
```

### Ver arquivo rolando:
```bash
less arquivo.txt
```

- Use `q` para sair do `less`.

**Quando usar qual?**  
- `cat` → arquivos pequenos  
- `less` → arquivos grandes  

---

# 🧼 10. Limpar a tela — `clear`

```bash
clear
```

Apenas limpa a visualização do terminal.

---

# 🔍 11. Procurar texto dentro de arquivos — `grep`

```bash
grep "texto" arquivo.txt
```

Mostra linhas que contêm o texto procurado.

Exemplo:

```bash
grep "Anderson" notas.txt
```

---

# 🧩 12. Conceitos de caminhos (importantíssimo)

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

# 🔐 13. Permissões no Linux (r, w, x)

No Linux (e Git Bash), cada arquivo/pasta tem permissões.

Quando você usa `ls -l`, vê algo assim:

```
-rwxr-xr--
```

Isso representa:

```
[ dono ] [ grupo ] [ outros ]
 rwx      r-x       r--
```

### Significado das letras:

- **r** → read (ler)
- **w** → write (escrever)
- **x** → execute (executar)

### Para arquivos:
- `r` → pode abrir/ler  
- `w` → pode editar  
- `x` → pode executar (scripts, programas)

### Para pastas:
- `r` → pode listar conteúdo  
- `w` → pode criar/apagar arquivos dentro  
- `x` → pode entrar na pasta (`cd`)

### Exemplo explicado:

```
drwxr-xr--
```

- `d` → é diretório  
- `rwx` → dono pode tudo  
- `r-x` → grupo pode ler e entrar  
- `r--` → outros só podem ler  

---

# 🔧 14. Alterar permissões — `chmod`

### Dar permissão de execução:
```bash
chmod +x script.sh
```

### Remover permissão de escrita:
```bash
chmod -w arquivo.txt
```

### Modo numérico (mais avançado):

```
r = 4
w = 2
x = 1
```

Exemplo:

```bash
chmod 755 arquivo.sh
```

Significa:

- 7 → dono: rwx  
- 5 → grupo: r-x  
- 5 → outros: r-x  

---

# 🎉 Fim do guia

Este é o conjunto essencial de comandos para trabalhar com terminal no dia a dia, com explicações detalhadas, analogias e exemplos práticos.
