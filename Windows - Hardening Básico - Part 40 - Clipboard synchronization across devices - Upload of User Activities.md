<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/4844dd19-1bae-4bce-b411-f3abff148f92" />


# Windows - Hardening Básico - Part 40 - Clipboard synchronization across devices - Upload of User Activities

Garanta que 'Allow Clipboard synchronization across devices' esteja atribuido como 'Disabled'

Essa configuração determina se o conteúdo da área de transferência pode ser sincronizado entre dispositivos.

Em ambientes de alta segurança, os dados da área de transferência devem permanecer locais no sistema e não devem ser sincronizados entre dispositivos, pois podem conter informações muito confidenciais que precisam ser mantidas localmente.

Computer Configuration\Policies\Administrative Templates\System\OS Policies\Allow Clipboard synchronization across devices

Garanta que 'Allow upload of User Activities' esteja atribuido como 'Disabled'

Essa configuração de política determina se as atividades do usuário publicadas podem ser carregadas na nuvem.

Em ambientes de alta segurança, os dados nunca devem ser compartilhados com terceiros sem consentimento explícito, pois podem conter informações confidenciais.

Computer Configuration\Policies\Administrative Templates\System\OS Policies\Allow upload of User Activities



Resumo das configurações:


<img width="1264" height="842" alt="image" src="https://github.com/user-attachments/assets/5bb1fa6f-13df-4d3b-93ae-498d96368c6f" />

<img width="1264" height="843" alt="image" src="https://github.com/user-attachments/assets/b11b70d1-70d2-4ca5-9aca-083030e79cc1" />


Salve este post como parte do seu checklist de hardening Windows.
