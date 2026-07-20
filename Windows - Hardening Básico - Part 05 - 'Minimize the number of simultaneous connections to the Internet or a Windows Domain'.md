<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/bfd3c4d5-fe90-471f-8389-198f4d1bcb23" />


# Hardening Básico - Part 05 - 'Minimize the number of simultaneous connections to the Internet or a Windows Domain'

Desativar recursos desnecessários no Windows não representa apenas bom senso, e sim uma exigência de segurança. Neste guia, mostro como minimizar o número de conexões simultâneas à Internet ou a um domínio do Windows através de políticas de grupo.

Essa configuração de política impede que os computadores estabeleçam diversas conexões simultâneas com a Internet ou com um domínio do Windows.

O estado recomendado para esta configuração é:

Ativado: 3 = Impedir Wi-Fi quando estiver em Ethernet.

(Confirme a configuração)

Impedir conexões de rede em ponte (bridged network) pode ajudar a evitar que um usuário permita, sem saber, o roteamento de tráfego entre redes internas e externas, o que corre o risco de exposição a dados internos confidenciais.

<img width="1122" height="870" alt="image" src="https://github.com/user-attachments/assets/05af4b28-d231-49c5-997b-f40d9e26b8a2" />

Computer Configuration\Policies\Administrative Templates\Network\Windows Connection Manager\Minimize the number of simultaneous connections to the Internet or a Windows Domain

Realizar esta configuração de forma consciente irá elevar o padrão e a maturidade de segurança do ambiente de Desktops. Quanto menos softwares instalados melhor. Quanto menos serviços desnecessários melhor.

Salve este post para usar como checklist em sua próxima auditoria de hardening.

Na empresa que você trabalha, quais políticas de grupo vocês usam para desativar funcionalidades de risco? Compartilhe seu checklist abaixo.

Até o próximo artigo.

#cybersecurity

#blueteam

#windows
