<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/5263cd4e-cad5-4103-8ba7-60f55f6b4c02" />


# Windows - Hardening Básico - Part 75 - Widgets - Recall

Garanta que 'Allow widgets' esteja atribuido como 'Disabled'

Esta configuração de política especifica se o recurso Widgets é permitido no dispositivo. O recurso Widgets fornece informações como previsão do tempo, notícias, esportes, ações, trânsito e entretenimento (lista não exaustiva).

O estado recomendado para esta configuração é: Desativado.

Os dados nunca devem ser compartilhados com terceiros sem consentimento explícito, pois podem conter informações confidenciais. Devido a preocupações com a privacidade, aplicativos e recursos como Widgets na barra de tarefas do Windows devem ser tratados como um possível risco de segurança.

Computer Configuration\Policies\Administrative Templates\Windows Components\Widgets\Allow widgets

<img width="1264" height="835" alt="image" src="https://github.com/user-attachments/assets/d836165a-90ca-48de-ae1e-a9894da4f1cb" />

Garanta que 'Allow Recall to be enabled' esteja atribuido como 'Disabled'

Essa configuração de política controla se o componente opcional Recall está disponível para os usuários finais habilitarem no sistema. O Microsoft Recall captura periodicamente capturas de tela do sistema, criando uma linha do tempo pesquisável de atividades, incluindo aplicativos, documentos e sites.

O estado recomendado para essa configuração é: Desativado.

Salvar instantâneos de toda a atividade do usuário pode resultar no armazenamento inseguro de informações confidenciais, como senhas ou dados bancários, tornando-as facilmente acessíveis.

Computer Configuration\Policies\Administrative Templates\Windows Components\Windows AI\Allow Recall to be enabled

<img width="1264" height="840" alt="image" src="https://github.com/user-attachments/assets/29d6e35b-175f-4500-a7ac-f6ee9b974605" />

Salve este post como parte do seu checklist de hardening Windows.
