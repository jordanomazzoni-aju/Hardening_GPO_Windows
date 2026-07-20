<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/b7da200e-6f8e-414f-8598-d8208f62a7f0" />


# Windows - Hardening Básico - Part 08 - Impedir que aplicativos do Windows sejam ativados por voz enquanto o sistema estiver bloqueado

Um recurso aparentemente inofensivo pode virar um vetor de ataque: permitir que apps do Windows sejam ativados por voz na tela de bloqueio. Mostro como desativar via GPO e por que isso é essencial no hardening de endpoints corporativos.

Certifique-se de que a opção "Permitir que os apps do Windows sejam ativados por voz enquanto o sistema estiver bloqueado" esteja definida como "Ativado: Forçar negação".

Permitir que os apps do Windows sejam ativados por voz na tela de bloqueio pode possibilitar o uso não autorizado. Exigir login garantirá que os apps sejam usados apenas por pessoal autorizado. Os usuários não poderão ativar apps enquanto o computador estiver bloqueado.

Configure o valor da política para:

Computer Configuration >> Administrative Templates >> Windows Components >> App Privacy >> "Let Windows apps activate with voice while the system is locked" to "Enabled" with Default for all Apps: set to Force Deny. 

Computer Configuration >> Administrative Templates >> Windows Components >> App Privacy" is configured to "Enabled" with Default for all Apps: set to Force Deny.

<img width="1120" height="861" alt="image" src="https://github.com/user-attachments/assets/5a79f393-4171-417a-bc2b-f5c674a840d9" />



Salve este post como parte do seu checklist de hardening Windows."

Na empresa que você trabalha, esse recurso ainda está ativo? Quais outras políticas de privacidade do Windows vocês bloqueiam por padrão?
