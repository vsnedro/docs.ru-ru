---
title: Настройка поведений клиентов
description: 'Узнайте о двух способах настройки поведения WCF: в файле конфигурации приложения или программным способом из вызывающего приложения.'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: df5b32fa-e73b-4e8e-b66f-357c748e0173
ms.openlocfilehash: 34cbb9e31933debb5120eb30956c3a5f0be065ed
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266718"
---
# <a name="configuring-client-behaviors"></a>Настройка поведений клиентов

Windows Communication Foundation (WCF) настраивает поведение двумя способами: либо путем обращения к конфигурациям поведения, которые определены в `<behavior>` разделе файла конфигурации клиентского приложения, либо программными средствами в вызывающем приложении. В этом разделе описываются оба подхода.  
  
 При использовании файла конфигурации конфигурация поведения представляет собой именованную коллекцию параметров конфигурации. Имя каждой из конфигураций поведения должно быть уникальным. Эта строка используется в атрибуте `behaviorConfiguration` конфигурации конечной точки, чтобы связать конечную точку с поведением.  
  
## <a name="example"></a>Пример  

 В следующем фрагменте кода конфигурации определяется поведение с именем `myBehavior`. Конечная точка клиента ссылается на это поведение в атрибуте `behaviorConfiguration`.  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <behaviors>  
            <endpointBehaviors>  
                <behavior name="myBehavior">  
                    <clientVia />  
                </behavior>  
            </endpointBehaviors>  
        </behaviors>  
        <bindings>  
            <basicHttpBinding>  
                <binding name="myBinding" maxReceivedMessageSize="10000" />  
            </basicHttpBinding>  
        </bindings>  
        <client>  
            <endpoint address="myAddress" binding="basicHttpBinding" bindingConfiguration="myBinding" behaviorConfiguration="myBehavior" contract="myContract" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="using-behaviors-programmatically"></a>Управление поведениями программным образом  

 Можно также настроить или вставить поведение программным путем, найдя соответствующее `Behaviors` свойство в клиентском объекте Windows Communication Foundation (WCF) или объекте фабрики канала клиента перед открытием клиента.  
  
## <a name="example"></a>Пример  

 В следующем примере кода показано, как программным образом вставить поведение, обратившись к свойству <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A> объекта <xref:System.ServiceModel.Description.ServiceEndpoint>, возвращаемого свойством <xref:System.ServiceModel.ChannelFactory.Endpoint%2A> до создания объекта канала.  
  
 [!code-csharp[ChannelFactoryBehaviors#10](../../../samples/snippets/csharp/VS_Snippets_CFX/channelfactorybehaviors/cs/client.cs#10)]
 [!code-vb[ChannelFactoryBehaviors#10](../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelfactorybehaviors/vb/client.vb#10)]  
  
## <a name="see-also"></a>См. также

- [\<behaviors>](../configure-apps/file-schema/wcf/behaviors.md)
