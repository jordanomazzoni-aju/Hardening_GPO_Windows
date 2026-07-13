<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/71582e22-059f-45ef-8432-41de83038459" />

# Windows - Hardening Básico - Part 82 - Printers - part05

Garanta que 'Require IPPS for IPP printers' esteja atribuido como 'Enabled'

Essa configuração de política determina se a comunicação com impressoras que usam o driver de classe do Protocolo de Impressão na Internet (IPP) da Microsoft utiliza o IPPS. O IPPS usa TLS para comunicação segura.

O estado recomendado para essa configuração é: Ativado.

Para evitar a interceptação ou adulteração dos dados da impressora, o IPPS criptografa toda a comunicação entre o cliente e a impressora.

Para estabelecer a configuração recomendada via Política de Grupo, defina o seguinte caminho da interface do usuário como Ativado.

Computer Configuration\Policies\Administrative Templates\Printers\Require IPPS for IPP printers

<img width="1411" height="678" alt="image" src="https://github.com/user-attachments/assets/43f6ad2e-8843-4af1-bf51-6b525f9068d4" />

Garanta que 'Set TLS/SSL security policy for IPP printers: Disallow invalid certificate authority' esteja atribuido como 'Enabled: Checked'

Essa configuração de política determina a política de segurança TLS/SSL (WINHTTP_OPTION_SECURITY_FLAGS) para impressoras que usam o driver de classe do Protocolo de Impressão na Internet (IPP) da Microsoft.

O estado recomendado para essa configuração é: Ativado: Marcado.

A validação de certificado ajuda a evitar impressoras falsificadas ou não autorizadas, reduz o risco de roubo de credenciais e protege trabalhos de impressão confidenciais contra redirecionamento.

Para estabelecer a configuração recomendada via Política de Grupo, defina o seguinte caminho da interface do usuário como Ativado: Marcado.

Computer Configuration\Policies\Administrative Templates\Printers\Set TLS/SSL security policy for IPP printers: Disallow invalid certificate authority

<img width="1440" height="711" alt="image" src="https://github.com/user-attachments/assets/4c45dce8-88b8-4d5d-9658-77be2455c67d" />

Garanta que 'Set TLS/SSL security policy for IPP printers: Disallow non-server certificates' esteja atribuido como 'Enabled: Checked'

Essa configuração de política determina a política de segurança TLS/SSL (WINHTTP_OPTION_SECURITY_FLAGS) para impressoras que usam o driver de classe do Protocolo de Impressão na Internet (IPP) da Microsoft.

O estado recomendado para essa configuração é: Ativado: Marcado.

A validação de certificado ajuda a evitar impressoras falsificadas ou não autorizadas, reduz o risco de roubo de credenciais e protege trabalhos de impressão confidenciais contra redirecionamento.

Para estabelecer a configuração recomendada via Política de Grupo, defina o seguinte caminho da interface do usuário como Ativado: Marcado.

Computer Configuration\Policies\Administrative Templates\Printers\Set TLS/SSL security policy for IPP printers: Disallow non-server certificates

<img width="1440" height="711" alt="image" src="https://github.com/user-attachments/assets/51cdc1b3-d2ee-44cf-bbbf-243478da1cdb" />

Garanta que 'Set TLS/SSL security policy for IPP printers: Disallow invalid certificate common name' esteja atribuido como 'Enabled: Checked'

Essa configuração de política determina a política de segurança TLS/SSL (WINHTTP_OPTION_SECURITY_FLAGS) para impressoras que usam o driver de classe do Protocolo de Impressão na Internet (IPP) da Microsoft.

O estado recomendado para essa configuração é: Ativado: Marcado.

A validação de certificado ajuda a evitar impressoras falsificadas ou não autorizadas, reduz o risco de roubo de credenciais e protege trabalhos de impressão confidenciais contra redirecionamento.

Para estabelecer a configuração recomendada via Política de Grupo, defina o seguinte caminho da interface do usuário como Ativado: Marcado.

Computer Configuration\Policies\Administrative Templates\Printers\Set TLS/SSL security policy for IPP printers: Disallow invalid certificate common name

<img width="1440" height="711" alt="image" src="https://github.com/user-attachments/assets/58350eff-6096-4d4e-8c58-f37a83edd2c4" />

Garanta que 'Set TLS/SSL security policy for IPP printers: Disallow invalid certificate date' esteja atribuido como 'Enabled: Checked'

Essa configuração de política determina a política de segurança TLS/SSL (WINHTTP_OPTION_SECURITY_FLAGS) para impressoras que usam o driver de classe do Protocolo de Impressão na Internet (IPP) da Microsoft.

O estado recomendado para essa configuração é: Ativado: Marcado.

A validação de certificado ajuda a evitar impressoras falsificadas ou não autorizadas, reduz o risco de roubo de credenciais e protege trabalhos de impressão confidenciais contra redirecionamento.

Para estabelecer a configuração recomendada via Política de Grupo, defina o seguinte caminho da interface do usuário como Ativado: Marcado.

Computer Configuration\Policies\Administrative Templates\Printers\Set TLS/SSL security policy for IPP printers: Disallow invalid certificate date

<img width="1440" height="711" alt="image" src="https://github.com/user-attachments/assets/e777a6e5-107a-44e5-aea6-c3e298a71c01" />

Salve este post como parte do seu checklist de hardening Windows.
