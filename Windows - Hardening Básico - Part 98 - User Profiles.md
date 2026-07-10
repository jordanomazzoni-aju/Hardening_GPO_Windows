# Windows - Hardening Básico - Part 98 - User Profiles

Garanta que 'Turn off the advertising ID' esteja atribuido como 'Enabled'

Essa configuração de política desativa o ID de publicidade, impedindo que os apps usem o ID para experiências entre apps.

O estado recomendado para essa configuração é: Ativado.

Em ambientes de alta segurança, os dados nunca devem ser compartilhados com terceiros sem consentimento explícito, pois podem conter informações confidenciais. Além disso, o rastreamento da atividade do usuário para fins publicitários, mesmo que anonimamente, pode representar um risco à privacidade.

Para estabelecer a configuração recomendada via Política de Grupo, defina o seguinte caminho da interface do usuário como Ativado:

`- Computer Configuration\Policies\Administrative Templates\System\User Profiles\Turn off the advertising ID`

![Conteúdo do artigo](https://media.licdn.com/dms/image/v2/D4D12AQH_iX838nunJA/article-inline_image-shrink_1000_1488/B4DZ4uM5rxKAAM-/0/1778891594875?e=1785369600&v=beta&t=hrMnBJNNxKMgXpmQm0TXErYRyWo7DecMoBkB6dLAOuo)

Garanta que 'Disallow copying of user input methods to the system account for sign-in' esteja atribuido como 'Enabled'

Esta política impede a cópia automática dos métodos de entrada do usuário para a conta do sistema para uso na tela de login. O usuário fica restrito ao conjunto de métodos de entrada habilitados na conta do sistema.

O estado recomendado para esta configuração é: Habilitado.

Esta é uma forma de aumentar a segurança da conta do sistema.

Para estabelecer a configuração recomendada via Política de Grupo, defina o seguinte caminho da interface do usuário como Habilitado:

`- Computer Configuration\Policies\Administrative Templates\System\Locale Services\Disallow copying of user input methods to the system account for sign-in`

![Conteúdo do artigo](https://media.licdn.com/dms/image/v2/D4D12AQH-aEpbqcQIAg/article-inline_image-shrink_1000_1488/B4DZ4uM2u.HMAQ-/0/1778891582749?e=1785369600&v=beta&t=u41suY9STkS0yYO-LTrspR-wh-aZp9Jj-Z5y4YtdMQk)

Salve este post como parte do seu checklist de hardening Windows.
