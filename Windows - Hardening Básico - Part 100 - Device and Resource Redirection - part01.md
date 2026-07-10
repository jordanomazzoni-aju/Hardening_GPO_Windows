<p><img src="https://media.licdn.com/dms/image/v2/D4D12AQFGLP9z9_myyA/article-cover_image-shrink_720_1280/B4DZ4uQ.SyK4AU-/0/1778892664199?e=1785369600&amp;v=beta&amp;t=rM3IAxBFiHsBNNOELSJdICiJGWwC5fDhgkCqoyF-3GQ" alt="" /></p>
<h1><strong>Windows - Hardening Básico - Part 100 - Device and Resource Redirection - part01</strong></h1>
<p>Garanta que 'Allow UI Automation redirection' esteja atribuido como 'Disabled'</p>
<p>Essa configuração de política determina se os aplicativos cliente de Automação da Interface do Usuário (UI) em execução no computador local podem acessar elementos da interface do usuário no servidor.</p>
<p>A Automação da Interface do Usuário permite que os programas acessem a maioria dos elementos da interface do usuário, possibilitando o uso de produtos de tecnologia assistiva, como a Lupa e o Narrador, que precisam interagir com a interface do usuário para funcionar corretamente. As informações da interface do usuário também permitem que scripts de teste automatizados interajam com ela. Por exemplo, os clientes Narrador e Lupa do computador local podem ser usados para interagir com a interface do usuário em uma página da web aberta em uma sessão remota.</p>
<p>O estado recomendado para essa configuração é: Desativado.</p>
<p>Observação: as sessões de Área de Trabalho Remota não oferecem suporte ao redirecionamento da Automação da Interface do Usuário no momento.</p>
<p>Em um ambiente com restrições de segurança, é desejável reduzir a superfície de ataque. A necessidade de redirecionamento da Automação da Interface do Usuário em uma sessão de Área de Trabalho Remota é rara e não é suportada atualmente, mas faz sentido reduzir o número de caminhos inesperados para a ocorrência de atividades maliciosas.</p>
<p>Para estabelecer a configuração recomendada por meio da Política de Grupo, defina o seguinte caminho da interface do usuário como Desativado:</p>
<blockquote>
<p>Computer Configuration\Administrative Templates\Windows Components\Remote Desktop Services\Remote Desktop Session Host\Device and Resource Redirection\Allow UI Automation redirection</p>
</blockquote>
<p><img src="https://media.licdn.com/dms/image/v2/D4D12AQGHPZJJ1TadWQ/article-inline_image-shrink_1000_1488/B4DZ4uRBZJHIAI-/0/1778892674996?e=1785369600&amp;v=beta&amp;t=Wx70iiLoJHX0VVmFXJn4a6p7F_B9Unq-akvDvF5Yviw" alt="Conteúdo do artigo" /></p>
<p><strong>Garanta que 'Não permitir redirecionamento de porta COM' esteja atribuído como 'Ativado'</strong></p>
<p>Essa configuração de política especifica se o redirecionamento de dados para portas COM do cliente a partir do computador remoto em uma sessão dos Serviços de Área de Trabalho Remota deve ser impedido.</p>
<p>O estado recomendado para essa configuração é: Ativado.</p>
<p>Em um ambiente com maior sensibilidade à segurança, é desejável reduzir a superfície de ataque. A necessidade de redirecionamento de porta COM em uma sessão de Área de Trabalho Remota é muito rara, portanto, faz sentido reduzir o número de vias inesperadas para exfiltração de dados e/ou transferência de código malicioso.</p>
<p>Para estabelecer a configuração recomendada via Política de Grupo, defina o seguinte caminho da interface do usuário como Ativado:</p>
<blockquote>
<p>Computer Configuration\Policies\Administrative Templates\Windows Components\Remote Desktop Services\Remote Desktop Session Host\Device and Resource Redirection\Do not allow COM port redirection</p>
</blockquote>
<p><img src="https://media.licdn.com/dms/image/v2/D4D12AQHWyS6QTyJ_8g/article-inline_image-shrink_1000_1488/B4DZ4uRFN4IMAI-/0/1778892690720?e=1785369600&amp;v=beta&amp;t=Uy5Xpr389OuILkoPN8ctx-gMilq5f2eIzyx2225So0M" alt="Conteúdo do artigo" /></p>
<p>Garanta que 'Do not allow drive redirection' esteja atribuido como 'Enabled'</p>
<p>Essa configuração de política impede que os usuários compartilhem as unidades locais de seus computadores cliente com os Servidores de Área de Trabalho Remota aos quais acessam. As unidades mapeadas aparecem na árvore de pastas da sessão no Explorador de Arquivos do Windows no seguinte formato:</p>
<p>\TSClient&lt;letra da unidade&gt;$</p>
<p>Se as unidades locais forem compartilhadas, elas ficarão vulneráveis a invasores que desejam explorar os dados armazenados nelas.</p>
<p>O estado recomendado para essa configuração é: Ativado.</p>
<p>Os dados podem ser encaminhados da sessão dos Serviços de Área de Trabalho Remota do usuário para o computador local do usuário sem qualquer interação direta do usuário. Um software malicioso já presente em um servidor comprometido teria acesso direto e furtivo ao disco do computador local do usuário durante a sessão de Área de Trabalho Remota.</p>
<p>Para estabelecer a configuração recomendada via Política de Grupo, defina o seguinte caminho da interface do usuário como Ativado:</p>
<blockquote>
<p>Computer Configuration\Policies\Administrative Templates\Windows Components\Remote Desktop Services\Remote Desktop Session Host\Device and Resource Redirection\Do not allow drive redirection</p>
</blockquote>
<p><img src="https://media.licdn.com/dms/image/v2/D4D12AQFS6m3bAlbe4g/article-inline_image-shrink_1000_1488/B4DZ4uRIe.KEAM-/0/1778892704040?e=1785369600&amp;v=beta&amp;t=Q64JbYSVh60oXY0SUZlwK93wQUaT0G0XEx__vlgzxNU" alt="Conteúdo do artigo" /></p>
<p>Garanta que 'Do not allow location redirection' esteja atribuido como 'Enabled'</p>
<p>Essa configuração de política controla o redirecionamento de dados de localização para o computador remoto em uma sessão dos Serviços de Área de Trabalho Remota.</p>
<p>O estado recomendado para essa configuração é: Ativado.</p>
<p>Em um ambiente com restrições de segurança, é desejável reduzir a superfície de ataque. A necessidade de redirecionamento de dados de localização em uma sessão de Área de Trabalho Remota é rara, portanto, faz sentido reduzir o número de possíveis vias de acesso para atividades maliciosas.</p>
<p>Para estabelecer a configuração recomendada via Política de Grupo, defina o seguinte caminho da interface do usuário como Ativado:</p>
<blockquote>
<p>Computer Configuration\Administrative Templates\Windows Components\Remote Desktop Services\Remote Desktop Session Host\Device and Resource Redirection\Do not allow location redirection</p>
</blockquote>
<p><img src="https://media.licdn.com/dms/image/v2/D4D12AQHeyKzAyIb2TQ/article-inline_image-shrink_1000_1488/B4DZ4uRLTxKAAI-/0/1778892715591?e=1785369600&amp;v=beta&amp;t=hNxw-zUsM1h7Jz41EXp-wSlVrBgITlzV_UFJZumiE-M" alt="Conteúdo do artigo" /></p>
<p>Salve este post como parte do seu checklist de hardening Windows.</p>
