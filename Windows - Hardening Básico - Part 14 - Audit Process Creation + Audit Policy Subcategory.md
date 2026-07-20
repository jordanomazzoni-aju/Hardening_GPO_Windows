

# Windows - Hardening Básico - Part 14 - Audit Process Creation + Audit Policy Subcategory

Capturar instruções sensíveis no ambiente terminal é fundamental para qualquer investigação forense. Todo detalhe é importante para registrar o passo a passo das ações para não deixar dúvidas nem lacunas.

No entanto, o preço da visibilidade pode ser alto:

Valioso para a Forense: Identifica exatamente quais argumentos e scripts um atacante utilizou.
Risco para o Compliance: Se não houver filtragem, senhas, tokens de API e dados sensíveis acabam gravados em texto claro nos logs.

Qual o ponto de equilíbrio? Monitorar é obrigatório, mas a higienização dos logs e o controle de acesso a esses eventos são o que diferenciam uma operação madura de uma vulnerável.

Manter um registro de auditoria dos logs das atividades do sistema pode ajudar a identificar erros de configuração, solucionar problemas de interrupções de serviço e analisar comprometimentos ocorridos, assim como detectar ataques. Os logs de auditoria são necessários para fornecer um rastro de evidências caso o sistema ou a rede sejam comprometidos. 

Habilitar a opção "Incluir dados da linha de comando para eventos de criação de processos" registrará as informações da linha de comando juntamente com os eventos de criação de processos no log. Isso pode fornecer detalhes adicionais quando um malware for executado em um sistema.

Se nenhuma configuração de auditoria estiver configurada, ou se as configurações de auditoria forem muito permissivas, incidentes de segurança podem não ser detectados ou não haverá evidências suficientes para análise forense de rede após a ocorrência dos incidentes. 

Configure o valor da política em:

Computer Configuration\Policies\Windows Settings\Security Settings\Local Policies\Security Options\Audit: Force audit policy subcategory settings (Windows Vista or later) to override audit policy category settings

<img width="1094" height="567" alt="image" src="https://github.com/user-attachments/assets/577bb174-2737-4aed-ba62-e33e20d68151" />

Computer Configuration\Policies\Windows Settings\Security Settings\Advanced Audit Policy Configuration\Audit Policies\Detailed Tracking\Audit Process Creation

<img width="1118" height="694" alt="image" src="https://github.com/user-attachments/assets/1c394493-7273-4be5-ac9f-3ee1204b6cb0" />

Vamos verificar os eventos nos logs do Event Viewer (Security):

 EventID: 4688
	New Process Name:	C:\Windows\System32\ipconfig.exe
	Creator Process Name:	C:\Windows\System32\cmd.exe
	Process Command Line:	ipconfig
 EventID: 4688
	New Process Name:	C:\Windows\System32\whoami.exe
	Creator Process Name:	C:\Windows\System32\cmd.exe
	Process Command Line:	whoami


  
<img width="1114" height="816" alt="image" src="https://github.com/user-attachments/assets/87d90716-d013-44c6-bd10-762c3e11d7d0" />

<img width="1118" height="856" alt="image" src="https://github.com/user-attachments/assets/0454af6a-ee7e-4a15-9433-ba2595f2a664" />

<img width="1119" height="861" alt="image" src="https://github.com/user-attachments/assets/4a89a53f-06bd-4725-a204-3b236d94e31d" />

Na imagem acima: conseguem identificar um possível vazamento de senha ? Observe o parametro - Process Command Line

Salve este post como parte do seu checklist de hardening Windows.

Na empresa que você trabalha, este tipo de configuração está implementada ? Já precisou periciar algum servidor e reconstituir toda a linha do tempo de comandos executados ?
