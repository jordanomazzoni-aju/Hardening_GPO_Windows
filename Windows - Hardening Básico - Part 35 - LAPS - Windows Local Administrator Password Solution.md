<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/1c3c6050-bed7-4e85-a7ae-9b29bdc24ca5" />


# Windows - Hardening Básico - Part 35 - LAPS - Windows Local Administrator Password Solution

Esta seção contém recomendações para as configurações da Solução de Senha de Administrador Local do Windows (LAPS).

O LAPS é uma solução de segurança que automatiza o gerenciamento de senhas de contas de administrador local em dispositivos ingressados no Active Directory. 

Em vez de uma senha única e imutável, o LAPS garante que:

Cada máquina tenha uma senha exclusiva eliminando o risco de ataques pass-the-hash e movimentação lateral.
As senhas sejam complexas e randômicas removendo o fator humano e a previsibilidade.
A rotação seja automática, as senhas expiram e são trocadas periodicamente sem intervenção manual.
O armazenamento seja seguro, credenciais são criptografadas e armazenadas nos atributos do próprio diretório (AD ou Entra ID), onde o acesso pode ser rigorosamente auditado e controlado via RBAC (Controle de Acesso Baseado em Função).

a implementação do LAPS não é apenas uma melhoria técnica, mas uma contramedida fundamental. Ao adotar o LAPS (especialmente a nova versão integrada nativamente ao Windows), você remove o oxigênio de um atacante após a brecha inicial.

Se um endpoint for comprometido, o impacto é isolado. O custo de oportunidade para o adversário sobe drasticamente, enquanto sua equipe de TI ganha visibilidade e controle sobre quem, quando e por que alguém solicitou acesso a uma conta administrativa local.



Garanta que 'Configure password backup directory' esteja atribuido como 'Enabled: Active Directory' or 'Enabled: Azure Active Directory'
Esta configuração de política define qual diretório o Windows LAPS usará para fazer backup da senha da conta de administrador local.

Organizações que utilizam software comercial de terceiros para gerenciar senhas de administrador local exclusivas e complexas em membros do domínio podem optar por ignorar estas recomendações do LAPS.

O Windows LAPS não oferece suporte a computadores autônomos; eles devem estar associados a um domínio do Active Directory ou Entra ID (anteriormente Azure Active Directory).

O Windows LAPS não oferece suporte ao armazenamento simultâneo da senha de administrador local em ambos os tipos de diretório.

Se a configuração estiver definida e o dispositivo gerenciado não estiver associado ao tipo de diretório configurado, a senha do administrador local não será gerenciada pelo Windows LAPS.

Computer Configuration\Policies\Administrative Templates\System\LAPS\Configure password backup directory



Garanta que 'Do not allow password expiration time longer than required by policy' esteja atribuido como 'Enabled'
Esta configuração de política define se a idade da senha, determinada pela política "Configurações de Senha" do Windows LAPS, é aplicada e não pode ser estendida manualmente (apenas encurtada) por um técnico autorizado.

Se uma expiração for detectada, a senha será alterada imediatamente e a expiração da senha será definida de acordo com a política.

Organizações que utilizam software comercial de terceiros para gerenciar senhas de Administrador local exclusivas e complexas em membros do domínio podem optar por ignorar estas recomendações do LAPS.

O Windows LAPS não oferece suporte a computadores autônomos; eles devem estar associados a um domínio do Active Directory ou Entra ID (anteriormente Azure Active Directory).

Computer Configuration\Policies\Administrative Templates\System\LAPS\Do not allow password expiration time longer than required by policy



Garanta que 'Enable password encryption' esteja atribuido como 'Enabled'
Esta configuração de política controla se a senha gerenciada pelo Windows LAPS é criptografada antes de ser enviada ao Active Directory.

Organizações que utilizam software comercial de terceiros para gerenciar senhas de administrador locais exclusivas e complexas em membros do domínio podem optar por ignorar estas recomendações do LAPS.

O Windows LAPS não oferece suporte a computadores autônomos; eles devem estar associados a um domínio do Active Directory ou ao Entra ID (anteriormente Azure Active Directory).

Esta configuração não tem efeito a menos que a senha tenha sido configurada para ser copiada para o Active Directory e o nível funcional do domínio do Active Directory seja Windows Server 2016 ou superior.

Esta configuração não tem relevância (mas é inofensiva) ao armazenar senhas do Windows LAPS no Entra ID (anteriormente Azure Active Directory), pois ele criptografa automaticamente todas as senhas do Windows LAPS.

Computer Configuration\Policies\Administrative Templates\System\LAPS\Enable password encryption

Se o nível funcional do domínio estiver definido como Windows Server 2016 ou superior, a senha da conta gerenciada do Windows LAPS será criptografada automaticamente; se estiver definido em um nível funcional de domínio inferior, a senha da conta gerenciada do Windows LAPS não será copiada para o diretório.



Garanta que 'Password Settings: Password Complexity' esteja atribuido como 'Enabled: Large letters + small letters + numbers + special characters' or 'Passphrase'
O estado recomendado para esta configuração é: Ativado: Letras maiúsculas + letras minúsculas + números + caracteres especiais. Configurar esta opção para Frase secreta (palavras longas), Frase secreta (palavras curtas) ou Frase secreta (palavras curtas com prefixos exclusivos) também está em conformidade com o padrão.

A lista de frases secretas é gerada a partir do documento "Deep Dive: EFF's New Wordlists for Random Passphrases" da Electronic Frontier Foundation e suporta apenas o idioma inglês.

Organizações que utilizam software comercial de terceiros para gerenciar senhas de administrador local exclusivas e complexas em membros do domínio podem optar por ignorar estas recomendações do LAPS.

O Windows LAPS não é compatível com computadores autônomos; eles devem estar associados a um domínio do Active Directory ou Entra ID (anteriormente Azure Active Directory).

Para configurar a opção recomendada via Política de Grupo, defina o seguinte caminho da interface do usuário como Ativado e configure a opção Complexidade da Senha como Letras maiúsculas + letras minúsculas + números + caracteres especiais, Frase secreta (palavras longas), Frase secreta (palavras curtas) ou Frase secreta (palavras curtas com prefixos exclusivos):

Computer Configuration\Policies\Administrative Templates\System\LAPS\Password Settings



Garanta que 'Password Settings: Password Length' esteja atribuido como 'Enabled: 15 or more'
 Esta configuração de política define a política de Configurações de Senha do Windows LAPS para o comprimento da senha.

Organizações que utilizam software comercial de terceiros para gerenciar senhas de Administrador local exclusivas e complexas em membros do domínio podem optar por ignorar estas recomendações do LAPS.

Elas devem estar associadas a um domínio do Active Directory ou Entra ID (anteriormente Azure Active Directory).

Computer Configuration\Policies\Administrative Templates\System\LAPS\Password Settings



Garanta que 'Password Settings: Password Age (Days)' esteja atribuido como 'Enabled: 30 or fewer'
Esta configuração de política define a política de Configurações de Senha do Windows LAPS para a idade da senha.

Organizações que utilizam software comercial de terceiros para gerenciar senhas de Administrador local exclusivas e complexas em membros do domínio podem optar por ignorar estas recomendações do LAPS.

O Windows LAPS não oferece suporte a computadores autônomos; eles devem estar associados a um domínio do Active Directory ou Entra ID (anteriormente Azure Active Directory).

Computer Configuration\Policies\Administrative Templates\System\LAPS\Password Settings



Garanta que 'Post-authentication actions: Grace period (hours)' esteja atribuido como 'Enabled: 8 or fewer hours, but not 0'
Esta configuração de política define as ações pós-autenticação que serão executadas após a detecção de uma autenticação pela conta gerenciada pelo Windows LAPS. O período de tolerância refere-se ao tempo (em horas) de espera após a autenticação antes da execução das ações pós-autenticação especificadas.

Organizações que utilizam software comercial de terceiros para gerenciar senhas de administrador local exclusivas e complexas em membros do domínio podem optar por ignorar estas recomendações do LAPS.

O Windows LAPS não oferece suporte a computadores autônomos; eles devem estar associados a um domínio do Active Directory ou Entra ID (anteriormente Azure Active Directory).

Se esta política estiver definida como 0, ela impede a execução de todas as ações pós-autenticação.

Computer Configuration\Policies\Administrative Templates\System\LAPS\Post-authentication actions: Grace period (hours)





Garanta que 'Post-authentication actions: Actions' esteja atribuido como'Enabled: Reset the password and logoff the managed account' or higher
Esta configuração de política define as ações pós-autenticação que serão executadas após a detecção de uma autenticação pela conta gerenciada do LAPS. A ação refere-se às ações a serem tomadas após o término do período de tolerância, antes da execução das ações pós-autenticação especificadas.

Ações pós-autenticação:

Redefinir senha: após o término do período de tolerância, a senha da conta gerenciada será redefinida.

Redefinir senha e encerrar sessão da conta gerenciada: após o término do período de tolerância, a senha da conta gerenciada será redefinida e quaisquer sessões de login interativas usando a conta gerenciada serão encerradas.

Redefinir senha e reiniciar o dispositivo: após o término do período de tolerância, a senha da conta gerenciada será redefinida e o dispositivo gerenciado será reiniciado imediatamente.

Redefinir senha, encerrar sessão da conta gerenciada e encerrar quaisquer processos restantes: após o término do período de tolerância, a senha da conta gerenciada será redefinida, quaisquer sessões de login interativas usando a conta gerenciada serão encerradas e quaisquer processos restantes serão finalizados.

O estado recomendado para esta configuração é: Ativado: Redefinir a senha e encerrar a sessão da conta gerenciada. Configurar esta opção para Redefinir a senha e reiniciar o dispositivo ou Redefinir a senha, encerrar a sessão da conta gerenciada e finalizar quaisquer processos restantes também está em conformidade com o padrão de referência.

Computer Configuration\Policies\Administrative Templates\System\LAPS\Post-authentication actions: Actions



Resumo das configurações:

<img width="1253" height="821" alt="image" src="https://github.com/user-attachments/assets/2e4b9392-ed44-491a-90d9-7750cfdba208" />

<img width="570" height="237" alt="image" src="https://github.com/user-attachments/assets/c74c0abc-2a72-44cd-b8bd-910a4456830d" />

<img width="1139" height="748" alt="image" src="https://github.com/user-attachments/assets/83ccb069-ce69-4c69-9f0b-2d6c5aec5414" />

<img width="1111" height="764" alt="image" src="https://github.com/user-attachments/assets/09f233b8-d20d-4de9-ab8f-26237f8782b0" />

<img width="1155" height="774" alt="image" src="https://github.com/user-attachments/assets/b124843e-09ec-46a3-90d2-0a4ba719dd05" />

<img width="1133" height="737" alt="image" src="https://github.com/user-attachments/assets/a84cde3b-cebf-402f-86af-ef659f932b79" />

<img width="481" height="556" alt="image" src="https://github.com/user-attachments/assets/4a9cc3af-4780-42e1-90b2-5f8778bb16a2" />

<img width="782" height="572" alt="image" src="https://github.com/user-attachments/assets/fd17dad0-0637-4595-93aa-e070b913a932" />

<img width="778" height="653" alt="image" src="https://github.com/user-attachments/assets/09dba454-5fac-439e-9b6c-d83badcaf9b9" />

Devido à dificuldade em gerenciar senhas de Administrador local, muitas organizações optam por usar a mesma senha em todas as estações de trabalho e/ou Servidores Membros ao implantá-los. Isso cria um sério risco de segurança na superfície de ataque, pois se um invasor conseguir comprometer um sistema e descobrir a senha da conta de Administrador local, poderá usar essa conta para obter acesso instantâneo a todos os outros computadores que também usam essa senha para sua conta de Administrador local. O mesmo ocorre na mudança ou saída de membros da equipe. 

Salve este post como parte do seu checklist de hardening Windows.
