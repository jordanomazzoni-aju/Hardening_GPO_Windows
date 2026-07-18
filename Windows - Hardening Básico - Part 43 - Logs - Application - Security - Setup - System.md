<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/5ed080d9-2015-42b8-a177-3b1bf7b3c2bb" />


# Windows - Hardening Básico - Part 43 - Logs - Application - Security - Setup - System

A primeira configuração de política controla o comportamento do log de eventos quando o arquivo de log atinge seu tamanho máximo.

A segunda configuração de política especifica o tamanho máximo do arquivo de log em quilobytes. O tamanho máximo do arquivo de log pode ser configurado entre 1 megabyte (1.024 quilobytes) e 2 terabytes (2.147.483.647 quilobytes) em incrementos de quilobytes.

Se os eventos não forem registrados, poderá ser difícil ou impossível determinar a causa raiz dos problemas do sistema ou das atividades não autorizadas dos agentes da ameaça.

A consequência desta configuração é que os eventos mais antigos serão removidos dos logs. Os atores da ameaça podem tirar vantagem de tal configuração, porque podem gerar um grande número de eventos estranhos para substituir qualquer evidência do seu ataque. Esses riscos podem ser reduzidos um pouco se você automatizar o arquivamento e o backup dos dados do log de eventos.

Em contextos modernos os logs são enviados em um curto espaço de tempo para um SIEM mitigando os problemas acima.


Garanta que 'Application: Control Event Log behavior when the log file reaches its maximum size' esteja atribuido como 'Disabled'

Garanta que 'Application: Specify the maximum log file size (KB)' esteja atribuido como 'Enabled: 32,768 ou valor superior'

Garanta que 'Security: Control Event Log behavior when the log file reaches its maximum size' esteja atribuido como 'Disabled'

Garanta que 'Security: Specify the maximum log file size (KB)' esteja atribuido como 'Enabled: 196,608 ou valor superior'

Garanta que 'Setup: Control Event Log behavior when the log file reaches its maximum size' esteja atribuido como 'Disabled'

Garanta que 'Setup: Specify the maximum log file size (KB)' esteja atribuido como 'Enabled: 32,768 ou valor superior'

Garanta que 'System: Control Event Log behavior when the log file reaches its maximum size' esteja atribuido como 'Disabled'

Garanta que 'System: Specify the maximum log file size (KB)' esteja atribuido como 'Enabled: 32,768 ou valor superior

 

<img width="1261" height="848" alt="image" src="https://github.com/user-attachments/assets/af37ef0d-6168-4272-bf4b-197e229f17d0" />

<img width="1267" height="847" alt="image" src="https://github.com/user-attachments/assets/b2bdfbf5-0da6-43ed-93ea-eafd49562581" />

<img width="1267" height="851" alt="image" src="https://github.com/user-attachments/assets/c13a11d2-c898-41c8-98ed-dc5ff36423c5" />


Investir no hardening das diretivas de log é garantir que o seu time de resposta a incidentes tenha as pegadas necessárias para caçar o invasor antes da criptografia. Segurança de verdade não se faz apenas com firewalls de última geração, mas com a higiene básica de garantir que cada evento crítico deixe um rastro auditável. Afinal, em um incidente, a única coisa pior do que ser atacado é não saber como, quando e por quem.
