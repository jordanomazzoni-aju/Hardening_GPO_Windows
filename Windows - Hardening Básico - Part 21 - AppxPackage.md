<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/2a66cdf1-9354-4278-8dcc-ef8b3a722609" />


# Windows - Hardening Básico - Part 21 - AppxPackage

Gerenciar pacotes Appx via PowerShell não é uma mera tarefa de limpeza de disco ou otimização de performance. É uma decisão importante de redução de superfície de ataque.

O excesso de facilidade e experiência do usuário joga, muitas vezes, contra os padrões de conformidade. Aplicações pré-instaladas, telemetria nativa e ferramentas de consumo integradas ao sistema operacional são vetores latentes de exposição.

O recurso AppxPackage (o ecossistema de aplicações modernas do Windows) é frequentemente o ponto cego na gestão da superfície de ataque corporativa.

Principais comandos:

Lista as aplicações instaladas para o usuário atual.

Get-AppxPackage

Get-AppxPackage Microsoft.BingNews

Get-AppxPackage Microsoft.*

Get-AppxPackage Bing

Get-AppxPackage | Select-Object Name, PackageFullName, Version, Publisher 

Get-AppxPackage | Select-Object Name, Version

Lista as aplicações para todos os perfis na máquina.

Get-AppxPackage -AllUsers

O Hardening na Prática

Get-AppxPackage Microsoft.BingNews | Remove-AppxPackage

Removendo de Todos os Usuários

Get-AppxPackage -AllUsers Microsoft.BingNews | Remove-AppxPackage -AllUsers

Dica use Wildcards: 

Use o asterisco  (ex: Maps*) para capturar todas as variações de um pacote indesejado.

Log de Auditoria: Sempre exporte a lista antes e depois do hardening para evidência de conformidade:

Get-AppxPackage -AllUsers | Select Name, PackageFullName | Export-Csv "C:\Temp\Appx_Pre_Hardening.csv"

Cuidado com as Dependências: Apps como o Microsoft Store ou Calculator podem ser vitais. Antes de uma limpeza geral, valide o impacto operacional.

Remove-AppxPackage
Remove um aplicativo já instalado para um usuário específico. É perfeito para remover aplicativos como Xbox ou Microsoft.3dBuilder do usuário atual sem afetar outros usuários no mesmo dispositivo. No entanto, ele não impedirá que o aplicativo seja instalado para novos usuários ou para aqueles que já o possuem.

Remove-AppxProvisionedPackage

Remove um aplicativo provisionado da própria imagem do Windows. Ele impede que o aplicativo seja instalado para novos usuários. Ele não afeta o aplicativo para usuários que já o têm instalado.

Isso garante que o Microsoft Bing Weather não será disponibilizado para nenhum novo usuário no sistema.

Get-AppxProvisionedPackage -Online | Where-Object DisplayName -like "Microsoft.BingNews" | Remove-AppxProvisionedPackage -Online

A remoção de aplicativos do sistema pode afetar a funcionalidade. Sempre teste em um ambiente que não seja de produção.

Hardening não é sobre limitar a experiência do usuário, é sobre garantir a soberania sobre os ativos críticos da organização. Nos ambientes que gerenciamos, manter apenas o estritamente necessário não é opcional, é o fundamento de uma postura de segurança governada e resiliente. Utilize a combinação Remove-AppxPackage com Remove-AppxProvisionedPackage provisioanndo uma imagem, garantindo que a superfície de ataque permaneça reduzida por padrão (Secure by Default), independentemente de quem utilize o endpoint.

Resumindo: (usando To-do, Microsoft.Todos)

Get-AppxPackage Microsoft.Todos

Get-AppxPackage Microsoft.Todos | Remove-AppxPackage

Get-AppxPackage -AllUsers Microsoft.Todos | Remove-AppxPackage -AllUsers

Get-AppxProvisionedPackage -Online | Where-Object DisplayName -like "Microsoft.Todos" | Remove-AppxProvisionedPackage -Online

<img width="1094" height="742" alt="image" src="https://github.com/user-attachments/assets/5141509a-fd1b-4337-8b8b-eadc9c4f65e5" />
