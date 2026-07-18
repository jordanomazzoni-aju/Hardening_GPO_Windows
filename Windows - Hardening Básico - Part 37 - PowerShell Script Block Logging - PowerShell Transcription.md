<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/842ec3dc-0860-4987-baf0-8818e024a1bf" />


# Windows - Hardening Básico - Part 37 - PowerShell Script Block Logging - PowerShell Transcription

O PowerShell é o melhor amigo do administrador e o grande aliado do invasor. Scripts ofuscados e comandos codificados em Base64 são projetados para enganar olhos humanos e ferramentas de monitoramento básicas.

A implementação de Script Block Logging e PowerShell Transcription não é opcional para ambientes maduros. Neste artigo, mostro como transformar o PowerShell de uma ameaça silenciosa em uma trilha forense inestimável para o seu Blue Team.

Garanta que 'Turn on PowerShell Script Block Logging' esteja atribuido como 'Enabled' 

Se o registro de eventos de início/fim de invocação de bloco de script estiver habilitado (caixa de opção marcada), o PowerShell registrará eventos adicionais quando a invocação de um comando, bloco de script, função ou script for iniciada ou interrompida. Habilitar essa opção gera um grande volume de logs de eventos. Avaliar o volume de logs gerados.

Os logs de entrada de scripts do PowerShell podem ser muito valiosos ao realizar investigações forenses de incidentes de ataque ao PowerShell para determinar o que ocorreu.

Computer Configuration\Policies\Administrative Templates\Windows Components\Windows PowerShell\Turn on PowerShell Script Block Logging
Applications and Services Logs\Microsoft\Windows\PowerShell\Operational 

Garanta que 'Turn on PowerShell Transcription' esteja atribuido como 'Enabled'

A transcrição do PowerShell pode ser muito valiosa em investigações forenses de incidentes de ataque ao PowerShell para determinar o que ocorreu.

Computer Configuration\Policies\Administrative Templates\Windows Components\Windows PowerShell\Turn on PowerShell Transcription
Pasta: %USERPROFILE%\Documents
(Se em sua empresa o projeto definiu um caminho centralizado (ex: \\Servidor\Logs), todos os logs de todos os usuários daquela máquina estarão lá.
Procure por pastas com o nome no formato de data (ex: 20260331) ou arquivos começando com PowerShell_transcript

A transcrição do PowerShell será registrada em arquivos de saída PowerShell_transcript, que são salvos na pasta Meus Documentos (dentro de uma subpasta separada para cada dia) do perfil de cada usuário por padrão. Opcionalmente, um nome de diretório de saída específico pode ser especificado, que conterá todos os registros de transcrição do PowerShell em uma subpasta de Meus Documentos. Se um caminho completo fora da pasta Meus Documentos do usuário for especificado, outros usuários do sistema poderão ter acesso a esses registros, que podem conter informações confidenciais, como senhas.

Existem riscos potenciais de captura de credenciais e informações confidenciais em arquivos de saída PowerShell_transcript, que podem ser expostas a usuários com acesso de leitura aos arquivos.

<img width="1263" height="847" alt="image" src="https://github.com/user-attachments/assets/dedd5dfa-6f51-4760-ae93-1105adf2233e" />

<img width="1266" height="850" alt="image" src="https://github.com/user-attachments/assets/91b54dd5-1c34-44a3-9fc8-322de5c3b9cf" />

<img width="1246" height="824" alt="image" src="https://github.com/user-attachments/assets/43ea3c4e-ce0b-485f-a9e0-874325f81c59" />

<img width="1202" height="775" alt="image" src="https://github.com/user-attachments/assets/5fa48ad7-903a-4165-8835-6d68c57a1c7d" />

Salve este post como parte do seu checklist de hardening Windows.
