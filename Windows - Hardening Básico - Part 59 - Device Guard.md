<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/303fee56-3ea4-4416-af3b-88e25e20f0a1" />


# Windows - Hardening Básico - Part 59 - Device Guard

Garanta que 'Turn On Virtualization Based Security' esteja atribuida como 'Enabled'

Esta configuração de política especifica se a Segurança Baseada em Virtualização está habilitada. A Segurança Baseada em Virtualização utiliza o Hipervisor do Windows para fornecer suporte a serviços de segurança.

O estado recomendado para esta configuração é: Habilitado.

Observação: A Segurança Baseada em Virtualização requer uma versão de 64 bits do Windows com Inicialização Segura habilitada, o que, por sua vez, requer que o Windows tenha sido instalado com uma configuração de BIOS UEFI, e não com uma configuração de BIOS Legada. Além disso, se o Windows estiver sendo executado em uma máquina virtual, o recurso de virtualização de CPU assistida por hardware (Intel VT-x ou AMD-V) deve ser exposto pelo host à máquina virtual convidada.

Computer Configuration\Policies\Administrative Templates\System\Device Guard\Turn On Virtualization Based Security

Garanta que 'Turn On Virtualization Based Security: Select Platform Security Level' esteja atribuida como 'Secure Boot' or higher

Esta configuração de política especifica se a Segurança Baseada em Virtualização (VBS) está habilitada. A VBS utiliza o Hipervisor do Windows para fornecer suporte a serviços de segurança.

O estado recomendado para esta configuração é: Inicialização Segura. Configurar esta opção para Inicialização Segura e Proteção DMA também está em conformidade com o padrão de referência. A Inicialização Segura pode ajudar a reduzir o risco de ataques ao carregador de inicialização e, em conjunto com as proteções DMA, ajuda a proteger os dados contra extração indevida da memória.

Computer Configuration\Policies\Administrative Templates\System\Device Guard\Turn On Virtualization Based Security: Select Platform Security Level

Garanta que 'Turn On Virtualization Based Security: Virtualization Based Protection of Code Integrity' esteja atribuida como 'Enabled with UEFI lock'

Esta configuração habilita a proteção da integridade do código no modo kernel baseada em virtualização. Quando habilitada, as proteções de memória no modo kernel são aplicadas e o caminho de validação da integridade do código é protegido pelo recurso de segurança baseado em virtualização.

O estado recomendado para esta configuração é: Habilitado com bloqueio UEFI.

Computer Configuration\Policies\Administrative Templates\System\Device Guard\Turn On Virtualization Based Security: Virtualization Based Protection of Code Integrity

Garanta que 'Turn On Virtualization Based Security: Require UEFI Memory Attributes Table' esteja atribuida como 'True (checked)'

Esta opção habilitará a Proteção de Integridade de Código Baseada em Virtualização apenas em dispositivos com suporte de firmware UEFI para a Tabela de Atributos de Memória. Dispositivos sem a Tabela de Atributos de Memória UEFI podem ter firmware incompatível com a Proteção de Integridade de Código Baseada em Virtualização, o que, em alguns casos, pode levar a falhas, perda de dados ou incompatibilidade com determinadas placas de expansão. Se esta opção não estiver ativada, os dispositivos em questão devem ser testados para garantir a compatibilidade.

O estado recomendado para esta configuração é: Verdadeiro (marcado).

Esta configuração ajudará a proteger este controle contra a ativação em um sistema incompatível, o que poderia levar a falhas ou perda de dados.

Computer Configuration\Policies\Administrative Templates\System\Device Guard\Turn On Virtualization Based Security: Require UEFI Memory Attributes Table

<img width="1264" height="846" alt="image" src="https://github.com/user-attachments/assets/2357d2a5-aceb-4aeb-a3ad-36bd5873ef93" />

Salve este post como parte do seu checklist de hardening Windows.
