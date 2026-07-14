<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/b34e94f0-b0f9-49ab-b43d-1f64281361f5" />


# Windows - Hardening Básico - Part 55 - Account - Administrator - Guest

Renomear as contas de Administrador e Convidado é uma recomendação clássica de hardening. A maioria dos ataques de força bruta, password spraying e scripts de malwares (incluindo Ransomwares) são codificados para atingir o usuário "Administrator" (ou "Administrador" em sistemas PT-BR). 

Ao renomear a conta, você força o atacante a realizar uma etapa adicional de reconhecimento para descobrir qual é o novo nome da conta com privilégios elevados. Isso invalida ataques automatizados que tentam credenciais comuns contra um alvo fixo.

Renomear previne ataques de "baixo esforço" (scripts simples e bots), mas não detém um invasor humano persistente que saiba buscar pelo RID. É importante lembrar que, tecnicamente, cada conta no Windows possui um SID (Security Identifier). O identificador relativo (RID) da conta de Administrador nativa é sempre 500, independentemente do nome.

Configure 'Accounts: Rename administrator account'

Esta configuração de política permite renomear a conta de administrador local integrada. Esta conta é conhecida por ser alvo de ataques cibernéticos.

Recomenda-se escolher outro nome para esta conta e evitar nomes que remetam a contas administrativas ou com privilégios elevados. Certifique-se também de alterar a descrição padrão do administrador local (através do console de Gerenciamento do Computador).

A conta de administrador integrada existe em todos os sistemas operacionais Windows 2000 ou posteriores. Se esta conta for renomeada, torna-se um pouco mais difícil para os agentes cibernéticos adivinhar essa combinação privilegiada de nome de usuário e senha.

A conta de administrador integrada não pode ser bloqueada, independentemente de quantas vezes um agente cibernético tente usar uma senha incorreta. Essa característica torna a conta de administrador um alvo popular para ataques de força bruta que tentam adivinhar senhas. A eficácia desta contramedida é reduzida porque esta conta possui um SID conhecido e existem ferramentas de terceiros que permitem a autenticação usando o SID em vez do nome da conta. Portanto, mesmo que a conta de Administrador seja renomeada, um agente malicioso poderia lançar um ataque de força bruta usando o SID para fazer login.

Computer Configuration\Policies\Windows Settings\Security Settings\Local Policies\Security Options\Accounts: Rename administrator account

<img width="1268" height="843" alt="image" src="https://github.com/user-attachments/assets/3a765fa1-190e-4db6-b503-7f0bc0919f02" />

Configure 'Accounts: Rename guest account'

Essa configuração de política permite renomear a conta de convidado local integrada. Essa conta é conhecida por ser alvo de ataques cibernéticos.

Recomenda-se renomear essa conta para um nome que não indique sua finalidade, mesmo que ela esteja desativada.

Computer Configuration\Policies\Windows Settings\Security Settings\Local Policies\Security Options\Accounts: Rename guest account

<img width="1268" height="846" alt="image" src="https://github.com/user-attachments/assets/872fb6a3-026d-43ae-b0f6-2b9e5e63391a" />

Para as contas de Administrador local a recomendação é usar o LAPS para gerenciar senhas únicas e aleatórias para essas contas renomeadas em todo o domínio.
