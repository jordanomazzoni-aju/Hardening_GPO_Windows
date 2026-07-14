<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/154462c2-5949-47fa-8d4a-331e6ffadc4d" />


# Windows - Hardening Básico - Part 44 - Encryption types allowed for Kerberos

Garanta que 'Network security: Configure encryption types allowed for Kerberos' esteja atribuido como 'AES128_HMAC_SHA1, AES256_HMAC_SHA1, Future encryption types'

Essa configuração de política permite definir os tipos de criptografia que o Kerberos pode usar.

O estado recomendado para esta configuração é: AES128_HMAC_SHA1, AES256_HMAC_SHA1, Tipos de criptografia futuros.

A força de cada algoritmo de criptografia varia de um para outro. A escolha de algoritmos mais fortes reduzirá o risco de comprometimento, no entanto, isso poderá causar problemas quando o computador tentar autenticar-se com sistemas que não os suportam.

Alguns aplicativos e sistemas operacionais legados ainda podem exigir RC4_HMAC_MD5 - recomendamos que você teste em seu ambiente e verifique se é possível removê-lo com segurança.

Atenção para as vulnerabilidades e as oportuniodades de ataque que podem surgir ao habilitar outras opções. Homologue, pesquise e investigue o impacto de cada configuração.

Computer Configuration\Policies\Windows Settings\Security Settings\Local Policies\Security Options\Network security: Configure encryption types allowed for Kerberos

<img width="1261" height="841" alt="image" src="https://github.com/user-attachments/assets/10b103c2-8312-4bf7-b206-d94f838129fc" />

Salve este post como parte do seu checklist de hardening Windows.
