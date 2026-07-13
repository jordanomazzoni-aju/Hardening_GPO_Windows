<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/5f289bf8-f6e0-4155-a180-363e59a02af7" />

# Windows - Hardening Básico - Part 80 - Printers - part03

Garanta que 'Configure Windows protected print' esteja atribuido como 'Enabled'

Essa configuração de política controla se a impressão protegida do Windows está habilitada no sistema. A impressão protegida do Windows usa a plataforma de impressão moderna e o modo de impressão protegida do Windows. A impressão moderna foi projetada para funcionar somente com impressoras certificadas pela Mopria. A Mopria é um conjunto de fabricantes de impressoras e fornecedores de software que definem padrões para impressão IPP e digitalização eSCL.

O estado recomendado para essa configuração é: Habilitado.

Observação: a impressão protegida do Windows não impede que administradores ou usuários instalem drivers de impressão de terceiros por meio de um pacote de instalação fornecido pelo fabricante do dispositivo de impressão.

Para estabelecer a configuração recomendada via Política de Grupo, defina o seguinte caminho da interface do usuário como Habilitado.

Computer Configuration\Policies\Administrative Templates\Printers\Configure Windows protected print

<img width="1441" height="725" alt="image" src="https://github.com/user-attachments/assets/d980744e-5e5c-4354-b935-23b3f321d10e" />

Garanta que 'Limits print driver installation to Administrators' esteja atribuido como 'Enabled'

Essa configuração de política controla se usuários que não são administradores podem instalar drivers de impressão no sistema.

O estado recomendado para essa configuração é: Ativado.

Em 10 de agosto de 2021, a Microsoft anunciou uma alteração no comportamento padrão do recurso Apontar e Imprimir, que modifica o comportamento padrão de instalação e atualização de drivers de Apontar e Imprimir para exigir privilégios de administrador. Isso está documentado no artigo KB5005652 — Gerenciar o novo comportamento de instalação de drivers de Apontar e Imprimir (CVE-2021-34481).

Restringir a instalação de drivers de impressão a administradores pode ajudar a mitigar a vulnerabilidade PrintNightmare (CVE-2021-34527) e outros ataques ao Spooler de Impressão.

Computer Configuration\Policies\Administrative Templates\Printers\Limits print driver installation to Administrators

<img width="1436" height="733" alt="image" src="https://github.com/user-attachments/assets/9ff0e992-475c-45e3-874c-d417db21ccb1" />

Salve este post como parte do seu checklist de hardening Windows.
