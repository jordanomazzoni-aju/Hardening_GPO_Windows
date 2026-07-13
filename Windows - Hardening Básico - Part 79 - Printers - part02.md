<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/8dc4741e-86b4-4910-b1ae-dd4b35e01c47" />


# Windows - Hardening Básico - Part 79 - Printers - part02

Garanta que 'Configure RPC listener settings: Protocols to allow for incoming RPC connections' esteja atribuido como 'Enabled: RPC over TCP'

Essa configuração de política controla quais protocolos as conexões de Chamada de Procedimento Remoto (RPC) recebidas pelo spooler de impressão podem usar.

O estado recomendado para essa configuração é: Ativado: RPC sobre TCP.

Essa configuração pode impedir o uso de pipes nomeados para conexões RPC com o spooler de impressão e força o uso de TCP, que é um método de comunicação mais seguro.

Para estabelecer a configuração recomendada via Política de Grupo, defina o seguinte caminho da interface do usuário como Ativado: RPC sobre TCP:

Computer Configuration\Policies\Administrative Templates\Printers\Configure RPC listener settings: Configure protocol options for incoming RPC connections

<img width="1440" height="825" alt="image" src="https://github.com/user-attachments/assets/c21da678-e5d5-42cc-a24e-a4f7077543fb" />

Garanta que 'Configure RPC listener settings: Authentication protocol to use for incoming RPC connections:' esteja atribuido como 'Enabled: Negotiate' or higher

Essa configuração de política controla quais protocolos as conexões de Chamada de Procedimento Remoto (RPC) recebidas pelo spooler de impressão podem usar.

O estado recomendado para essa configuração é: Ativado: Negociar. Configurar essa opção como Ativado: Kerberos também está em conformidade com o padrão de referência.

Essa configuração pode impedir o uso de pipes nomeados para conexões RPC com o spooler de impressão e força o uso de TCP, que é um método de comunicação mais seguro.

Para estabelecer a configuração recomendada via Política de Grupo, defina o seguinte caminho da interface do usuário como Ativado: Negociar ou Ativado: Kerberos:

Computer Configuration\Policies\Administrative Templates\Printers\Configure RPC listener settings: Configure protocol options for incoming RPC connections

<img width="1440" height="825" alt="image" src="https://github.com/user-attachments/assets/c35f9b9c-65f7-46cf-8774-92084fcd1310" />

Salve este post como parte do seu checklist de hardening Windows.
