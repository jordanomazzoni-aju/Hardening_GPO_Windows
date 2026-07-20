<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/68c73ce2-23d9-4de2-b959-098e6922bf41" />


# Windows - Hardening Básico - Part 22 - Log on as a batch job - Log on as a service

Vou destacar duas políticas que, quando mal configuradas, podem se tornar a porta de entrada para agentes de ameaça: o direito de "Logon como trabalho em lote" e o "Logon como serviço". 

Como profissionais de segurança, nosso papel é equilibrar a continuidade operacional com o Princípio do Privilégio Mínimo, e entender essas nuances é o primeiro passo.

Garanta que a configuração 'Log on as a batch job' esteja atribuída como 'Administrators'

Garanta que a configuração 'Log on as a service' esteja atribuída como 'No One' 

Essa configuração de política permite que as contas façam logon usando o serviço Agendador de Tarefas. Como o Agendador de Tarefas (task scheduler) é frequentemente usado para fins administrativos, ele pode ser necessário em ambientes corporativos. No entanto, seu uso deve ser restrito em ambientes de alta segurança para evitar o uso indevido de recursos do sistema ou para impedir que agentes maliciosos usem o direito de executar código malicioso após obterem acesso de usuário a um computador.

O direito de usuário Fazer logon como um trabalho em lote apresenta uma vulnerabilidade de baixo risco. Para a maioria das organizações, as configurações padrão são suficientes.

Log on as a service: essa configuração de política permite que as contas iniciem serviços de rede ou registrem um processo como um serviço em execução no sistema. Esse direito de usuário deve ser restrito em qualquer computador em um ambiente de alta segurança, mas como muitos aplicativos podem exigir esse privilégio, ele deve ser cuidadosamente avaliado e testado antes de ser configurado em um ambiente corporativo. Em computadores com versões de Windows mais recentes, nenhum usuário ou grupo possui esse privilégio por padrão.

O estado recomendado para esta configuração é: Ninguém ou (quando o recurso Hyper-V estiver instalado) NT VIRTUAL MACHINE\Virtual Machines ou (ao usar o Windows Defender Application Guard, como no perfil de Segurança do Windows de Próxima Geração) WDAGUtilityAccount.

Fazer logon como um serviço é um direito de usuário poderoso porque permite que as contas iniciem serviços de rede ou serviços que são executados continuamente em um computador, mesmo quando ninguém está conectado ao console. O risco é reduzido pelo fato de que somente usuários com privilégios administrativos podem instalar e configurar serviços. Um invasor que já tenha obtido esse nível de acesso poderia configurar o serviço para ser executado com a conta do Sistema Local.

Se você instalou componentes opcionais, como ASP.NET ou IIS, pode ser necessário atribuir o direito de usuário (Fazer logon como um serviço) a contas adicionais exigidas por esses componentes. O IIS exige que esse direito de usuário seja concedido explicitamente à conta de usuário ASPNET. Em estações de trabalho Windows com o recurso Hyper-V instalado, esse direito de usuário também deve ser concedido ao grupo especial NT VIRTUAL MACHINE\Virtual Machines.

Configure o valor da política em:

Computer Configuration\Windows Settings\Security Settings\Local Policies\User Rights Assignment\Log on as a batch job

Computer Configuration\Windows Settings\Security Settings\Local Policies\User Rights Assignment\Log on as a service

<img width="1087" height="697" alt="image" src="https://github.com/user-attachments/assets/c633b400-4bba-4401-b923-c4684d284a89" />

<img width="1090" height="703" alt="image" src="https://github.com/user-attachments/assets/c542c417-01c1-4c22-a33a-7bf2f7016eeb" />

Salve este post como parte do seu checklist de hardening Windows.

Como vimos, a segurança não se trata de bloquear tudo, mas de conhecer profundamente o que deve ser permitido. Enquanto o logon como trabalho em lote exige uma vigilância focada em impedir que atacantes automatizem códigos maliciosos, o logon como serviço nos desafia a mapear meticulosamente as dependências de aplicações críticas, como IIS e ambientes virtualizados com Hyper-V.

Minha recomendação é clara: a configuração padrão raramente é suficiente para ambientes de alta segurança. É imperativo que sua equipe de sistemas e segurança colabore em auditorias periódicas de GPOs, validando se esses direitos poderosos estão restritos apenas ao estritamente necessário. 

O Hardening dessas políticas neutraliza vetores comuns de escalonamento de privilégios e garante que, mesmo que uma conta seja comprometida, o raio de alcance do atacante seja drasticamente reduzido. A resiliência cibernética é construída nos detalhes.
