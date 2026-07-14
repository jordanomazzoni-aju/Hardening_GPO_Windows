<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/f05d98c4-3c7f-4abf-bc4e-f2be01aefbc5" />


# Windows - Hardening Básico - Part 76 - App runtime

Garanta que 'Allow Microsoft accounts to be optional' esteja atribuido como 'Enabled'

Essa configuração de política permite controlar se as contas da Microsoft são opcionais para aplicativos da Windows Store que exigem uma conta para fazer login. Essa política afeta apenas os aplicativos da Windows Store que a suportam.

O estado recomendado para essa configuração é: Ativado.

Ativar essa configuração permite que uma organização use suas contas de usuário corporativas em vez de suas contas da Microsoft ao acessar aplicativos da Windows Store. Isso proporciona à organização maior controle sobre as credenciais relevantes. As contas da Microsoft não podem ser gerenciadas centralmente e, portanto, as políticas de segurança de credenciais corporativas não podem ser aplicadas a elas, o que pode colocar em risco qualquer informação acessada por meio de contas da Microsoft.

Computer Configuration\Policies\Administrative Templates\Windows Components\App runtime\Allow Microsoft accounts to be optional

<img width="1263" height="845" alt="image" src="https://github.com/user-attachments/assets/a82b5f25-0ac6-4a79-8035-57948b625586" />

Garanta que 'Block launching Universal Windows apps with Windows Runtime API access from hosted content.' esteja atribuido como 'Enabled'

Essa configuração de política controla se os aplicativos da Microsoft Store que acessam a API do Windows Runtime diretamente do conteúdo da Web podem ser executados.

O estado recomendado para essa configuração é: Ativado.

Bloquear aplicativos da Web com acesso direto à API do Windows pode impedir a execução de aplicativos maliciosos no sistema. Somente administradores de sistema devem instalar aplicativos aprovados.

Computer Configuration\Policies\Administrative Templates\Windows Components\App runtime\Block launching Universal Windows apps with Windows Runtime API access from hosted content.

<img width="1263" height="844" alt="image" src="https://github.com/user-attachments/assets/467a9d2a-5bcc-4d17-aa2e-029849e1fda9" />

Salve este post como parte do seu checklist de hardening Windows.
