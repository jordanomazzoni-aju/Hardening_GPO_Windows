<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/c922cd11-7634-4bca-85ff-5d4c47db21fa" />


# Windows - Hardening Básico - Part 67 - Credentials Delegation

Garanta que 'Encryption Oracle Remediation' esteja atribuido como 'Enabled: Force Updated Clients'

Algumas versões do protocolo CredSSP, usado por certos aplicativos (como a Conexão de Área de Trabalho Remota), são vulneráveis a um ataque de oráculo de criptografia contra o cliente. Esta política controla a compatibilidade com clientes e servidores vulneráveis e permite definir o nível de proteção desejado para a vulnerabilidade de oráculo de criptografia.

O estado recomendado para esta configuração é: Ativado: Forçar Clientes Atualizados.

Esta configuração é importante para mitigar a vulnerabilidade de oráculo de criptografia do CredSSP, para a qual a Microsoft publicou informações em 13/03/2018 no CVE-2018-0886 | Vulnerabilidade de Execução Remota de Código no CredSSP. Todas as versões do Windows, do Windows Vista em diante, são afetadas por esta vulnerabilidade e serão compatíveis com esta recomendação, desde que tenham sido corrigidas pelo menos até maio de 2018 (ou posterior).

Computer Configuration\Policies\Administrative Templates\System\Credentials Delegation\Encryption Oracle Remediation

<img width="1264" height="844" alt="image" src="https://github.com/user-attachments/assets/c15a4c1b-5bb0-4d6e-9352-05de07c54fb4" />



Garanta que 'Remote host allows delegation of non-exportable credentials' esteja atribuido como 'Enabled'

Ao usar a delegação de credenciais, os dispositivos fornecem uma versão exportável das credenciais para o host remoto. Isso expõe os usuários ao risco de roubo de credenciais por agentes maliciosos no host remoto. O Modo de Administrador Restrito e o Windows Defender Remote Credential Guard são duas opções para ajudar a proteger contra esse risco.

O estado recomendado para essa configuração é: Ativado.

Computer Configuration\Policies\Administrative Templates\System\Credentials Delegation\Remote host allows delegation of non-exportable credentials

<img width="1262" height="842" alt="image" src="https://github.com/user-attachments/assets/ab6106a2-dcf5-4256-bb0a-2d0a6cf37438" />

Salve este post como parte do seu checklist de hardening Windows.
