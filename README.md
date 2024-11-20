# Guia de Comandos PowerShell 🖥️💻

Este repositório contém uma lista de **comandos úteis para PowerShell** que você pode usar para gerenciar arquivos, diretórios e muito mais. Ideal para desenvolvedores e administradores de sistemas! 🚀

---

## Comandos Básicos de Arquivo e Diretório 📂

### 1. Listar Arquivos e Diretórios 🔍

Para listar os arquivos e diretórios no diretório atual:

```powershell
ls
```

Ou com uma visualização mais detalhada:

```powershell
Get-ChildItem
```

---

### 2. Criar um Novo Diretório 📁

Para criar um novo diretório:

```powershell
New-Item -ItemType Directory -Name "nome_do_diretorio"
```

Ou a versão curta:

```powershell
mkdir nome_do_diretorio
```

---

### 3. Remover Diretório (vazio ou não vazio) 🧹

- Para remover um diretório **vazio**:

```powershell
Remove-Item nome_do_diretorio
```

- Para remover um diretório **não vazio**:

```powershell
Remove-Item nome_do_diretorio -Recurse
```

---

### 4. Criar um Novo Arquivo ✍️

Para criar um novo arquivo e adicionar conteúdo a ele:

```powershell
"Conteúdo do arquivo" | Out-File "nome_do_arquivo.txt"
```

---

### 5. Copiar Arquivo ou Diretório 📑

- Para copiar um arquivo:

```powershell
Copy-Item "origem" "destino"
```

- Para copiar um diretório **recursivamente**:

```powershell
Copy-Item "origem" "destino" -Recurse
```

---

### 6. Mover ou Renomear Arquivo 🔄

- Para **mover** um arquivo para outro diretório:

```powershell
Move-Item "origem" "destino"
```

- Para **renomear** um arquivo:

```powershell
Rename-Item "arquivo_antigo" "novo_nome"
```

---

### 7. Excluir Arquivo ⚠️

Para excluir um arquivo:

```powershell
Remove-Item "nome_do_arquivo"
```

Adicione a opção `-Force` para forçar a exclusão de arquivos protegidos.

---

### 8. Buscar Arquivos 🔎

Para buscar arquivos dentro do diretório atual e subdiretórios:

```powershell
Get-ChildItem -Recurse -Filter "nome_do_arquivo.extensao"
```

Ou se você quiser buscar por nome com um padrão:

```powershell
Get-ChildItem -Recurse | Where-Object { $_.Name -like "*parte_do_nome*" }
```

---

## Comandos Avançados ⚡

### 9. Verificar o Espaço em Disco 💽

Para verificar o uso do disco em sua máquina:

```powershell
Get-PSDrive
```

### 10. Mudar para Outro Diretório 📂

Para navegar entre diretórios:

```powershell
Set-Location "caminho_do_diretorio"
```

Ou apenas:

```powershell
cd "caminho_do_diretorio"
```

---

### 11. Listar Processos em Execução 🛠️

Para listar os processos em execução no seu sistema:

```powershell
Get-Process
```

### 12. Parar um Processo 🔴

Para parar um processo pelo nome:

```powershell
Stop-Process -Name "nome_do_processo"
```

Ou para parar um processo pelo ID:

```powershell
Stop-Process -Id 1234
```

---

### 13. Obter Informações do Sistema 🖥️

Para obter detalhes sobre o sistema, como versão do Windows:

```powershell
Get-ComputerInfo
```

Ou para verificar a versão do PowerShell:

```powershell
$PSVersionTable.PSVersion
```

---

### 14. Comprimir Arquivos 🗜️

Para comprimir um arquivo ou diretório em um arquivo ZIP:

```powershell
Compress-Archive -Path "caminho_do_arquivo" -DestinationPath "arquivo_comprimido.zip"
```

---

### 15. Descomprimir Arquivos 📦

Para extrair arquivos de um arquivo ZIP:

```powershell
Expand-Archive -Path "arquivo_comprimido.zip" -DestinationPath "diretorio_destino"
```

---

## Dicas e Truques Extras ✨

- **Usando Variáveis no PowerShell:**

  Para criar uma variável e atribuir valor:

  ```powershell
  $nome_da_variavel = "valor"
  ```

- **Redirecionando Saída para Arquivo 📄**

  Para salvar a saída de um comando em um arquivo de texto:

  ```powershell
  comando | Out-File "arquivo.txt"
  ```

- **Executando Script no PowerShell ⌨️**

  Para rodar um script `.ps1`:

  ```powershell
  .\script.ps1
  ```

  Se você tiver problemas de segurança, pode alterar a política de execução:

  ```powershell
  Set-ExecutionPolicy RemoteSigned
  ```

---

## Referências 📚

- [Documentação Oficial do PowerShell](https://docs.microsoft.com/en-us/powershell/)
- [Comandos PowerShell no Tutorialspoint](https://www.tutorialspoint.com/powershell/index.htm)

---
📝 **Feito com amor por [Bruno Hoinacki](https://www.linkedin.com/in/brunohoinacki/)!**
```
