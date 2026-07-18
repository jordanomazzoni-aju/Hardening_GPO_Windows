<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/b6966c0c-7615-4696-b373-5854aeb16164" />


# Windows - Hardening Básico - Part 32 - anonymous enumeration - storage of passwords and credentials

Garanta que 'Network access: Do not allow anonymous enumeration of SAM accounts and shares' esteja atribuido como 'Enabled'

Essa configuração de política controla a capacidade de usuários anônimos enumerarem contas SAM, bem como compartilhamentos. Se você habilitar essa configuração de política, usuários anônimos não poderão enumerar nomes de usuários de contas de domínio e nomes de compartilhamentos de rede nos sistemas do seu ambiente.

Um usuário não autorizado poderia listar anonimamente nomes de contas e recursos compartilhados e usar as informações para tentar adivinhar senhas ou realizar ataques de engenharia social. (Ataques de engenharia social tentam enganar os usuários de alguma forma para obter senhas ou algum tipo de informação de segurança.)

Computer Configuration\Policies\Windows Settings\Security Settings\Local Policies\Security Options\Network access: Do not allow anonymous enumeration of SAM accounts and shares

Garanta que 'Network access: Do not allow storage of passwords and credentials for network authentication' esteja atribuido como 'Enabled'

Essa configuração de política determina se o Gerenciador de Credenciais salva senhas ou credenciais para uso posterior, quando obtiver autenticação de domínio.

As senhas armazenadas em cache podem ser acessadas pelo usuário ao fazer login no computador. Embora essa informação possa parecer óbvia, um problema pode surgir se o usuário, sem saber, executar um código malicioso que leia as senhas e as encaminhe para outro usuário não autorizado.

Computer Configuration\Policies\Windows Settings\Security Settings\Local Policies\Security Options\Network access: Do not allow storage of passwords and credentials for network authentication

<img width="1072" height="706" alt="image" src="https://github.com/user-attachments/assets/f9c5a86c-7f77-4292-bd67-20ff69b30176" />

<img width="1105" height="734" alt="image" src="https://github.com/user-attachments/assets/b4ea7ce3-d436-4efe-a000-87d4e10dc640" />

Mesmo que você habilite a diretiva "Do not allow anonymous enumeration of SAM accounts", o Windows ainda pode permitir a enumeração de compartilhamentos (shares) se a diretiva "Network access: Restrict anonymous access to Named Pipes and Shares" não estiver configurada em conjunto.

Adote sempre um conjunto de configurações e teste sempre os controles. As configurações podem variar para cada versão de Windows e por isso devemos sempre homologar e atualizar cada configuração para a versão específica.
