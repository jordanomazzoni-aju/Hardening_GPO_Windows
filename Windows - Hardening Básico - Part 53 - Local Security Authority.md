<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/e583d27d-00dc-4c49-8fed-6b3e6439a945" />


# Windows - Hardening Básico - Part 53 - Local Security Authority

Garanta que 'Allow Custom SSPs and APs to be loaded into LSASS' esteja atribuido como 'Disabled'

Esta configuração de política controla a configuração sob a qual o Serviço de Subsistema de Autoridade de Segurança Local (LSASS) carregará o Provedor de Suporte de Segurança/Pacote de Autenticação (SSP/AP) personalizado.

O estado recomendado para esta configuração é: Desativado.

Existem vulnerabilidades em que agentes maliciosos podem interceptar credenciais de login por meio de SSP/AP. Desativar o carregamento de SSPs e APs personalizados no LSASS minimiza essa vulnerabilidade.

Computer Configuration\Policies\Administrative Templates\System\Local Security Authority\Allow Custom SSPs and APs to be loaded into LSASS

<img width="1264" height="836" alt="image" src="https://github.com/user-attachments/assets/807dcfdb-d364-4236-8264-e6a087f6ff4a" />

Garanta que 'Configures LSASS to run as a protected process' esteja atribuido como 'Enabled: Enabled with UEFI Lock'

Essa configuração de política controla se o Serviço de Subserviço de Autoridade de Segurança Local (LSASS) é executado em modo protegido e também oferece a opção de bloqueio em modo protegido com a Interface de Firmware Extensível Unificada (UEFI). A Autoridade de Segurança Local (LSA), que inclui o processo LSASS, valida usuários para logins locais e remotos e aplica políticas de segurança locais.

O estado recomendado para essa configuração é: Ativado: Ativado com Bloqueio UEFI.

Fornece segurança adicional para as credenciais que a LSA armazena e gerencia. Habilitar essa configuração com Bloqueio UEFI impede que ela seja alterada remotamente.

Computer Configuration\Policies\Administrative Templates\System\Local Security Authority\Configures LSASS to run as a protected process

<img width="1264" height="850" alt="image" src="https://github.com/user-attachments/assets/1574613c-cb62-45bf-8412-ead2333ec77b" />

Salve este post como parte do seu checklist de hardening Windows.
