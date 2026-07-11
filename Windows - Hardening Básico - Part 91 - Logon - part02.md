<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/64570dad-2be7-4e19-b1ff-dbed5c8de7f5" />

# Windows - Hardening Básico - Part 91 - Logon - part02

Garanta que 'Enumerate local users on domain-joined computers' esteja atribuido como 'Disabled'

Essa configuração de política permite que usuários locais sejam enumerados em computadores ingressados no domínio.

O estado recomendado para essa configuração é: Desativado.

Um agente malicioso poderia usar esse recurso para coletar nomes de contas de outros usuários. Essas informações poderiam ser usadas em conjunto com outros tipos de ataques, como adivinhação de senhas ou engenharia social. O valor dessa contramedida é pequeno, pois um usuário com credenciais de domínio poderia coletar as mesmas informações de conta usando outros métodos.

Para estabelecer a configuração recomendada via Política de Grupo, defina o seguinte caminho da interface do usuário como Desativado:

* Computer Configuration\\Policies\\Administrative Templates\\System\\Logon\\Enumerate local users on domain-joined computers

![Conteúdo do artigo](https://media.licdn.com/dms/image/v2/D4D12AQEliFQ5PUIZBQ/article-inline_image-shrink_1500_2232/B4DZ4tCnr9HMAQ-/0/1778872122516?e=1785369600&v=beta&t=Jxqfn-r_pXbVEJMw4S8JGoROQ2tiR3ge45-PBgBn0Hs)

Garanta que 'Turn off app notifications on the lock screen' esteja atribuido como 'Enabled'

Essa configuração de política permite impedir que as notificações de aplicativos apareçam na tela de bloqueio.

O estado recomendado para essa configuração é: Ativado.

As notificações de aplicativos podem exibir dados comerciais ou pessoais confidenciais.

Para definir a configuração recomendada por meio da Política de Grupo, defina o seguinte caminho da interface do usuário como Ativado:

* Computer Configuration\\Policies\\Administrative Templates\\System\\Logon\\Turn off app notifications on the lock screen

![Conteúdo do artigo](https://media.licdn.com/dms/image/v2/D4D12AQGXAXPEQENdTw/article-inline_image-shrink_1000_1488/B4DZ4tCqWsIMAI-/0/1778872133383?e=1785369600&v=beta&t=BtUbLFy0Ul64Zh4WTVijhVHDPvbpD_9HwNS1-mNxlLY)

Salve este post como parte do seu checklist de hardening Windows.
