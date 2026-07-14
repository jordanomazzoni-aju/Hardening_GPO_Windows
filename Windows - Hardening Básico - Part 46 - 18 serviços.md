<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/f879cb08-084b-4644-ac22-1be277a39ae5" />


# Windows - Hardening Básico - Part 46 - 18 serviços

Antes de partir para toda e qualquer nova configuração:

Teste, teste, teste

Quais os impactos aos desativar o Remote Desktop (TermService) no seu ambiente ?

Quais os impactos aos desativar o WinRM (gerenciamento remoto) no seu ambiente ?

Quais os impactos aos desativar o Server (LanmanServer) no seu ambiente ?

Vocẽ ainda utiliza o acesso via RDP para acessar os Desktops ?

Impedir que Desktops compartilhem qualquer pasta ou impressora na rede é um problema ou um avanço ?

Garanta que 'Bluetooth Audio Gateway Service (BTAGService)' esteja atribuido como 'Disabled' 

Serviço que suporta a função de gateway de áudio do perfil Bluetooth.

A tecnologia Bluetooth apresenta riscos de segurança inerentes, especialmente em versões anteriores ao padrão v2.1. O tráfego sem fio Bluetooth não é bem criptografado (ou sequer criptografado), portanto, em um ambiente de alta segurança, não deve ser permitido, apesar do inconveniente adicional de não poder usar dispositivos Bluetooth.

Garanta que 'Bluetooth Support Service (bthserv)' esteja atribuido como 'Disabled' 

O serviço Bluetooth suporta a descoberta e associação de dispositivos Bluetooth remotos.

A tecnologia Bluetooth apresenta riscos de segurança inerentes, especialmente em versões anteriores ao padrão v2.1. O tráfego Bluetooth sem fio não é bem criptografado (ou sequer criptografado), portanto, em um ambiente de alta segurança, não deve ser permitido, apesar do inconveniente adicional de não poder usar dispositivos Bluetooth.

Garanta que 'Downloaded Maps Manager (MapsBroker)' esteja atribuido como 'Disabled' 

Serviço do Windows para acesso de aplicativos a mapas baixados. Este serviço é iniciado sob demanda pelo aplicativo que acessa os mapas baixados. Tecnologias de mapeamento podem revelar involuntariamente sua localização a agentes maliciosos e outros softwares que coletam informações. Além disso, downloads automáticos de dados de fontes de terceiros devem ser minimizados quando não forem necessários. Portanto, este serviço não deve ser necessário em ambientes de alta segurança.

Garanta que 'GameInput Service (GameInputSvc)' esteja atribuido como 'Disabled' 

Este serviço permite o uso de teclados, mouses, gamepads e outros dispositivos de entrada com a API GameInput. A API GameInput encaminha a entrada de teclados, mouses, gamepads e outros controladores de jogos via Acesso Direto à Memória (DMA) para diminuir a latência e melhorar o desempenho em jogos. Essa utilização de DMA aumenta o risco de que os dados de entrada (especialmente as teclas pressionadas) sejam capturados por um agente malicioso.

Garanta que 'Geolocation Service (lfsvc)' esteja atribuido como'Disabled' 

Este serviço monitora a localização atual do sistema e gerencia geocercas (uma localização geográfica com eventos associados). Essa configuração afeta o recurso de localização (por exemplo, GPS ou outro rastreamento de localização). Do ponto de vista da segurança, não é recomendável revelar sua localização para softwares na maioria dos casos, mas existem usos legítimos, como em softwares de mapeamento. No entanto, eles não devem ser usados em ambientes de alta segurança.

Garanta que 'Link-Layer Topology Discovery Mapper (lltdsvc)' esteja atribuido como 'Disabled' 

Cria um mapa de rede, contendo informações sobre a topologia (conectividade) de PCs e dispositivos, além de metadados que descrevem cada PC e dispositivo. O recurso habilitado por este serviço pode ser potencialmente usado para descoberta e conexão não autorizadas a dispositivos de rede. Desativar o serviço ajuda a impedir respostas a solicitações de descoberta de topologia de rede em ambientes de alta segurança.

Garanta que 'Microsoft iSCSI Initiator Service (MSiSCSI)' esteja atribuido como 'Disabled' 

Gerencia sessões iSCSI (Internet SCSI) deste computador para dispositivos remotos. Este serviço é essencial para conectar-se diretamente a um dispositivo iSCSI. No entanto, o próprio iSCSI utiliza um protocolo de autenticação muito fraco (CHAP), o que significa que as senhas para comunicação iSCSI são facilmente expostas, a menos que todo o tráfego seja isolado e/ou criptografado usando outra tecnologia como IPsec. Este serviço é geralmente mais adequado para servidores em um ambiente controlado do que para estações de trabalho que exigem alta segurança.

Garanta que 'Problem Reports and Solutions Control Panel Support (wercplsupport)' esteja atribuido como 'Disabled' 

Este serviço oferece suporte para visualização, envio e exclusão de relatórios de problemas em nível de sistema para o Painel de Controle de Relatórios e Soluções de Problemas. Ele participa do processo de exibição/relatório de problemas e soluções para/da Microsoft. Em ambientes de alta segurança, os dados nunca devem ser compartilhados com terceiros sem consentimento explícito, pois podem conter informações confidenciais.

Garanta que 'Remote Access Auto Connection Manager (RasAuto)' esteja atribuido como 'Disabled' 

Cria uma conexão com uma rede remota sempre que um programa referencia um nome ou endereço DNS ou NetBIOS remoto. A função deste serviço é fornecer uma funcionalidade de "discagem sob demanda". Em um ambiente de alta segurança, é preferível que quaisquer conexões remotas de "discagem" (sejam elas linhas telefônicas convencionais ou VPN) sejam iniciadas pelo usuário, e não automaticamente pelo sistema.

Garanta que 'Remote Desktop Configuration (SessionEnv)' esteja atribuido como 'Disabled' 

O serviço de Configuração de Área de Trabalho Remota (RDCS) é responsável por todas as atividades de configuração e manutenção de sessão relacionadas à Área de Trabalho Remota que exigem o contexto do SISTEMA. Isso inclui pastas temporárias por sessão, temas de Área de Trabalho Remota e certificados de Área de Trabalho Remota. Em um ambiente de alta segurança, o acesso à Área de Trabalho Remota representa um risco de segurança elevado. Para esses ambientes, somente o acesso ao console local deve ser permitido.

Garanta que 'Remote Desktop Services (TermService)' esteja atribuido como 'Disabled' 

Permite que os usuários se conectem interativamente a um computador remoto. A Área de Trabalho Remota e o Servidor Host de Sessão da Área de Trabalho Remota dependem desse serviço. Em ambientes de alta segurança, o acesso à Área de Trabalho Remota representa um risco de segurança elevado. Nesses ambientes, somente o acesso ao console local deve ser permitido.

Garanta que 'Remote Desktop Services UserMode Port Redirector (UmRdpService)' esteja atribuido como 'Disabled' 

Permite o redirecionamento de impressoras/unidades/portas para conexões RDP. Em um ambiente com restrições de segurança, é desejável reduzir a superfície de ataque potencial — impedir o redirecionamento de portas COM, LPT e PnP reduzirá o número de vias inesperadas para exfiltração de dados e/ou transferência de código malicioso em uma sessão RDP.

Garanta que 'Server (LanmanServer)' esteja atribuido como 'Disabled' 

Este serviço suporta o compartilhamento de arquivos, impressão e pipes nomeados na rede para este computador. Se este serviço for interrompido, essas funções ficarão indisponíveis. Em um ambiente de alta segurança, uma estação de trabalho segura deve ser apenas um cliente, não um servidor. O compartilhamento de recursos da estação de trabalho para acesso remoto aumenta o risco de segurança, pois a superfície de ataque é consideravelmente maior.

Garanta que 'Windows Error Reporting Service (WerSvc)' esteja atribuido como 'Disabled' 

Allows errors to be reported when programs stop working or responding and allows existing solutions to be delivered. Also allows logs to be generated for diagnostic and repair services. If a Windows Error occurs in a secure, enterprise managed environment, the error should be reported directly to IT staff for troubleshooting and remediation. There is no benefit to the corporation to report these errors directly to Microsoft, and there is some risk of unknowingly exposing sensitive data as part of the error.

Garanta que 'Windows Event Collector (Wecsvc)' esteja atribuido como 'Disabled' 

Permite que erros sejam relatados quando os programas param de funcionar ou responder, possibilitando a entrega de soluções existentes. Também permite a geração de logs para serviços de diagnóstico e reparo. Se um erro do Windows ocorrer em um ambiente corporativo seguro, o erro deve ser relatado diretamente à equipe de TI para solução de problemas e correção. Não há benefício para a empresa em relatar esses erros diretamente à Microsoft, e existe o risco de expor dados confidenciais inadvertidamente como parte do erro.

Garanta que 'Windows Push Notifications System Service (WpnService)' esteja atribuido como 'Disabled' 

Este serviço é executado na sessão 0 e hospeda a plataforma de notificação e o provedor de conexão que gerencia a conexão entre o dispositivo e o servidor WNS. O Windows Push Notification Services (WNS) é um mecanismo para receber notificações e atualizações de terceiros da nuvem/Internet. Em um ambiente de alta segurança, sistemas externos, especialmente aqueles hospedados fora da organização, devem ser protegidos para evitar impactos nas estações de trabalho seguras.

Garanta que 'Windows PushToInstall Service (PushToInstall)' esteja atribuido como 'Disabled' 

Este serviço gerencia os aplicativos que são enviados para o dispositivo a partir do aplicativo Microsoft Store executado em outros dispositivos ou da web. Em um ambiente gerenciado de alta segurança, as instalações de aplicativos devem ser gerenciadas centralmente pela equipe de TI, e não pelos usuários finais.

Garanta que 'Windows Remote Management (WS-Management) (WinRM)' esteja atribuido como 'Disabled'

O serviço Windows Remote Management (WinRM) implementa o protocolo WS-Management para gerenciamento remoto. O WS-Management é um protocolo padrão de serviços web usado para gerenciamento remoto de software e hardware. O serviço WinRM monitora a rede em busca de solicitações WS-Management e as processa. Recursos que permitem conexões de rede de entrada aumentam a superfície de ataque. Em um ambiente de alta segurança, o gerenciamento de estações de trabalho seguras deve ser feito localmente.

<img width="1190" height="881" alt="image" src="https://github.com/user-attachments/assets/5825308e-29e1-4480-8bc5-6bbf8fc75d45" />

Computer Configuration\Policies\Windows Settings\Security Settings\System Services\Windows Remote Management (WS-Management)

Computer Configuration\Policies\Windows Settings\Security Settings\System Services\Windows PushToInstall Service (PushToInstall)

Computer Configuration\Policies\Windows Settings\Security Settings\System Services\Windows Push Notifications System Service

Computer Configuration\Policies\Windows Settings\Security Settings\System Services\Windows Event Collector

Computer Configuration\Policies\Windows Settings\Security Settings\System Services\Windows Error Reporting Service

Computer Configuration\Policies\Windows Settings\Security Settings\System Services\Server

Computer Configuration\Policies\Windows Settings\Security Settings\System Services\Remote Desktop Services UserMode Port Redirector

Computer Configuration\Policies\Windows Settings\Security Settings\System Services\Remote Desktop Services

Computer Configuration\Policies\Windows Settings\Security Settings\System Services\Remote Desktop Configuration

Computer Configuration\Policies\Windows Settings\Security Settings\System Services\Remote Access Auto Connection Manager

Computer Configuration\Policies\Windows Settings\Security Settings\System Services\Problem Reports and Solutions Control Panel Support

Computer Configuration\Policies\Windows Settings\Security Settings\System Services\Microsoft iSCSI Initiator Service

Computer Configuration\Policies\Windows Settings\Security Settings\System Services\Link-Layer Topology Discovery Mapper

Computer Configuration\Policies\Windows Settings\Security Settings\System Services\Geolocation Service

Computer Configuration\Policies\Windows Settings\Security Settings\System Services\GameInput Service

Computer Configuration\Policies\Windows Settings\Security Settings\System Services\Downloaded Maps Manager

Computer Configuration\Policies\Windows Settings\Security Settings\System Services\Bluetooth Support Service

Computer Configuration\Policies\Windows Settings\Security Settings\System Services\Bluetooth Audio Gateway Service



$services = "BTAGService","bthserv","MapsBroker","GameInputSvc","lfsvc","lltdsvc","MSiSCSI","wercplsupport","RasAuto","SessionEnv","TermService","UmRdpService","LanmanServer","WerSvc","Wecsvc","WpnService","PushToInstall","WinRM"

$services | ForEach-Object {
    Set-Service -Name $_ -StartupType Disabled -Confirm:$false
    Stop-Service -Name $_ -Force -ErrorAction SilentlyContinue
} 


Salve este post como parte do seu checklist de hardening Windows.
