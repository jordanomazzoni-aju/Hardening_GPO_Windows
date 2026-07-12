<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/6fd75421-6f87-40b1-acb8-075ce292af43" />

# Windows - Hardening Básico - Part 89 - Handwriting personalization

Garanta que 'Allow users to enable online speech recognition services' esteja atribuido como 'Disabled' 

Esta política permite o componente de aprendizagem automática de personalização de entrada que inclui fala, escrita à tinta e digitação. O aprendizado automático permite a coleta de padrões de fala e escrita, histórico de digitação, contatos e informações recentes do calendário. É necessário para o uso da Cortana. Algumas dessas informações coletadas poderão ser armazenadas no OneDrive do usuário, no caso de escrita à tinta e digitação; algumas das informações serão carregadas na Microsoft para personalizar a fala.

O estado recomendado para esta configuração é: Disabled .

Se esta configuração estiver Habilitada, informações confidenciais poderão ser armazenadas na nuvem ou enviadas para a Microsoft.

Para estabelecer a configuração recomendada via GP, defina o seguinte caminho da UI como Disabled :

Computer Configuration\Policies\Administrative Templates\Control Panel\Regional and Language Options\Allow users to enable online speech recognition services

<img width="1440" height="850" alt="image" src="https://github.com/user-attachments/assets/7b858e26-881b-422d-b641-4dfa0f7707ce" />

Garanta que 'Allow Online Tips' esteja atribuido como 'Disabled'

Esta configuração de política configura a recuperação de dicas e ajuda on-line para o aplicativo Configurações.

O estado recomendado para esta configuração é: Disabled .

Em ambientes de alta segurança, os dados nunca devem ser partilhados com terceiros sem consentimento explícito, pois podem conter informações sensíveis.

Para estabelecer a configuração recomendada via GP, defina o seguinte caminho da UI como Disabled :

Computer Configuration\Policies\Administrative Templates\Control Panel\Allow Online Tips

<img width="1445" height="852" alt="image" src="https://github.com/user-attachments/assets/8bed5ebf-3e63-416f-85d7-0a8f0e813cc6" />

Salve este post como parte do seu checklist de hardening Windows.
