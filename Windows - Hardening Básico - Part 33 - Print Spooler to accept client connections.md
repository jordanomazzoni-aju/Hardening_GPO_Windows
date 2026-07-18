<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/d6e10ab9-7244-4fcc-a78c-0516615a82c3" />


# Windows - Hardening Básico - Part 33 - Print Spooler to accept client connections

O serviço de Spooler de Impressão (historicamente onipresente) tornou-se um vetor de alto risco com a descoberta da vulnerabilidade PrintNightmare (CVE-2021-34527), que permite a execução remota de código com privilégios de sistema.

Como medida de mitigação prioritária, especialmente em Controladores de Domínio e servidores que não desempenham o papel de servidores de impressão, a desativação da capacidade do serviço de aceitar conexões de entrada é fundamental. Esta configuração isola o serviço de requisições externas, neutralizando vetores de ataque remotos conhecidos, embora a vigilância contra vetores locais deva permanecer no radar da equipe de SOC. Considere também desabilitar no escopo Desktops e Estações de Trabalho.

Garanta que 'Allow Print Spooler to accept client connections' esteja atribuido como 'Disabled'

Esta configuração de política controla se o serviço de Spooler de Impressão aceitará conexões de clientes.

O serviço de Spooler de Impressão precisa ser reiniciado para que as alterações nesta política entrem em vigor.
Desativar a capacidade do serviço de Spooler de Impressão de aceitar conexões de clientes mitiga ataques remotos contra a vulnerabilidade PrintNightmare (CVE-2021-34527) e outros ataques remotos ao Spooler de Impressão. No entanto, esta recomendação não mitiga ataques locais ao serviço de Spooler de Impressão.

Computer Configuration\Policies\Administrative Templates\Printers\Allow Print Spooler to accept client connections

<img width="1171" height="944" alt="image" src="https://github.com/user-attachments/assets/5fd2d5fe-6311-4563-801b-490aea76aeb2" />

Desde que o serviço de Spooler de Impressão não esteja desativado, os usuários continuarão podendo imprimir a partir de suas estações de trabalho. No entanto, o serviço de Spooler de Impressão da estação de trabalho não aceitará conexões de clientes nem permitirá que os usuários compartilhem impressoras. Observe que todas as impressoras que já estavam compartilhadas continuarão sendo compartilhadas.

Verificando staus do serviço:

Get-Service Spooler | Select-Object Status, StartType
Desabilitando via gpmc.msc:

<img width="1147" height="817" alt="image" src="https://github.com/user-attachments/assets/4cd4d525-f39b-4d8c-964c-a9372c98450a" />

Salve este post como parte do seu checklist de hardening Windows.
