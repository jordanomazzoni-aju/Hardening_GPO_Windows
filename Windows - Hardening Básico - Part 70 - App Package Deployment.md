<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/320b6a12-10a0-4caa-a073-218a668cdb2b" />


# Windows - Hardening Básico - Part 70 - App Package Deployment

Garanta que 'Allow a Windows app to share application data between users' esteja atribuido como 'Disabled' 

Gerencia a capacidade de um aplicativo do Windows compartilhar dados entre usuários que o instalaram. Os dados são compartilhados por meio da pasta SharedLocal. Essa pasta está disponível através da API Windows . Storage.

O estado recomendado para essa configuração é: Desativado.

Usuários de um sistema podem compartilhar acidentalmente dados confidenciais com outros usuários no mesmo sistema.

Computer Configuration\Policies\Administrative Templates\Windows Components\App Package Deployment\Allow a Windows app to share application data between users

<img width="1263" height="840" alt="image" src="https://github.com/user-attachments/assets/0759c0fb-8d9c-4fd6-be33-0d4a61e36237" />

Garanta que 'Not allow per-user unsigned packages to install by default (requires explicitly allow per install)' esteja atribuido como 'Enabled' 

Essa configuração controla a capacidade do usuário de instalar pacotes de aplicativos do Windows não assinados.

O estado recomendado para essa configuração é: Ativado.

Observação: Pacotes de aplicativos do Windows não assinados exigirão uma permissão explícita para cada instalação se essa configuração estiver desativada.

Em um ambiente corporativo gerenciado, as instalações de aplicativos devem ser gerenciadas centralmente pela equipe de TI, e não pelos usuários finais.

Computer Configuration\Policies\Administrative Templates\Windows Components\App Package Deployment\Not allow per-user unsigned packages to install by default (requires explicitly allow per install)

<img width="1263" height="842" alt="image" src="https://github.com/user-attachments/assets/05e0dc0f-7bf3-4961-a8b0-8d9d52b09f47" />

Garanta que 'Prevent non-admin users from installing packaged Windows apps' esteja atribuido como 'Enabled'

Essa configuração controla a capacidade de usuários sem privilégios de administrador instalarem pacotes de aplicativos do Windows.

O estado recomendado para essa configuração é: Ativado.

Em um ambiente corporativo gerenciado, as instalações de aplicativos devem ser gerenciadas centralmente pela equipe de TI, e não pelos usuários finais.

Computer Configuration\Policies\Administrative Templates\Windows Components\App Package Deployment\Prevent non-admin users from installing packaged Windows apps

<img width="1262" height="847" alt="image" src="https://github.com/user-attachments/assets/a5b876d3-93aa-469b-9057-64c49186477d" />

Salve este post como parte do seu checklist de hardening Windows.
