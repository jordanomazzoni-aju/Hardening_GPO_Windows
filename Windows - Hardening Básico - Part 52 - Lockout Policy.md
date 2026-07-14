<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/147198b7-99fe-4e7e-bc48-8efa58a340cd" />


# Windows - Hardening Básico - Part 52 - Lockout Policy

Garanta que 'Account lockout duration' esteja atribuido como '15 or more minute(s)' 

Essa configuração de política determina o período de tempo que deve passar antes que uma conta bloqueada seja desbloqueada e um usuário possa tentar fazer logon novamente. A configuração faz isso especificando o número de minutos que uma conta bloqueada permanecerá indisponível. Se o valor desta configuração de política estiver configurado como 0, as contas bloqueadas permanecerão bloqueadas até que um administrador as desbloqueie manualmente.

Embora possa parecer uma boa ideia definir o valor desta configuração de política para um valor alto, tal configuração provavelmente aumentará o número de chamadas que o suporte técnico recebe para desbloquear contas bloqueadas por engano. Os usuários devem estar cientes de quanto tempo um bloqueio permanece em vigor, para que percebam que só precisam ligar para o suporte técnico se tiverem uma necessidade extremamente urgente de recuperar o acesso ao seu computador.

O estado recomendado para esta configuração é: 15 ou mais minuto(s) .

Uma condição de negação de serviço (DoS) pode ser criada se um agente de ameaça abusar do limite de bloqueio de conta e tentar repetidamente fazer logon com uma conta específica. Depois que a configuração Limite de bloqueio de conta for configurada, a conta será bloqueada após o número especificado de tentativas malsucedidas. Se a duração do bloqueio da conta estiver definida como 0, a conta permanecerá bloqueada até que um administrador a desbloqueie manualmente.

Computer Configuration\Policies\Windows Settings\Security Settings\Account Policies\Account Lockout Policy\Account lockout duration

<img width="1207" height="913" alt="image" src="https://github.com/user-attachments/assets/bdea64d5-1fbf-4883-9b4c-cbc1542a65af" />

Garanta que 'Account lockout threshold' esteja atribuido como '5 or fewer invalid logon attempt(s), but not 0' 

Essa configuração de política determina o número de tentativas de logon malsucedidas antes que a conta seja bloqueada.

O estado recomendado para esta configuração é: 5 ou menos tentativas de logon inválidas, mas não 0 .

Definir um limite de bloqueio de conta reduz a probabilidade de um ataque de força bruta de senha online ser bem-sucedido. Definir o limite de bloqueio de conta muito baixo apresenta o risco de aumento de bloqueios acidentais e/ou de um agente de ameaça bloquear intencionalmente contas.

Se esta configuração de política estiver habilitada, uma conta bloqueada não poderá ser usada até que seja redefinida por um administrador ou até que o período de bloqueio da conta expire. Essa configuração pode gerar chamadas adicionais ao suporte técnico.

Se você aplicar essa configuração, um agente de ameaça poderá causar uma condição de negação de serviço ao gerar deliberadamente logons com falha para vários usuários; portanto, você também deverá configurar a Duração do bloqueio de conta para um valor relativamente baixo.

Se o Limite de bloqueio de conta estiver definido como 0, existe a possibilidade de que a tentativa de um agente de ameaça de descobrir senhas com um ataque de força bruta de senha passe despercebida se um mecanismo de auditoria robusto não estiver em vigor.

Computer Configuration\Policies\Windows Settings\Security Settings\Account Policies\Account Lockout Policy\Account lockout threshold

<img width="1203" height="912" alt="image" src="https://github.com/user-attachments/assets/61119bb7-ed2d-4152-a6fa-5173a2f616ee" />

Garanta que 'Reset account lockout counter after' esteja atribuido como '15 or more minute(s)'

Esta configuração de política determina o período de tempo antes que o limite de bloqueio de conta seja redefinido para zero. Se o Limite de bloqueio de conta estiver definido, esse tempo de redefinição deverá ser menor ou igual ao valor da configuração Duração do bloqueio de conta.

O estado recomendado para esta configuração é: 15 ou mais minuto(s) .

Se a política de bloqueio de conta for deixada na configuração padrão ou configurada com um intervalo excessivamente longo, o ambiente poderá ficar vulnerável a ataques de negação de serviço (DoS). Um agente de ameaça pode tentar repetidamente fazer login em várias contas, provocando bloqueios e interrompendo o acesso.

Sem um limite de bloqueio definido, os administradores precisariam redefinir manualmente as contas afetadas. No entanto, ao definir uma duração de bloqueio razoável, as contas serão desbloqueadas automaticamente após um período especificado, reduzindo a sobrecarga administrativa e mantendo a segurança.

Computer Configuration\Policies\Windows Settings\Security Settings\Account Policies\Account Lockout Policy\Reset account lockout counter after

<img width="1201" height="914" alt="image" src="https://github.com/user-attachments/assets/7dea52ae-47ed-4dbd-b160-0f26f2575c71" />

Salve este post como parte do seu checklist de hardening Windows.
