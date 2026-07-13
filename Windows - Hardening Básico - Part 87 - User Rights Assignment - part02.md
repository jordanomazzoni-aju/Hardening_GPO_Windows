<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/73802b3b-f389-45fb-a729-ed838dd2e356" />

# Windows - Hardening Básico - Part 87 - User Rights Assignment - part02

Garanta que 'Deny access to this computer from the network' esteja atribuido como 'Guests, Local account' 

Esta configuração de política proíbe os usuários de se conectarem a um computador pela rede, o que permitiria que os usuários acessassem e potencialmente modificassem dados remotamente. Em ambientes de alta segurança, não deverá haver necessidade de usuários remotos acessarem dados em um computador. Em vez disso, o compartilhamento de arquivos deve ser realizado através do uso de servidores de rede. Este direito de usuário substitui o direito de usuário Acessar este computador pela rede se uma conta estiver sujeita a ambas as políticas.

O estado recomendado para esta configuração é incluir: Convidados, Conta local .

Cuidado: Configurar uma estação de trabalho autônoma (não associada ao domínio) conforme descrito acima pode resultar na incapacidade de administrar remotamente a estação de trabalho.

Os usuários que podem fazer logon no computador pela rede podem enumerar listas de nomes de contas, nomes de grupos e recursos compartilhados. Os usuários com permissão para acessar pastas e arquivos compartilhados podem se conectar pela rede e possivelmente visualizar ou modificar dados.

Para estabelecer a configuração recomendada via GP, defina o seguinte caminho da UI para incluir Convidados, Conta local:

Computer Configuration\Policies\Windows Settings\Security Settings\Local Policies\User Rights Assignment\Deny access to this computer from the network

<img width="1429" height="828" alt="image" src="https://github.com/user-attachments/assets/88efe9e6-68e5-42c8-84ab-3f571f762a63" />

Garanta que 'Deny log on as a batch job' esteja atribuido como 'Guests' 

Essa configuração de política determina quais contas não poderão fazer logon no computador como um trabalho em lotes. Um trabalho em lote não é um arquivo em lote (.bat), mas sim um recurso de fila em lote. As contas que usam o Agendador de Tarefas para agendar trabalhos precisam desse direito de usuário.

Este direito de usuário substitui o direito de usuário Fazer logon como trabalho em lote, que pode ser usado para permitir que contas agendem trabalhos que consomem recursos excessivos do sistema. Tal ocorrência poderia causar uma condição DoS. A não atribuição deste direito de usuário às contas recomendadas pode ser um risco de segurança.

O estado recomendado para esta configuração é incluir: Convidados .

As contas que possuem o direito de usuário Fazer logon como um trabalho em lote podem ser usadas para agendar trabalhos que possam consumir recursos excessivos do computador e causar uma condição de DoS.

Para estabelecer a configuração recomendada via GP, defina o seguinte caminho de UI para incluir convidados:

Computer Configuration\Policies\Windows Settings\Security Settings\Local Policies\User Rights Assignment\Deny log on as a batch job

<img width="1432" height="835" alt="image" src="https://github.com/user-attachments/assets/a72bf51f-16a7-4596-830c-e5669f33b55e" />

Garanta que 'Deny log on as a service' esteja atribuido como 'Guests'

Essa configuração de segurança determina quais contas de serviço serão impedidas de registrar um processo como serviço. Este direito de usuário substitui o direito de usuário Fazer logon como um serviço se uma conta estiver sujeita a ambas as políticas.

O estado recomendado para esta configuração é incluir: Convidados .

Nota: Esta configuração de segurança não se aplica às contas Sistema, Serviço Local ou Serviço de Rede.

As contas que podem fazer logon como um serviço podem ser usadas para configurar e iniciar novos serviços não autorizados, como um keylogger ou outro software malicioso. O benefício da contramedida especificada é um pouco reduzido pelo fato de que apenas usuários com privilégios administrativos podem instalar e configurar serviços, e um agente de ameaça que já tenha atingido esse nível de acesso poderia configurar o serviço para ser executado com a conta do sistema.

Para estabelecer a configuração recomendada via GP, defina o seguinte caminho de UI para incluir convidados:

Computer Configuration\Policies\Windows Settings\Security Settings\Local Policies\User Rights Assignment\Deny log on as a service

<img width="1430" height="830" alt="image" src="https://github.com/user-attachments/assets/0d4a18b3-21be-46c6-9f8e-e6cde8235885" />

Salve este post como parte do seu checklist de hardening Windows.
