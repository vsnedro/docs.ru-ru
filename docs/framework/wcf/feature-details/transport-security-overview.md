---
title: Общие сведения о безопасности транспорта
description: Узнайте о основных механизмах безопасности транспорта в привязках, предоставляемых системой WCF. Эти механизмы безопасности зависят от используемой привязки и транспорта.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 00959326-aa9d-44d0-af61-54933d4adc7f
ms.openlocfilehash: 100af5cd7bc8fe91c7498902177f47d88a25c2ab
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96261440"
---
# <a name="transport-security-overview"></a>Общие сведения о безопасности транспорта

Механизмы безопасности транспорта в Windows Communication Foundation (WCF) зависят от используемой привязки и транспорта. Например, при использовании класса <xref:System.ServiceModel.WSHttpBinding> транспортом является протокол HTTP и в качестве основного механизма защиты транспорта применяется протокол SSL через HTTP, обычно называемый HTTPS. В этом разделе обсуждаются основные механизмы безопасности транспорта, используемые в привязках, предоставляемых системой WCF.  
  
> [!NOTE]
> При использовании безопасности SSL с .NET Framework 3,5 и более поздней версии клиент WCF использует как промежуточные сертификаты в хранилище сертификатов, так и промежуточные сертификаты, полученные во время согласования SSL для выполнения проверки цепочки сертификатов в сертификате службы. Платформа .NET Framework 3.0 использует только промежуточные сертификаты, установленные в локальном хранилище сертификатов.  
  
> [!WARNING]
> При использовании системы безопасности транспорта свойство <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> не применяется. Чтобы избежать этого, задайте для свойства <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A?displayProperty=nameWithType> значение <xref:System.ServiceModel.Description.PrincipalPermissionMode.None?displayProperty=nameWithType> . <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> - это поведение службы, которое можно задать в описании службы.  
  
## <a name="basichttpbinding"></a>BasicHttpBinding  

 По умолчанию класс <xref:System.ServiceModel.BasicHttpBinding> не обеспечивает безопасность. Эта привязка предназначена для взаимодействия с поставщиками веб-служб, которые не реализуют средства обеспечения безопасности. Однако режим безопасности можно включить, присвоив свойству <xref:System.ServiceModel.BasicHttpSecurity.Mode%2A> любое значение, кроме <xref:System.ServiceModel.BasicHttpSecurityMode.None>. Чтобы включить режим безопасности транспорта, присвойте этому свойству значение <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>.  
  
### <a name="interoperation-with-iis"></a>Взаимодействие с IIS  

 Класс <xref:System.ServiceModel.BasicHttpBinding> используется в основном для взаимодействия с существующими веб-службами, многие из которых размещаются в службах IIS. Поэтому безопасность транспорта для этой привязки предназначена для беспрепятственного взаимодействия с узлами IIS. Она обеспечивается посредством установки для режима безопасности значения <xref:System.ServiceModel.BasicHttpSecurityMode.Transport> и последующего задания типа учетных данных клиента. Значения типа учетных данных соответствуют механизмам безопасности каталогов IIS. В следующем коде показаны установка режима и задание в качестве типа учетных данных типа Windows. Эту конфигурацию можно использовать, когда клиент и сервер находятся в одном домене Windows.  
  
 [!code-csharp[c_ProgrammingSecurity#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#10)]
 [!code-vb[c_ProgrammingSecurity#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#10)]  
  
 Или в виде конфигурации:  
  
```xml  
<bindings>  
  <basicHttpBinding>  
    <binding name="SecurityByTransport">  
      <security mode="Transport">  
        <transport clientCredentialType="Windows" />  
       </security>  
     </binding>  
  </basicHttpBinding>  
</bindings>  
```  
  
 В следующих разделах рассматриваются другие типы учетных данных клиентов.  
  
#### <a name="basic"></a>Основные  

 Соответствует методу обычной проверки подлинности в IIS. При использовании этого режима на сервере IIS должны быть настроены учетные записи пользователей Windows и соответствующие разрешения файловой системы NTFS. Дополнительные сведения о IIS 6,0 см. [в разделе Включение обычной проверки подлинности и настройка имени области](/previous-versions/windows/it-pro/windows-server-2003/cc785293(v=ws.10)). Дополнительные сведения о IIS 7,0 см. в разделе [Настройка обычной проверки подлинности (IIS 7)](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772009(v=ws.10)).  
  
#### <a name="certificate"></a>Сертификат  

 В IIS предусмотрена функция, требующая, чтобы клиенты входили в систему с использованием сертификата. Эта возможность также позволяет IIS сопоставить сертификат клиента с учетной записью Windows. Дополнительные сведения о IIS 6,0 см. [в разделе Включение сертификатов клиентов в iis 6,0](/previous-versions/windows/it-pro/windows-server-2003/cc727994(v=ws.10)). Дополнительные сведения о IIS 7,0 см. [в разделе Настройка сертификатов сервера в IIS 7](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732230(v=ws.10)).  
  
#### <a name="digest"></a>Digest (дайджест)  

 Дайджест-проверка подлинности подобна обычной проверке подлинности, но имеет преимущество, заключающееся в передаче учетных данных в виде хэша, а не открытого текста. Дополнительные сведения о IIS 6,0 см. [в статье дайджест-проверка подлинности в iis 6,0](/previous-versions/windows/it-pro/windows-server-2003/cc782661(v=ws.10)). Дополнительные сведения о IIS 7,0 см. в разделе [Настройка дайджест-проверки подлинности (IIS 7)](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc754104(v=ws.10)).  
  
#### <a name="windows"></a>Windows  

 Соответствует встроенной проверке подлинности Windows в IIS. При задании этого значения также предполагается, что сервер находится в домене Windows, в котором для взаимодействия с контроллером домена используется протокол Kerberos. Если сервер не находится в домене с поддержкой Kerberos или происходит сбой системы Kerberos, можно использовать значение NTLM, описанное в следующем разделе. Дополнительные сведения о IIS 6,0 см. [в статье встроенная проверка подлинности Windows в iis 6,0](/previous-versions/windows/it-pro/windows-server-2003/cc738016(v=ws.10)). Дополнительные сведения о IIS 7,0 см. [в разделе Настройка сертификатов сервера в IIS 7](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732230(v=ws.10)).
  
#### <a name="ntlm"></a>NTLM  

 Это позволяет серверу использовать NTLM для проверки подлинности в случае сбоя протокола Kerberos. Дополнительные сведения о настройке служб IIS в IIS 6,0 см. в разделе [Принудительная проверка подлинности NTLM](/previous-versions/windows/it-pro/windows-server-2003/cc786486(v=ws.10)). Для IIS 7,0 проверка подлинности Windows включает проверку подлинности NTLM. Дополнительные сведения см. в разделе [Настройка сертификатов сервера IIS 7](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732230(v=ws.10)).
  
## <a name="wshttpbinding"></a>WsHttpBinding  

 Класс <xref:System.ServiceModel.WSHttpBinding> предназначен для взаимодействия со службами, реализующими спецификации WS-*. Безопасность транспорта для этой привязки обеспечивается посредством протокола SSL по протоколам HTTP или HTTPS. Чтобы создать приложение WCF, использующее SSL, используйте IIS для размещения приложения. В случае создания резидентного приложения используйте средство HttpCfg.exe для привязки сертификата X.509 к конкретному порту на компьютере. Номер порта указывается как часть приложения WCF в качестве адреса конечной точки. При использовании транспортного режима адрес конечной точки должен включать протокол HTTPS; в противном случае во время выполнения будет вызвано исключение. Дополнительные сведения см. в разделе [Безопасность транспорта HTTP](http-transport-security.md).  
  
 Для проверки подлинности клиента присвойте свойству <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> класса <xref:System.ServiceModel.HttpTransportSecurity> одно из значений перечисления <xref:System.ServiceModel.HttpClientCredentialType>. Значения перечисления идентичны типам учетных данных клиентов для класса <xref:System.ServiceModel.BasicHttpBinding> и должны размещаться службами IIS.  
  
 В следующем примере показана привязка, используемая с учетными данными клиента типа Windows.  
  
 [!code-csharp[c_ProgrammingSecurity#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#11)]
 [!code-vb[c_ProgrammingSecurity#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#11)]  
  
## <a name="wsdualhttpbinding"></a>WSDualHttpBinding  

 Эта привязка обеспечивает безопасность только на уровне сообщений, а не на транспортном уровне.  
  
## <a name="nettcpbinding"></a>NetTcpBinding  

 Для передачи сообщений класс <xref:System.ServiceModel.NetTcpBinding> использует протокол TCP. Безопасность транспортного режима обеспечивается реализацией протокола TLS по TCP. Реализация TLS обеспечивается операционной системой.  
  
 Тип учетных данных клиента можно также задать, присвоив свойству <xref:System.ServiceModel.TcpTransportSecurity.ClientCredentialType%2A> класса <xref:System.ServiceModel.TcpTransportSecurity> одно из значений <xref:System.ServiceModel.TcpClientCredentialType>, как показано в следующем коде.  
  
 [!code-csharp[c_ProgrammingSecurity#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#12)]
 [!code-vb[c_ProgrammingSecurity#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#12)]  
  
#### <a name="client"></a>Клиент  

 На клиенте следует задать сертификат с помощью метода <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> класса <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>.  
  
> [!NOTE]
> В случае использования безопасности Windows сертификат не требуется.  
  
 В следующем коде используется отпечаток сертификата, который однозначно идентифицирует его. Дополнительные сведения см. в разделе [Работа с сертификатами](working-with-certificates.md).  
  
 [!code-csharp[c_ProgrammingSecurity#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#13)]
 [!code-vb[c_ProgrammingSecurity#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#13)]  
  
 Кроме того, можно указать сертификат в конфигурации клиента, используя [\<clientCredentials>](../../configure-apps/file-schema/wcf/clientcredentials.md) элемент в разделе "поведение".  
  
```xml  
<behaviors>  
  <behavior>  
   <clientCredentials>  
     <clientCertificate findValue= "101010101010101010101010101010000000000"
      storeLocation="LocalMachine" storeName="My"
      X509FindType="FindByThumbPrint">  
     </clientCertificate>  
   </clientCredentials>  
 </behavior>  
</behaviors>
```  
  
## <a name="netnamedpipebinding"></a>NetNamedPipeBinding  

 Класс <xref:System.ServiceModel.NetNamedPipeBinding> предназначен для эффективного взаимодействия внутри компьютера, т. е. для процессов, выполняющихся на одном компьютере, хотя между двумя компьютерами, расположенными в одной сети, могут быть созданы именованные каналы. Эта привязка обеспечивает безопасность только на транспортном уровне. При создании приложений с использованием данной привязки адреса конечных точек должны включать "net.pipe" в качестве протокола адреса конечной точки.  
  
## <a name="wsfederationhttpbinding"></a>WSFederationHttpBinding  

 При использовании безопасности транспорта эта привязка использует протокол SSL по HTTP, известный как HTTPS-протокол с выданным токеном (<xref:System.ServiceModel.WSFederationHttpSecurityMode.TransportWithMessageCredential>). Дополнительные сведения о приложениях Федерации см. в разделе [Федерация и выданные токены](federation-and-issued-tokens.md).  
  
## <a name="netpeertcpbinding"></a>NetPeerTcpBinding  

 Класс <xref:System.ServiceModel.NetPeerTcpBinding> представляет защищенный транспорт, предназначенный для эффективного взаимодействия с использованием возможности одноранговой сети. Как указано в имени класса и привязки, применяется протокол TCP. Если для режима безопасности задано значение Transport, данная привязка реализует протокол TLS по TCP. Дополнительные сведения о одноранговой функции см. в разделе одноранговая [сеть](peer-to-peer-networking.md).  
  
## <a name="msmqintegrationbinding-and-netmsmqbinding"></a>MsmqIntegrationBinding и NetMsmqBinding  

 Полное обсуждение безопасности транспорта с помощью очереди сообщений (прежнее название — MSMQ) см. в разделе [Защита сообщений с использованием защиты транспорта](securing-messages-using-transport-security.md).  
  
## <a name="see-also"></a>См. также

- [Программирование безопасности WCF](programming-wcf-security.md)
