Projeto 3 — Automação de Backup

Este projeto é um script em Python que faz backup automático de arquivos entre pastas e registra tudo em logs com data e hora.

O que ele faz

Copia arquivos automaticamente
Move todos os arquivos de uma pasta para outra, mantendo a estrutura de subpastas.

Gera logs detalhados
Cada execução cria um log com horário, arquivos copiados e possíveis erros.

Pode rodar sozinho
Dá para agendar no Windows (Agendador de Tarefas) e deixar backups diários ou semanais automatizados.

O que esse projeto demonstra

Automação prática de verdade (não é só teoria)

Algo útil no dia a dia de empresas

Organização e rastreabilidade com logs

Como usar
Opção 1 — Rodar pela primeira vez (modo exemplo)

Na primeira execução, o script cria uma pasta exemplo_origem com arquivos de teste e gera o backup em backup_destino.

cd projeto3_backup
python backup.py

Também dá para usar os atalhos:

Windows (PowerShell): duplo clique em rodar.ps1 ou execute .\rodar.ps1

Windows (CMD): duplo clique em rodar.bat ou execute rodar.bat

Opção 2 — Definir origem e destino
python backup.py "C:\Pasta\Origem" "D:\Backups\Destino"
Opção 3 — Personalizar onde salvar os logs
python backup.py "C:\Origem" "D:\Backup" --logs "C:\LogsBackup"
Onde ficam os logs

Por padrão: dentro da pasta logs/ do projeto

Nome do arquivo: backup_AAAA-MM-DD_HH-MM-SS.log

Cada log mostra:

Data e hora da execução

Arquivos copiados

Resumo final (quantidade e erros, se houver)

Como automatizar no Windows

Você pode deixar o backup rodando sozinho com o Agendador de Tarefas:

Abra o Agendador de Tarefas (taskschd.msc)

Clique em Criar Tarefa Básica

Nome: Backup automático

Escolha quando rodar (diário ou semanal)

Ação: Iniciar um programa

Programa: python (ou caminho completo do python.exe)

Argumentos:
"C:\caminho\projeto3_backup\backup.py" "C:\Origem" "D:\Backup"

Campo Iniciar em:
C:\caminho\projeto3_backup

Pronto — o backup roda sozinho e os logs ficam salvos para consulta.
