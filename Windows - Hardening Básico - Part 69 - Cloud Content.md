<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/84430fad-62dc-457e-8824-87bd3c1b13bd" />


# Windows - Hardening Básico - Part 69 - Cloud Content

Garanta que 'Turn off cloud consumer account state content' esteja atribuido como 'Enabled'

Essa configuração de política determina se o conteúdo do estado da conta do consumidor na nuvem é permitido em todas as experiências do Windows.

O estado recomendado para esta configuração é: Ativado.

A utilização de contas pessoais num ambiente gerido por empresas não é uma boa prática de segurança, pois pode levar a uma possível fuga de dados.

Computer Configuration\Policies\Administrative Templates\Windows Components\Cloud Content\Turn off cloud consumer account state content

<img width="1262" height="848" alt="image" src="https://github.com/user-attachments/assets/f884c29e-9d48-4d8d-8d11-1c28c5770201" />

Garanta que 'Turn off cloud optimized content' esteja atribuido como'Enabled'

Essa configuração de política desativa o conteúdo otimizado para nuvem em todas as experiências do Windows.

O estado recomendado para esta configuração é: Ativado.

Em ambientes de alta segurança, os dados nunca devem ser partilhados com terceiros sem consentimento explícito, pois podem conter informações sensíveis.

Computer Configuration\Policies\Administrative Templates\Windows Components\Cloud Content\Turn off cloud optimized content

<img width="1263" height="841" alt="image" src="https://github.com/user-attachments/assets/24bb5caa-e25e-4702-bd4f-b3286dab21a6" />

Garanta que 'Turn off Microsoft consumer experiences' esteja atribuido como 'Enabled'

Esta configuração de política desativa experiências que ajudam os consumidores a aproveitar ao máximo seus dispositivos e conta da Microsoft.

O estado recomendado para esta configuração é: Ativado.

Instalar aplicativos silenciosamente em um ambiente gerenciado pela empresa não é uma boa prática de segurança, especialmente se os aplicativos enviarem dados de volta a terceiros.

Computer Configuration\Policies\Administrative Templates\Windows Components\Cloud Content\Turn off Microsoft consumer experiences

<img width="1266" height="839" alt="image" src="https://github.com/user-attachments/assets/9544a986-7288-41f2-9a9a-1eb2fdfd2ce6" />

Garanta que 'Require pin for pairing' esteja atribuido como 'Enabled: First Time' ou 'Enabled: Always'

Esta configuração de política controla se um PIN é necessário ou não para emparelhar um dispositivo de exibição sem fio.

O estado recomendado para esta configuração é: Ativado: Primeira vez OU Ativado: Sempre .

Se esta configuração não estiver configurada ou desabilitada, um PIN não será necessário ao emparelhar dispositivos de exibição sem fio com o sistema, aumentando o risco de uso não autorizado.

Computer Configuration\Policies\Administrative Templates\Windows Components\Connect\Require pin for pairing

<img width="1264" height="845" alt="image" src="https://github.com/user-attachments/assets/50a3958b-ab38-4fd7-a0ff-e03d6c01bbf6" />

Salve este post como parte do seu checklist de hardening Windows.
