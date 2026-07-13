<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/68544607-635a-4438-960a-21817ab0690d" />


# Windows - Hardening Básico - Part 84 - Brute-Force Protection

Garanta que 'Configure Brute-Force Protection aggressiveness' esteja atribuido como 'Enabled: Medium' or higher

Esta configuração de política define se a Proteção contra Ataques de Força Bruta no Microsoft Defender Antivírus está habilitada. A proteção contra ataques de força bruta pode detectar e bloquear tentativas de acesso forçado a um sistema.

O estado recomendado para esta configuração é: Habilitado: Médio. Configurar esta opção como Habilitado: Alto também está em conformidade com o padrão de referência.

Este recurso pode ajudar a reduzir a probabilidade de um ataque de força bruta bem-sucedido.

Para estabelecer a configuração recomendada via Política de Grupo, defina o seguinte caminho da interface do usuário como Habilitado: Médio ou Habilitado: Alto:

Computer Configuration\Policies\Administrative Templates\Windows Components\Microsoft Defender Antivirus\Remediation\Behavioral Network Blocks\Brute-Force Protection\Configure Brute-Force Protection aggressiveness

<img width="1446" height="826" alt="image" src="https://github.com/user-attachments/assets/c41defda-c035-4661-b474-4b753863a62b" />

Garanta que 'Configure Remote Encryption Protection Mode' esteja atribuido como 'Enabled: Audit' or higher

Esta configuração de política configura o recurso de Proteção contra Ataques de Força Bruta no Microsoft Defender Antivírus. A Proteção contra Ataques de Força Bruta pode detectar e bloquear tentativas de iniciar logins e sessões à força.

O estado recomendado para esta configuração é: Ativado: Auditoria. Configurar esta opção como Ativado: Bloqueio também está em conformidade com o benchmark.

Este recurso ajuda a mitigar tentativas de força bruta, detectando e bloqueando logins e sessões não autorizados.

Para estabelecer a configuração recomendada via Política de Grupo, defina o seguinte caminho da interface do usuário como Ativado: Auditoria ou Ativado: Bloqueio:

Computer Configuration\Policies\Administrative Templates\Windows Components\Microsoft Defender Antivirus\Remediation\Behavioral Network Blocks\Brute-Force Protection\Configure Remote Encryption Protection Mode

<img width="1444" height="850" alt="image" src="https://github.com/user-attachments/assets/4c81469f-d42e-49a7-bfd4-574a390da062" />

Salve este post como parte do seu checklist de hardening Windows.
