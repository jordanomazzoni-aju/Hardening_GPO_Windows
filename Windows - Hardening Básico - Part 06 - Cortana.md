<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/b9e0035b-860c-4a18-aba5-390dc3f96b7f" />


# Windows - Hardening Básico - Part 06 - Cortana

Desativar Cortana não é apenas uma questão de privacidade. É uma medida crítica de segurança: funcionalidades como execução de comandos e acesso a credenciais podem ser exploradas em ataques de elevação de privilégio por exemplo.

Neste guia técnico, mostro como desativar Cortana via GPO e por que isso deve estar no seu checklist de hardening

Garanta que a configuração 'Allow Cortana' esteja atribuída como 'Disabled'

Garanta que a configuração 'Allow Cortana above lock screen' esteja atribuída como 'Disabled' 

Garanta que a configuração 'Allow indexing of encrypted files' esteja atribuída como 'Disabled' 

Garanta que a configuração 'Allow search and Cortana to use location' esteja atribuída como 'Disabled'

Atribua os valores:

1-) A Cortana será desativada. Os usuários ainda poderão usar a busca para encontrar itens no dispositivo e na internet. Se a Cortana estiver ativada, informações confidenciais poderão ser armazenadas no histórico de buscas e enviadas para a Microsoft.

Computer Configuration\Policies\Administrative Templates\Windows Components\Search\Allow Cortana

2-) O acesso a qualquer recurso do computador não deve ser permitido quando o dispositivo estiver bloqueado. O sistema precisará ser desbloqueado para que o usuário interaja com a Cortana por meio de comandos de voz.

Computer Configuration\Policies\Administrative Templates\Windows Components\Search\Allow Cortana above lock screen

3-) Indexar e permitir que os usuários pesquisem arquivos criptografados pode potencialmente revelar dados confidenciais armazenados nesses arquivos.

Computer Configuration\Policies\Administrative Templates\Windows Components\Search\Allow indexing of encrypted files

4-) Em um ambiente corporativo gerenciado, permitir que a Cortana e a Busca acessem dados de localização é desnecessário. É provável que as organizações não queiram que essas informações sejam compartilhadas. A Busca e a Cortana não terão acesso a informações de localização.

Computer Configuration\Policies\Administrative Templates\Windows Components\Search\Allow search and Cortana to use location

<img width="1118" height="814" alt="image" src="https://github.com/user-attachments/assets/2a430200-645e-4b5e-8ada-0882af27aa7c" />

Realizar estas configurações de forma consciente irá elevar o padrão e a maturidade de segurança do ambiente de Desktops. Quanto menos softwares instalados melhor. Quanto menos serviços desnecessários melhor.

Sua empresa permite Cortana em estações de trabalho? Quais políticas de grupo vocês usam para controlar funcionalidades de risco no Windows?

Até o próximo artigo.

#cybersecurity

#blueteam

#windows
