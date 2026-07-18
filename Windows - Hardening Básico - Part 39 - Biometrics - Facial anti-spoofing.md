<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/bfb12808-acb9-49d3-b7ae-00493dc02b65" />


# Windows - Hardening Básico - Part 39 - Biometrics - Facial anti-spoofing

O Enhanced Anti-Spoofing (também conhecido como Enhanced Spoofing Protection) é uma camada de inteligência que obriga o hardware de biometria a provar que o que está na frente da lente é um ser humano vivo e não uma representação (foto, vídeo ou máscara).

Exigência de IR (Infrared): Quando ativada, a GPO exige que a câmera utilize dados de infravermelho para mapear a profundidade e o calor. Uma foto impressa ou uma tela de iPad não emitem o mesmo padrão térmico ou de profundidade que um rosto real.

Análise de Textura e Profundidade faz com que o algoritmo busque por artefatos que denunciam uma fraude, como reflexos em papel ou bordas de uma tela.

Hardening de Hardware ocorre quando a câmera do dispositivo não for compatível com os requisitos de segurança do Enhanced Anti-Spoofing, o Windows simplesmente desabilita o reconhecimento facial para aquele usuário, forçando o uso de PIN ou senha.

Garanta que 'Configure enhanced anti-spoofing' esteja atribuido como 'Enabled'

Essa configuração de política determina se a proteção aprimorada contra falsificação de identidade (anti-spoofing) está configurada para dispositivos que a suportam.

Computer Configuration\Policies\Administrative Templates\Windows Components\Biometrics\Facial Features\Configure enhanced anti-spoofing

<img width="1267" height="848" alt="image" src="https://github.com/user-attachments/assets/dc6dd210-a940-4f79-8eea-6c0023a8f46d" />

Salve este post como parte do seu checklist de hardening Windows.
