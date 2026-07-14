<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/3efb7ee0-dcfb-44c7-b50a-0c107d8c9f6e" />


# Windows - Hardening Básico - Part 51 - Remote Desktop Session

Garanta que 'Always prompt for password upon connection' esteja atribuido como 'Enabled'

Esta configuração de política especifica se os Serviços de Área de Trabalho Remota sempre solicitam uma senha ao computador cliente durante a conexão. Você pode usar essa configuração de política para impor uma solicitação de senha aos usuários que fazem logon nos Serviços de Área de Trabalho Remota, mesmo que eles já tenham fornecido a senha no cliente Conexão de Área de Trabalho Remota.

Os usuários têm a opção de armazenar seu nome de usuário e senha ao criar um novo atalho de Conexão de Área de Trabalho Remota. Se o servidor que executa os Serviços de Área de Trabalho Remota permitir que os usuários que usaram esse recurso façam logon no servidor, mas não insiram sua senha, é possível que um agente de ameaça que tenha obtido acesso físico ao computador do usuário possa se conectar a um Servidor de Área de Trabalho Remota por meio do atalho de Conexão de Área de Trabalho Remota, mesmo que não saiba a senha do usuário.

Computer Configuration\Policies\Administrative Templates\Windows Components\Remote Desktop Services\Remote Desktop Session Host\Security\Always prompt for password upon connection

Conteúdo do artigo
Garanta que 'Require secure RPC communication' esteja atribuido como 'Enabled' 

Essa configuração de política permite especificar se os Serviços de Área de Trabalho Remota exigem comunicação segura de Chamada de Procedimento Remoto (RPC) com todos os clientes ou permitem comunicação não segura.

Você pode usar essa configuração de política para fortalecer a segurança da comunicação RPC com clientes, permitindo apenas solicitações autenticadas e criptografadas.

O estado recomendado para esta configuração é: Enabled .

Permitir comunicação RPC insegura pode expor o servidor a ataques man in the middle e ataques de divulgação de dados. Os Serviços de Área de Trabalho Remota aceitam solicitações de clientes RPC que oferecem suporte a solicitações seguras e não permitem comunicação não segura com clientes não confiáveis.

Computer Configuration\Policies\Administrative Templates\Windows Components\Remote Desktop Services\Remote Desktop Session Host\Security\Require secure RPC communication

<img width="1264" height="842" alt="image" src="https://github.com/user-attachments/assets/614bc4bf-af43-4c66-93e6-80e86a06f8b9" />

Garanta que 'Require use of specific security layer for remote (RDP) connections' esteja atribuido como 'Enabled: SSL' 

Esta configuração de política especifica se será necessário o uso de uma camada de segurança específica para proteger as comunicações entre clientes e servidores Host de Sessão RD durante conexões RDP (Remote Desktop Protocol).

O estado recomendado para esta configuração é: Enabled: SSL . 

Apesar de essa configuração ser rotulada como SSL , na verdade ela está aplicando Transport Layer Security (TLS), e não o protocolo Secure Socket Layer (SSL) mais antigo e menos seguro.

A criptografia RDP nativa agora é considerada um protocolo fraco, portanto, é preferível impor o uso de criptografia TLS mais forte para todas as comunicações RDP entre clientes e servidores Host de Sessão RD.

Computer Configuration\Policies\Administrative Templates\Windows Components\Remote Desktop Services\Remote Desktop Session Host\Security\Require use of specific security layer for remote (RDP) connections

<img width="1266" height="846" alt="image" src="https://github.com/user-attachments/assets/024c19cc-427f-421d-a34e-5d2e45a41ea4" />

Garanta que 'Require user authentication for remote connections by using Network Level Authentication' esteja atribuido como 'Enabled' 

Esta configuração de política permite especificar se a autenticação do usuário será necessária para conexões remotas com o servidor Host de Sessão RD usando a Autenticação em Nível de Rede.

Exigir que a autenticação do usuário ocorra mais cedo no processo de conexão remota aumenta a segurança.

Computer Configuration\Policies\Administrative Templates\Windows Components\Remote Desktop Services\Remote Desktop Session Host\Security\Require user authentication for remote connections by using Network Level Authentication

<img width="1266" height="850" alt="image" src="https://github.com/user-attachments/assets/6c446354-3b21-4084-9af9-f307e7e68084" />

Garanta que 'Set client connection encryption level' esteja atribuido como 'Enabled: High Level'

Esta configuração de política especifica se será necessário o uso de um nível de criptografia específico para proteger as comunicações entre computadores clientes e servidores Host de Sessão RD durante conexões de Protocolo de Área de Trabalho Remota (RDP). Esta política só se aplica quando você usa criptografia RDP nativa. No entanto, a criptografia RDP nativa (em oposição à criptografia SSL) não é recomendada. Esta política não se aplica à criptografia SSL.

Se conexões de cliente de Área de Trabalho Remota que usam criptografia de baixo nível forem permitidas, é mais provável que um agente de ameaça consiga descriptografar qualquer tráfego de rede capturado dos Serviços de Área de Trabalho Remota.

Computer Configuration\Policies\Administrative Templates\Windows Components\Remote Desktop Services\Remote Desktop Session Host\Security\Set client connection encryption level

<img width="1264" height="846" alt="image" src="https://github.com/user-attachments/assets/2ce04250-71a3-41b7-9f24-1923fd582dfc" />

Salve este post como parte do seu checklist de hardening Windows.
