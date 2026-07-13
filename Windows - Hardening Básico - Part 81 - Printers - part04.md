<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/a0df277c-6d14-46e3-aba5-bdec6eae262b" />

# Windows - Hardening Básico - Part 81 - Printers - part04

Garanta que 'Manage processing of Queue-specific files' esteja atribuido como 'Enabled: Limit Queue-specific files to Color profiles'

Essa configuração de política gerencia como os arquivos específicos da fila são processados durante a instalação da impressora. No momento da instalação da impressora, um aplicativo de instalação fornecido pelo fabricante pode especificar um conjunto de arquivos, de qualquer tipo, para serem associados a uma fila de impressão específica. Os arquivos são baixados para cada cliente que se conecta ao servidor de impressão.

O estado recomendado para essa configuração é: Ativado: Limitar arquivos específicos da fila a perfis de cor.

Existe uma vulnerabilidade de execução remota de código no Spooler de Impressão do Windows (CVE-2021-36958) quando o serviço Spooler de Impressão do Windows executa operações de arquivo privilegiadas de forma inadequada. Um agente malicioso que explore com sucesso essa vulnerabilidade pode executar código arbitrário com privilégios de SISTEMA e, em seguida, instalar programas; visualizar, alterar ou excluir dados; ou criar novas contas com direitos de usuário completos.

Para estabelecer a configuração recomendada via Política de Grupo, defina o seguinte caminho da interface do usuário como Ativado: Limitar arquivos específicos da fila a perfis de cor:

Computer Configuration\Policies\Administrative Templates\Printers\Manage processing of Queue-specific files

<img width="1420" height="709" alt="image" src="https://github.com/user-attachments/assets/8bc5cc76-18bc-4b5e-b3a9-e84b6999485a" />

Garanta que 'Point and Print Restrictions: When installing drivers for a new connection' esteja atribuido como 'Enabled: Show warning and elevation prompt'

Essa configuração de política controla se os computadores exibirão um aviso e uma solicitação de elevação de privilégios de segurança quando os usuários criarem uma nova conexão de impressora usando o recurso Apontar e Imprimir.

O estado recomendado para essa configuração é: Ativado: Exibir aviso e solicitação de elevação de privilégios.

Observação: Em 10 de agosto de 2021, a Microsoft anunciou uma alteração no comportamento padrão do recurso Apontar e Imprimir, que modifica o comportamento padrão de instalação e atualização de drivers para exigir privilégios de administrador. Isso está documentado no artigo KB5005652 — Gerenciar o novo comportamento de instalação de drivers padrão do recurso Apontar e Imprimir (CVE-2021-34481). Essa alteração substitui todas as configurações de Política de Grupo do recurso Apontar e Imprimir e garante que somente administradores possam instalar drivers de impressora de um servidor de impressão usando o recurso Apontar e Imprimir.

Habilitar o Controle de Conta de Usuário (UAC) do Windows para a instalação de novos drivers de impressão pode ajudar a mitigar a vulnerabilidade PrintNightmare (CVE-2021-34527) e outros ataques ao Spooler de Impressão.

Embora o comportamento padrão de instalação do driver de apontar e imprimir substitua essa configuração, é importante configurá-la como medida de segurança caso o comportamento seja revertido.

Para estabelecer a configuração recomendada via Política de Grupo, defina o seguinte caminho da interface do usuário como Ativado: Exibir aviso e solicitação de elevação de privilégios:

Computer Configuration\Policies\Administrative Templates\Printers\Point and Print Restrictions: When installing drivers for a new connection

<img width="1430" height="717" alt="image" src="https://github.com/user-attachments/assets/ce5f4ac9-8f67-4713-9a93-69a25451fdb7" />

Salve este post como parte do seu checklist de hardening Windows.
