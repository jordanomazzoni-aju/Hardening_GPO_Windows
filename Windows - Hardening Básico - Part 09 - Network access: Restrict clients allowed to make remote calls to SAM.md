<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/1a677645-95d8-4009-b278-7ce35467da49" />


# Windows - Hardening Básico - Part 09 - Network access: Restrict clients allowed to make remote calls to SAM

O SAM (Security Account Manager) do Windows armazena hashes de senhas. Permitir chamadas remotas não autorizadas abre caminho para enumeração de contas e ataques de movimentação lateral. Neste guia, mostro como restringir via GPO, tarefa essencial para hardening em ambientes corporativos

Para garantir que um usuário não autorizado não possa listar anonimamente nomes de contas ou grupos locais e usar as informações para tentar adivinhar senhas ou realizar ataques de engenharia social. (Ataques de engenharia social tentam enganar os usuários de alguma forma para obter senhas ou algum tipo de informação de segurança.)

Essa configuração de política permite restringir conexões RPC remotas ao SAM.

O estado recomendado para essa configuração é: Administradores: Acesso Remoto: Permitir.

Para garantir que um usuário não autorizado não possa listar anonimamente nomes de contas ou grupos locais e usar as informações para tentar adivinhar senhas ou realizar ataques de engenharia social. (Ataques de engenharia social tentam enganar os usuários de alguma forma para obter senhas ou algum tipo de informação de segurança.)

Configure o valor da política para:

Computer Configuration\Policies\Windows Settings\Security Settings\Local Policies\Security Options\Network access: Restrict clients allowed to make remote calls to SAM
Selecione "Editar Segurança" para configurar o "Descritor de segurança:".
Adicione "Administradores" em "Nomes de grupos ou usuários:" se ainda não estiver listado (este é o padrão).
Selecione "Administradores" em "Nomes de grupos ou usuários:".
Selecione "Permitir" para "Acesso Remoto" em "Permissões para "Administradores".
Clique em "OK".
O "Descritor de segurança:" deve ser preenchido com "O:BAG:BAD:(A;;RC;;;BA)" para que a política seja aplicada.

<img width="1120" height="867" alt="image" src="https://github.com/user-attachments/assets/72cfe3ec-5e8c-4c94-87e0-8deac2334ed8" />

Salve este post como parte do seu checklist de hardening Windows."

Na empresa que você trabalha, esta configuração está habilitada ? Como você mitiga, monitora ou realiza a detecção de movimentação lateral entre os Desktops ?
