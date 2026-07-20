<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/532d8a76-6d93-4fc6-ac26-e5a6fabe0059" />


# Hardening Básico - Part 03 - System Services - Windows Mobile Hotspot Service (icssvc)

Serviços do Windows mal configurados são portas abertas para ataques. Neste guia, mostro como desativar o serviço Windows Mobile Hotspot Service (icssvc) utilizando comandos Powershell. 

Este serviço oferece a capacidade de compartilhar uma conexão de dados de celular com outro dispositivo. A capacidade de executar um hotspot móvel a partir de um computador conectado a um domínio facilita a exposição a rede interna.

Impacto:

O recurso Windows Mobile Hotspot não estará disponível.

Comando PowerShell:

Stop-Service -Name icssvc -Force

Set-Service -Name icssvc -StartupType Disabled

Get-Service | Where-Object { $_.Name -like "*icssvc*"} 

<img width="970" height="425" alt="image" src="https://github.com/user-attachments/assets/2946632c-4afd-4ae2-a7e4-39e29279f176" />

Desabilitar serviços de forma consciente irá elevar o padrão e a maturidade de segurança do ambiente de Desktops. Quanto menos software instalado melhor. Quanto menos serviço desnecessário melhor.

Salve este post para usar como checklist em sua próxima auditoria de hardening

Na empresa que você trabalha, quais serviços do Windows ainda estão ativos por compatibilidade? Como vocês mitigam os riscos? 

Até o próximo artigo.

#cybersecurity

#blueteam

#windows

#infosec
