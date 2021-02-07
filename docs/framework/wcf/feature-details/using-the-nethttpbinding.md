---
description: 'Дополнительные сведения о: использование NetHttpBinding'
title: Использование NetHttpBinding
ms.date: 03/30/2017
ms.assetid: fe134acf-ceca-49de-84a9-05a37e3841f1
ms.openlocfilehash: 3964c3c3e563d143df1edfcd1f98d3250301c209
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99756049"
---
# <a name="using-the-nethttpbinding"></a>Использование NetHttpBinding

<xref:System.ServiceModel.NetHttpBinding> - это привязка, предназначенная для использования служб HTTP или WebSocket и использующая по умолчанию двоичное кодирование. <xref:System.ServiceModel.NetHttpBinding> определит, будет ли она использоваться с дуплексным контрактом и контрактом типа «запрос-ответ» и изменит ли свое поведение для соответствия контракту. HTTP будет использоваться для контрактов типа «запрос-ответ», и WebSockets - для дуплексных контрактов. Данное поведение можно переопределить с помощью параметра <xref:System.ServiceModel.Channels.WebSocketTransportUsage>:.  
  
1. <xref:System.ServiceModel.Channels.WebSocketTransportUsage.Always> — Заставляет использовать WebSockets даже для контрактов "запрос-ответ".  
  
2. <xref:System.ServiceModel.Channels.WebSocketTransportUsage.Never> — Предотвращается использование WebSockets. Попытка использования дуплексного контракта с этим параметром приведет к возникновению исключения.  
  
3. <xref:System.ServiceModel.Channels.WebSocketTransportUsage.WhenDuplex> — Это значение по умолчанию, которое ведет себя, как описано выше.  
  
 <xref:System.ServiceModel.NetHttpBinding> поддерживает надежные сеансы как в режиме HTTP, так и в режиме WebSocket. В режиме WebSocket сеансы предоставляются транспортом.  
  
> [!WARNING]
> При использовании <xref:System.ServiceModel.NetHttpBinding> и в тех случаях, когда TransferMode привязки имеет значение TransferMode.Streamed, большие потоки могут привести к взаимоблокировке, в результате чего будет превышено время ожидания вызова. Чтобы избежать этой проблемы, отправляйте меньшие сообщения или используйте TransferMode.Buffered.  
  
## <a name="configuring-a-service-to-use-nethttpbinding"></a>Настройка службы на использование NetHttpBinding  

 Привязку <xref:System.ServiceModel.NetHttpBinding> можно настроить так же, как и любые другие привязки. В следующем фрагменте конфигурации показано, как настроить службу WCF с <xref:System.ServiceModel.NetHttpBinding>.  
  
```xml  
<system.serviceModel>  
    <services>  
      <service name="WcfService1.Service1">  
        <endpoint address=""  
                  binding="netHttpBinding"  
                  contract="WcfService1.IService1"/>  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange"/>  
      </service>  
    </services>  
    <bindings>  
      <netHttpBinding>  
        <binding name="My_NetHttpBindingConfig">  
          <webSocketSettings transportUsage="WhenDuplex"/>  
        </binding>  
      </netHttpBinding>  
    </bindings>  
    ...
  </system.serviceModel>  
```  
  
 В следующем фрагменте кода показано, как добавить <xref:System.ServiceModel.NetHttpBinding> в коде.  
  
```csharp  
ServiceHost svchost = new ServiceHost(typeof(Service1), baseAddress);  
            NetHttpBinding binding = new NetHttpBinding();  
            svchost.AddServiceEndpoint(typeof(IService1), binding, address);
        }  
```  
  
## <a name="see-also"></a>См. также

- [Настройка привязок для служб](../configuring-bindings-for-wcf-services.md)
- [Привязки](bindings.md)
- [Привязки, предоставляемые системой](../system-provided-bindings.md)
- [Дуплексные службы](duplex-services.md)
