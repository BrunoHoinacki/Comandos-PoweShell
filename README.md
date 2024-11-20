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

### 16. **Exibir Configurações de Rede (IP)** 🌐

Para exibir as configurações de rede, como endereço IP, máscara de sub-rede, gateway e servidores DNS:

```powershell
Get-NetIPAddress
```

Ou para uma visualização mais detalhada, semelhante ao **ipconfig**:

```powershell
ipconfig
```

---

### 17. **Liberar e Renovar IP (DHCP)** 🔄

- Para **liberar** o IP atual (equivalente ao `ipconfig /release`):

```powershell
Release-DhcpLease -InterfaceAlias "Ethernet"
```

- Para **renovar** o IP (equivalente ao `ipconfig /renew`):

```powershell
Renew-DhcpLease -InterfaceAlias "Ethernet"
```

---

### 18. **Configurar Endereço IP Estático** 🏠

Para definir um **endereço IP estático** para um adaptador de rede:

```powershell
New-NetIPAddress -InterfaceAlias "Ethernet" -IPAddress "192.168.1.100" -PrefixLength 24 -DefaultGateway "192.168.1.1"
```

---

### 19. **Alterar o Servidor DNS** 🔄

Para configurar **servidores DNS** específicos para um adaptador de rede:

```powershell
Set-DnsClientServerAddress -InterfaceAlias "Ethernet" -ServerAddresses ("8.8.8.8", "8.8.4.4")
```

---

### 20. **Teste de Conexão (Ping)** 📡

Para testar a conectividade com um host, como o Google:

```powershell
Test-Connection "www.google.com"
```

Ou para fazer um **ping** para um endereço IP específico:

```powershell
Test-Connection 192.168.1.1
```

---

### 21. **Rastrear a Rota até um Host (Tracert)** 🌍

Para rastrear o caminho de pacotes até um host (semelhante ao **tracert**):

```powershell
Test-NetConnection -Traceroute -RemoteAddress "www.google.com"
```

Ou para rastrear até um endereço IP:

```powershell
Test-NetConnection -Traceroute -RemoteAddress 8.8.8.8
```

---

### 22. **Verificar Conexões de Rede Ativas** 🔌

Para exibir as **conexões de rede ativas** e as portas de escuta no sistema:

```powershell
Get-NetTCPConnection
```

---

### 23. **Verificar o Status do Firewall** 🔥

Para verificar as regras de firewall e o status das conexões:

```powershell
Get-NetFirewallRule
```

Para verificar o status do firewall do Windows:

```powershell
Get-NetFirewallProfile
```

---

### 24. **Exibir Informações de Roteamento** 🛣️

Para exibir a **tabela de roteamento**:

```powershell
Get-NetRoute
```

---

### 25. **Gerenciar Conexões VPN** 🌐

Para listar as **conexões VPN** no sistema:

```powershell
Get-VpnConnection
```

Para adicionar uma nova **conexão VPN**:

```powershell
Add-VpnConnection -Name "MinhaVPN" -ServerAddress "vpn.servidor.com" -TunnelType L2tp -EncryptionLevel Required -AuthenticationMethod MSCHAPv2 -AllUserConnection
```

---

### 26. **Configurar Rede sem Fio (Wi-Fi)** 📶

- Para **visualizar as redes Wi-Fi** disponíveis:

```powershell
Get-NetWiFiNetwork
```

- Para **conectar-se a uma rede Wi-Fi** específica:

```powershell
Connect-NetWiFi -Name "Nome_da_Rede" -Password "Senha_da_Rede"
```

---

### 27. **Obter Informações sobre o Adaptador de Rede** 🖧

- Para **exibir informações detalhadas** sobre um adaptador de rede:

```powershell
Get-NetAdapter -Name "Ethernet"
```

- Para **exibir informações sobre todos os adaptadores de rede**:

```powershell
Get-NetAdapter
```

---

### 28. **Testar a Conectividade com uma Porta Específica** 🌐

Para testar a **conexão com uma porta específica**:

```powershell
Test-NetConnection -ComputerName "www.google.com" -Port 80
```

Ou testar a conexão com uma **porta personalizada**, por exemplo, 443 (HTTPS):

```powershell
Test-NetConnection -ComputerName "www.google.com" -Port 443
```

---

### 29. **Configurar Firewall para Bloquear Conexões** 🔥

Para **bloquear** uma conexão de rede através do **firewall** do Windows:

```powershell
New-NetFirewallRule -DisplayName "Bloqueio Conexão" -Direction Inbound -Action Block -Protocol TCP -LocalPort 8080
```

Para **desbloquear** uma conexão:

```powershell
Remove-NetFirewallRule -DisplayName "Bloqueio Conexão"
```

---

### 30. **Verificar e Gerenciar Túnel VPN** 🌐

Para exibir detalhes de uma conexão VPN ativa:

```powershell
Get-VpnConnection
```

Para **desconectar uma VPN**:

```powershell
Remove-VpnConnection -Name "MinhaVPN" -Force
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
