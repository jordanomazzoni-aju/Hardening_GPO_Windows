<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/881c7133-7a5c-4364-ad78-7582e74eb444" />


# Windows - Hardening Básico - Part 60 - Interactive logon

Garanta que 'Interactive logon: Machine inactivity limit' esteja configurada como '900 or fewer second(s), but not 0'

O Windows detecta a inatividade de uma sessão de logon e, se o tempo de inatividade exceder o limite definido, o protetor de tela será ativado, bloqueando a sessão.

O valor recomendado para essa configuração é de 900 segundos ou menos, e não 0.

Se um usuário se esquecer de bloquear o computador ao se afastar, é possível que alguém que passe por perto o assuma.

Computer Configuration\Policies\Windows Settings\Security Settings\Local Policies\Security Options\Interactive logon: Machine inactivity limit

Garanta que 'Interactive logon: Do not require CTRL+ALT+DEL' esteja configurada como 'Disabled'

Essa configuração de política determina se os usuários devem pressionar CTRL+ALT+DEL antes de fazer login.

O estado recomendado para essa configuração é: Desativado.

Se os usuários não forem obrigados a pressionar CTRL+ALT+DEL, eles ficarão vulneráveis a ataques que tentam interceptar suas senhas. Se CTRL+ALT+DEL for obrigatório antes do login, as senhas dos usuários serão comunicadas por meio de um caminho confiável.

Um invasor poderia instalar um programa cavalo de Troia que se parece com a caixa de diálogo de login padrão do Windows e capturar a senha do usuário. O invasor poderia então fazer login na conta comprometida com qualquer nível de privilégio que o usuário possua.

Computer Configuration\Policies\Windows Settings\Security Settings\Local Policies\Security Options\Interactive logon: Do not require CTRL+ALT+DEL

Garanta que 'Interactive logon: Don't display last signed-in' esteja configurada como 'Enabled'

Essa configuração de política determina se o nome da conta do último usuário a fazer logon nos computadores cliente da sua organização será exibido na tela de logon do Windows de cada computador.

O estado recomendado para essa configuração é: Ativado.

Um invasor com acesso ao console (por exemplo, alguém com acesso físico ou alguém que consiga se conectar ao servidor por meio dos Serviços de Área de Trabalho Remota) poderia visualizar o nome do último usuário que fez logon no servidor. O invasor poderia então tentar adivinhar a senha, usar um dicionário ou realizar um ataque de força bruta para tentar fazer logon.

Computer Configuration\Policies\Windows Settings\Security Settings\Local Policies\Security Options\Interactive logon: Don't display last signed-in



<img width="1266" height="848" alt="image" src="https://github.com/user-attachments/assets/f1dcfc9d-89d7-4b2d-80a1-fe9013f4e6bf" />

<img width="1264" height="844" alt="image" src="https://github.com/user-attachments/assets/cc796246-d0de-45b4-9433-d0195851224a" />

<img width="1266" height="845" alt="image" src="https://github.com/user-attachments/assets/a95c4045-9d0a-4c2e-89c4-dcb1a4f578af" />

Salve este post como parte do seu checklist de hardening Windows.
