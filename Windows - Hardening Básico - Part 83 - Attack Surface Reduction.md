<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/012a1ac3-c942-46df-a2bb-0836c7ba0a1e" />

# Windows - Hardening Básico - Part 83 - Attack Surface Reduction

Garanta que 'Configure Attack Surface Reduction rules' esteja atribuido como 'Enabled'

Essa configuração de política controla o estado das regras de Redução da Superfície de Ataque (ASR).

O estado recomendado para essa configuração é: Ativado.

A redução da superfície de ataque ajuda a impedir ações e aplicativos normalmente usados por malwares que buscam vulnerabilidades para infectar máquinas.

Computer Configuration\Policies\Administrative Templates\Windows Components\Microsoft Defender Antivirus\Microsoft Defender Exploit Guard\Attack Surface Reduction\Configure Attack Surface Reduction rules

<img width="1356" height="837" alt="image" src="https://github.com/user-attachments/assets/ff312d28-512a-429d-a97d-a0ced49049e7" />

Garanta que 'Configure Attack Surface Reduction rules: Set the state for each ASR rule' esteja atribuido como - valores abaixo:

Esta configuração de política define as regras de Redução da Superfície de Ataque.

O estado recomendado para esta configuração é:

26190899-1602-49e8-8b27-eb1d0a1ce869 - 1 (Block Office communication application from creating child processes)

3b576869-a4ec-4529-8536-b80a7769e899 - 1 (Block Office applications from creating executable content)

56a863a9-875e-4185-98a7-b882c64b5ce5 - 1 (Block abuse of exploited vulnerable signed drivers)

5beb7efe-fd9a-4556-801d-275e5ffc04cc - 1 (Block execution of potentially obfuscated scripts)

75668c1f-73b5-4cf0-bb93-3ecf5cb7cc84 - 1 (Block Office applications from injecting code into other processes)

7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c - 1 (Block Adobe Reader from creating child processes)

92e97fa1-2edf-4476-bdd6-9dd0b4dddc7b - 1 (Block Win32 API calls from Office macro)

9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2 - 1 (Block credential stealing from the Windows local security authority subsystem (lsass.exe))

b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4 - 1 (Block untrusted and unsigned processes that run from USB)

be9ba2d9-53ea-4cdc-84e5-9b1eeee46550 - 1 (Block executable content from email client and webmail)

d3e037e1-3eb8-44c8-a917-57927947596d - 1 (Block JavaScript or VBScript from launching downloaded executable content)

d4f940ab-401b-4efc-aadc-ad5f3c50688a - 1 (Block Office applications from creating child processes)

e6db77e5-3df2-4cf1-b95a-636979351e5b - 1 (Block persistence through WMI event subscription)

Computer Configuration\Policies\Administrative Templates\Windows Components\Microsoft Defender Antivirus\Microsoft Defender Exploit Guard\Attack Surface Reduction\Configure Attack Surface Reduction rules: Set the state for each ASR rule

<img width="1436" height="842" alt="image" src="https://github.com/user-attachments/assets/e52a1f24-41da-4248-9da3-266ba3824dcc" />

Salve este post como parte do seu checklist de hardening Windows.
