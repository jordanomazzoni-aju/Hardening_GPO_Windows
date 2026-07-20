<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/8ca3b63e-f24c-4d6e-a1ba-d49208652683" />


# Windows - Hardening Básico - Part 07 - Windows Remote Management (WinRM)

O Windows Remote Management (WinRM) é um alvo subestimado em ataques laterais. Neste guia técnico, mostro como desativar configurações perigosas através de GPOs no passo a passo abaixo.

Atribua os valores:

Para WinRM Client

Garanta que a configuração 'Allow Basic authentication' esteja atribuída como 'Disabled'

Garanta que a configuração 'Allow unencrypted traffic' esteja atribuída como 'Disabled'

Garanta que a configuração 'Disallow Digest authentication' esteja atribuída como 'Enabled'

Para WinRM Service

Garanta que a configuração 'Allow Basic authentication' esteja atribuída como 'Disabled' 

Garanta que a configuração 'Allow unencrypted traffic' esteja atribuída como 'Disabled' 

Garanta que a configuração 'Disallow WinRM from storing RunAs credentials' esteja atribuída como 'Enabled'

Para - WinRM Client

1-) A autenticação básica é menos robusta do que outros métodos de autenticação disponíveis no WinRM, pois as credenciais, incluindo senhas, são transmitidas em texto não criptografado. Um agente malicioso capaz de capturar pacotes na rede onde o WinRM está em execução pode ser capaz de determinar as credenciais usadas para acessar hosts remotos via WinRM.

Computer Configuration\Policies\Administrative Templates\Windows Components\Windows Remote Management (WinRM)\WinRM Client\Allow Basic authentication

2-) A criptografia do tráfego de rede WinRM reduz o risco de um agente malicioso visualizar ou modificar as mensagens WinRM enquanto elas transitam pela rede.

Computer Configuration\Policies\Administrative Templates\Windows Components\Windows Remote Management (WinRM)\WinRM Client\Allow unencrypted traffic

3-) A autenticação Digest é menos robusta do que outros métodos de autenticação disponíveis no WinRM. Um agente malicioso capaz de capturar pacotes na rede onde o WinRM está em execução pode ser capaz de determinar as credenciais usadas para acessar hosts remotos via WinRM.

Computer Configuration\Policies\Administrative Templates\Windows Components\Windows Remote Management (WinRM)\WinRM Client\Disallow Digest authentication

<img width="1112" height="715" alt="image" src="https://github.com/user-attachments/assets/2a228903-f2b6-46f9-b3f5-f3ff34fb18cc" />

Para - WinRM Service

Computer Configuration\Policies\Administrative Templates\Windows Components\Windows Remote Management (WinRM)\WinRM Service\Allow Basic authentication
Computer Configuration\Policies\Administrative Templates\Windows Components\Windows Remote Management (WinRM)\WinRM Service\Allow unencrypted traffic

1-) Embora a capacidade de armazenar credenciais de execução como seja um recurso conveniente, ela aumenta ligeiramente o risco de comprometimento da conta. Por exemplo, se você se esquecer de bloquear sua área de trabalho antes de deixá-la sem supervisão por alguns minutos, outra pessoa poderá acessar não apenas a área de trabalho do seu computador, mas também quaisquer hosts que você gerencie via WinRM com credenciais de execução como armazenadas em cache.

Computer Configuration\Policies\Administrative Templates\Windows Components\Windows Remote Management (WinRM)\WinRM Service\Disallow WinRM from storing RunAs credentials

<img width="1117" height="746" alt="image" src="https://github.com/user-attachments/assets/547a583d-b530-4e41-9546-52582471e968" />

Realizar estas configurações de forma consciente irá elevar o padrão e a maturidade de segurança do ambiente de Desktops. Quanto menos softwares instalados melhor. Quanto menos serviços desnecessários melhor.

Salve este post para referência rápida em sua rotina de hardening.

Até o próximo artigo.

#cybersecurity

#blueteam

#windows
