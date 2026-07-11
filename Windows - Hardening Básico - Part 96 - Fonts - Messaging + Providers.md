![](https://media.licdn.com/dms/image/v2/D4D12AQFwa0UeNyH35w/article-cover_image-shrink_720_1280/B4DZ4tmOPKKAAQ-/0/1778881457350?e=1785369600&v=beta&t=klJGzSYVOLiuz_Nd4WhGnhXTmvPSefipEl4BjlPX6-k)

# Windows - Hardening Básico - Part 96 - Fonts - Messaging + Providers

Garanta que 'Enable Font Providers' esteja atribuido como 'Disabled'

Essa configuração de política determina se o Windows tem permissão para baixar fontes e dados do catálogo de fontes de um provedor de fontes online.

O estado recomendado para essa configuração é: Desativado.

Em um ambiente corporativo gerenciado, o departamento de TI deve gerenciar as alterações na configuração do sistema para garantir que todas as alterações sejam testadas e aprovadas.

Para estabelecer a configuração recomendada via Política de Grupo, defina o seguinte caminho da interface do usuário como Desativado:


```
Computer Configuration\Policies\Administrative Templates\Network\Fonts\Enable Font Providers
```

<img width="1441" height="817" alt="image" src="https://github.com/user-attachments/assets/934d1113-507e-4d29-a551-f62dc629de45" />

Garanta que 'Allow Message Service Cloud Sync' esteja atribuido como 'Disabled'

Essa configuração de política permite o backup e a restauração de mensagens de texto de celulares nos serviços de nuvem da Microsoft.

O estado recomendado para essa configuração é: Desativado.

Em ambientes de alta segurança, os dados nunca devem ser compartilhados com terceiros sem consentimento explícito, pois podem conter informações confidenciais.

Para estabelecer a configuração recomendada via Política de Grupo, defina o seguinte caminho da interface do usuário como Desativado:


```
Computer Configuration\Policies\Administrative Templates\Windows Components\Messaging\Allow Message Service Cloud Sync
```

<img width="1445" height="842" alt="image" src="https://github.com/user-attachments/assets/cdbeddd1-7647-481c-a3c4-cb6ad22dedba" />


Salve este post como parte do seu checklist de hardening Windows.
