<img width="1279" height="720" alt="image" src="https://github.com/user-attachments/assets/9c360f3c-147d-42fe-88b3-b85e2a750bc1" />


# Windows - Hardening Básico - Part 30 - Advanced Audit Policy - System

A implementação da Advanced Audit Policy Configuration via GPO é um imperativo de governança que eleva o monitoramento de um estado passivo para rastreamento granular e de alto detalhamento, essencial para a detecção de evento para a equipe de monitoramento. 

Nos próximos passos vamos contruir a base de evidências necessária para a conformidade com frameworks globais como NIST e ISO 27001 além de trazer vida e significado aos eventos de um SOC.

1-) Garanta que a configuração 'Audit IPsec Driver' esteja atribuída como 'Success and Failure' 

Esta subcategoria relata as atividades do driver de segurança do Protocolo de Internet (IPsec). Os eventos desta subcategoria incluem:

4960: IPsec dropped an inbound packet that failed an integrity check. If this problem persists, it could indicate a network issue or that packets are being modified in transit to this computer. Verify that the packets sent from the remote computer are the same as those received by this computer. This error might also indicate interoperability problems with other IPsec implementations.

4961: IPsec dropped an inbound packet that failed a replay check. If this problem persists, it could indicate a replay attack against this computer.

4962: IPsec dropped an inbound packet that failed a replay check. The inbound packet had too low a sequence number to ensure it was not a replay.

4963: IPsec dropped an inbound clear text packet that should have been secured. This is usually due to the remote computer changing its IPsec policy without informing this computer. This could also be a spoofing attack attempt.

4965: IPsec received a packet from a remote computer with an incorrect Security Parameter Index (SPI). This is usually caused by malfunctioning hardware that is corrupting packets. If these errors persist, verify that the packets sent from the remote computer are the same as those received by this computer. This error may also indicate interoperability problems with other IPsec implementations. In that case, if connectivity is not impeded, then these events can be ignored.

5478: IPsec Services has started successfully.

5479: IPsec Services has been shut down successfully. The shutdown of IPsec Services can put the computer at greater risk of network attack or expose the computer to potential security risks.

5480: IPsec Services failed to get the complete list of network interfaces on the computer. This poses a potential security risk because some of the network interfaces may not get the protection provided by the applied IPsec filters. Use the IP Security Monitor snap-in to diagnose the problem.

5483: IPsec Services failed to initialize RPC server. IPsec Services could not be started.

5484: IPsec Services has experienced a critical failure and has been shut down. The shutdown of IPsec Services can put the computer at greater risk of network attack or expose the computer to potential security risks.

5485: IPsec Services failed to process some IPsec filters on a plug-and-play event for network interfaces. This poses a potential security risk because some of the network interfaces may not get the protection provided by the applied IPsec filters. Use the IP Security Monitor snap-in to diagnose the problem.

Computer Configuration\Policies\Windows Settings\Security Settings\Advanced Audit Policy Configuration\Audit Policies\System\Audit IPsec Driver

2-) Garanta que a configuração 'Audit Other System Events' esteja atribuída como 'Success and Failure'

Esta subcategoria registra outros eventos do sistema. Os eventos desta subcategoria incluem:

5024: The Windows Firewall Service has started successfully.

5025: The Windows Firewall Service has been stopped.

5027: The Windows Firewall Service was unable to retrieve the security policy from the local storage. The service will continue enforcing the current policy.

5028: The Windows Firewall Service was unable to parse the new security policy. The service will continue with currently enforced policy.

5029: The Windows Firewall Service failed to initialize the driver. The service will continue to enforce the current policy.

5030: The Windows Firewall Service failed to start.

5032: Windows Firewall was unable to notify the user that it blocked an application from accepting incoming connections on the network.

5033: The Windows Firewall Driver has started successfully.

5034: The Windows Firewall Driver has been stopped.

5035: The Windows Firewall Driver failed to start.

5037: The Windows Firewall Driver detected critical runtime error. Terminating.

5058: Key file operation.

5059: Key migration operation.

Computer Configuration\Policies\Windows Settings\Security Settings\Advanced Audit Policy Configuration\Audit Policies\System\Audit Other System Events

3-) Garanta que a configuração 'Audit Security State Change' esteja atribuída como 'Success' 

Esta subcategoria registra alterações no estado de segurança do sistema, como quando o subsistema de segurança é iniciado e interrompido. Os eventos desta subcategoria incluem:

4608: Windows is starting up.

4609: Windows is shutting down.

4616: The system time was changed.

4621: Administrator recovered system from CrashOnAuditFail. Users who are not administrators will now be allowed to log on. Some audit-able activity might not have been recorded.

Computer Configuration\Policies\Windows Settings\Security Settings\Advanced Audit Policy Configuration\Audit Policies\System\Audit Security State Change

4-) Garanta que a configuração 'Audit Security System Extension' esteja atribuída como 'Success'

Esta subcategoria registra o carregamento de código de extensão, como pacotes de autenticação, pelo subsistema de segurança. Os eventos desta subcategoria incluem:

4610: An authentication package has been loaded by the Local Security Authority.

4611: A trusted logon process has been registered with the Local Security Authority.

4614: A notification package has been loaded by the Security Account Manager.

4622: A security package has been loaded by the Local Security Authority.

4697: A service was installed in the system.

Computer Configuration\Policies\Windows Settings\Security Settings\Advanced Audit Policy Configuration\Audit Policies\System\Audit Security System Extension

5-) Garanta que a configuração 'Audit System Integrity' esteja atribuída como 'Success and Failure'

Esta subcategoria relata violações da integridade do subsistema de segurança. Os eventos desta subcategoria incluem:

4612: Internal resources allocated for the queuing of audit messages have been exhausted, leading to the loss of some audits.

4615: Invalid use of LPC port.

4618: A monitored security event pattern has occurred.

4816: RPC detected an integrity violation while decrypting an incoming message.


5038: Code integrity determined that the image hash of a file is not valid. The file could be corrupt due to unauthorized modification or the invalid hash could indicate a potential disk device error.

5056: A cryptographic self test was performed.

5057: A cryptographic primitive operation failed.

5060: Verification operation failed.

5061: Cryptographic operation.

5062: A kernel-mode cryptographic self test was performed.

Computer Configuration\Policies\Windows Settings\Security Settings\Advanced Audit Policy Configuration\Audit Policies\System\Audit System Integrity

Resumo das configurações:
<img width="1122" height="753" alt="image" src="https://github.com/user-attachments/assets/331c4c9f-5e73-4d7a-b136-6a9d1367f477" />

Salve este post como parte do seu checklist de hardening Windows.
