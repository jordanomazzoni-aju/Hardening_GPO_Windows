<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/cf9f572f-4f54-4451-a77e-b9e0510d3cf1" />


# Hardening Básico - Part 02 - System Services - XBox

Serviços relacionados ao Xbox Live no Windows podem ser explorados em ataques internos. Neste guia, mostro como desativá-los via PowerShell e por que isso deve estar no seu checklist de hardening de endpoints corporativos.

Avalie sempre o contexto organizacional. O Xbox Live é um serviço de jogos e geralmente não tem lugar em um ambiente empresarial gerenciado (a menos que seja uma empresa de jogos ou uma Lan House).

Certifique-se de que o serviço 'Xbox Accessory Management Service (XboxGipSvc)' esteja definido como 'Disabled'

Certifique-se de que o serviço 'Xbox Live Auth Manager (XblAuthManager)' esteja definido como 'Disabled'

Certifique-se de que o serviço 'Xbox Live Game Save (XblGameSave)' esteja definido como 'Disabled' 

Certifique-se de que o serviço 'Xbox Live Networking Service (XboxNetApiSvc)' esteja definido como 'Disabled'

<img width="994" height="735" alt="image" src="https://github.com/user-attachments/assets/a4aaf29e-598b-47b5-ae65-0b506d738387" />

Impacto:

Os acessórios Xbox conectados podem não funcionar.

Os dados de jogos salvos não serão enviados nem baixados da Xbox Live.

As conexões com a Xbox Live podem falhar e os aplicativos que interagem com esse serviço também podem falhar.

1-) Desative serviços relacionados ao Xbox: (Comandos Powershell)

Stop-Service -Name XblGameSave -Force

Set-Service -Name XblGameSave -StartupType Disabled

Stop-Service -Name XblAuthManager -Force

Set-Service -Name XblAuthManager -StartupType Disabled

Stop-Service -Name XboxGipSvc -Force

Set-Service -Name XboxGipSvc -StartupType Disabled

Stop-Service -Name XboxNetApiSvc -Force

Set-Service -Name XboxNetApiSvc -StartupType Disabled

2-) Confirmando o Status dos Serviços

Get-Service | Where-Object { $_.Name -like "*Xbox*" -or $_.Name -like "*Gaming*" -or $_.Name -like "*Xbl*"} 

<img width="982" height="663" alt="image" src="https://github.com/user-attachments/assets/00c734fd-cfa7-4dfe-b229-368129e8a1d7" />

Desabilitar estes serviços de forma consciente irá elevar o padrão e a maturidade de segurança do ambiente de Desktops. Quanto menos software instalado melhor. Quanto menos serviço desnecessário melhor.

Salve este post para usar como checklist em sua próxima auditoria de hardening

Na empresa que você trabalha, quais serviços do Windows ainda estão ativos por compatibilidade? Como vocês mitigam os riscos? 

Até o próximo artigo. 

#cybersecurity

#blueteam

#windows

#infosec
