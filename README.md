# Servidor Web Linux com Nginx — Fundamentos de Infraestrutura e Cloud

Projeto prático de Linux que rodar um servidor linux estático , faz backup automatico e gerencia usuarios e grupos no linux.

---

# Objetivos do Projeto

Este projeto foi desenvolvido para praticar:

* Administração básica Linux
* Gerenciamento de usuários e permissões
* Configuração de servidor web Nginx
* Automação de backups com Bash Script
* Agendamento de tarefas com Cron
* Monitoramento de recursos do sistema
* Troubleshooting básico Linux

---

# Tecnologias Utilizadas

* Linux Ubuntu
* Nginx
* Bash Script
* Cron
* Systemd
* Ferramentas Linux CLIEstrutura do Projeto

# &#x20;Servidor Web com Nginx

## Atualizar sistema

```bash
sudo apt update && sudo apt upgrade -y
```

## Instalar Nginx

```bash
sudo apt install nginx -y
```

## Verificar status do serviço

```bash
systemctl status nginx
```

## Habilitar inicialização automática

```bash
sudo systemctl enable nginx
```

## Criar página HTML

```bash
cd /var/www/html
sudo nano index.html
```

Conteúdo:

```html
<h1>Servidor Linux funcionando!</h1>
```

## Reiniciar serviço

```bash
sudo systemctl restart nginx
```

## Verificar IP da máquina

```bash
hostname -I
```

Acessar no navegador:

```text
http://IP_DA_MAQUINA
```

---

# Backup Automático com Bash Script

## Criar diretórios

```bash
mkdir ~/arquivos_importantes
mkdir ~/backup
```

## Criar arquivos de teste

```bash
touch ~/arquivos_importantes/arquivo1.txt
touch ~/arquivos_importantes/arquivo2.txt
```

## Criar script backup.sh

```bash
nano backup.sh
```

Conteúdo:

```bash
#!/bin/bash

DATA=$(date +%Y-%m-%d)

tar -czvf ~/backup/backup-$DATA.tar.gz ~/arquivos_importantes
```

## Dar permissão de execução

```bash
chmod +x backup.sh
```

## Executar script

```bash
.backup.sh
```

## Automatizar com Cron

```bash
crontab -e
```

Adicionar:

```bash
0 22 * * * /home/USUARIO/backup.sh
```

---

# Gerenciamento de Usuários e Permissões

## Criar usuário

```bash
sudo useradd -m joao
```

## Definir senha

```bash
sudo passwd joao
```

## Criar grupo

```bash
sudo groupadd desenvolvedores
```

## Adicionar usuário ao grupo

```bash
sudo usermod -aG desenvolvedores joao
```

## Verificar grupos

```bash
groups joao
```

## Alterar permissões

```bash
chmod 755 teste.txt
```

## Alterar dono do arquivo

```bash
sudo chown joao:desenvolvedores teste.txt
```

##

---

# Habilidades Desenvolvidas

* Linux CLI
* Administração de sistemas
* Troubleshooting
* Gerenciamento de serviços
* Monitoramento Linux
* Permissões e usuários
* Automação básica
* Fundamentos de infraestrutura
* Fundamentos de cloud computing

---

# Aprendizados

Durante este laboratório foi possível compreender:

* Como funciona um servidor Linux
* Como serviços são gerenciados via systemd
* Como configurar um servidor web
* Como automatizar tarefas administrativas
* Como monitorar recursos do sistema
* Como resolver problemas comuns em ambientes Linux

---

# Autor

Cleyton

Estudante de Engenharia da Computação com foco em Linux, Cloud Computing, AWS e Infraestrutura.
