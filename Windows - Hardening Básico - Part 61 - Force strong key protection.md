<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/3eec18a3-cebd-4248-b377-3521612982b1" />


# Windows - Hardening Básico - Part 61 - Force strong key protection

Garanta que 'System cryptography: Force strong key protection for user keys stored on the computer' esteja configurada como 'User is prompted when the key is first used' ou superior

Se a conta de um usuário for comprometida ou se o computador dele for inadvertidamente deixado desprotegido, um usuário malicioso poderá usar as chaves armazenadas para acessar recursos protegidos. Você pode configurar essa política para que os usuários precisem fornecer uma senha diferente da senha do domínio sempre que usarem uma chave. Essa configuração dificulta o acesso de um invasor às chaves de usuário armazenadas localmente, mesmo que ele assuma o controle do computador do usuário e descubra a senha de login.

Computer Configuration\Policies\Windows Settings\Security Settings\Local Policies\Security Options\System cryptography: Force strong key protection for user keys stored on the computer

<img width="1268" height="772" alt="image" src="https://github.com/user-attachments/assets/e3a68b9c-0550-4f85-9f12-8eb5dbb5f7da" />

Salve este post como parte do seu checklist de hardening Windows.
