---
title: Настройка поведений клиентов
description: 'Узнайте о двух способах настройки поведения WCF: в файле конфигурации приложения или программным способом из вызывающего приложения.'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: df5b32fa-e73b-4e8e-b66f-357c748e0173
ms.openlocfilehash: 4b83862221cf249455478c3ade159a3101062f3e
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245444"
---
# <a name="configuring-client-behaviors"></a><span data-ttu-id="262fa-103">Настройка поведений клиентов</span><span class="sxs-lookup"><span data-stu-id="262fa-103">Configuring Client Behaviors</span></span>
<span data-ttu-id="262fa-104">Windows Communication Foundation (WCF) настраивает поведение двумя способами: либо путем обращения к конфигурациям поведения, которые определены в `<behavior>` разделе файла конфигурации клиентского приложения, либо программными средствами в вызывающем приложении.</span><span class="sxs-lookup"><span data-stu-id="262fa-104">Windows Communication Foundation (WCF) configures behaviors in two ways: either by referring to behavior configurations -- which are defined in the `<behavior>` section of a client application configuration file – or programmatically in the calling application.</span></span> <span data-ttu-id="262fa-105">В этом разделе описываются оба подхода.</span><span class="sxs-lookup"><span data-stu-id="262fa-105">This topic describes both approaches.</span></span>  
  
 <span data-ttu-id="262fa-106">При использовании файла конфигурации конфигурация поведения представляет собой именованную коллекцию параметров конфигурации.</span><span class="sxs-lookup"><span data-stu-id="262fa-106">When using a configuration file, behavior configuration is a named collection of configuration settings.</span></span> <span data-ttu-id="262fa-107">Имя каждой из конфигураций поведения должно быть уникальным.</span><span class="sxs-lookup"><span data-stu-id="262fa-107">The name of each behavior configuration must be unique.</span></span> <span data-ttu-id="262fa-108">Эта строка используется в атрибуте `behaviorConfiguration` конфигурации конечной точки, чтобы связать конечную точку с поведением.</span><span class="sxs-lookup"><span data-stu-id="262fa-108">This string is used in the `behaviorConfiguration` attribute of an endpoint configuration to link the endpoint to the behavior.</span></span>  
  
## <a name="example"></a><span data-ttu-id="262fa-109">Пример</span><span class="sxs-lookup"><span data-stu-id="262fa-109">Example</span></span>  
 <span data-ttu-id="262fa-110">В следующем фрагменте кода конфигурации определяется поведение с именем `myBehavior`.</span><span class="sxs-lookup"><span data-stu-id="262fa-110">The following configuration code defines a behavior called `myBehavior`.</span></span> <span data-ttu-id="262fa-111">Конечная точка клиента ссылается на это поведение в атрибуте `behaviorConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="262fa-111">The client endpoint references this behavior in the `behaviorConfiguration` attribute.</span></span>  
  
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
  
## <a name="using-behaviors-programmatically"></a><span data-ttu-id="262fa-112">Управление поведениями программным образом</span><span class="sxs-lookup"><span data-stu-id="262fa-112">Using Behaviors Programmatically</span></span>  
 <span data-ttu-id="262fa-113">Можно также настроить или вставить поведение программным путем, найдя соответствующее `Behaviors` свойство в клиентском объекте Windows Communication Foundation (WCF) или объекте фабрики канала клиента перед открытием клиента.</span><span class="sxs-lookup"><span data-stu-id="262fa-113">You can also configure or insert behaviors programmatically by locating the appropriate `Behaviors` property on the Windows Communication Foundation (WCF) client object or on the client channel factory object prior to opening the client.</span></span>  
  
## <a name="example"></a><span data-ttu-id="262fa-114">Пример</span><span class="sxs-lookup"><span data-stu-id="262fa-114">Example</span></span>  
 <span data-ttu-id="262fa-115">В следующем примере кода показано, как программным образом вставить поведение, обратившись к свойству <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A> объекта <xref:System.ServiceModel.Description.ServiceEndpoint>, возвращаемого свойством <xref:System.ServiceModel.ChannelFactory.Endpoint%2A> до создания объекта канала.</span><span class="sxs-lookup"><span data-stu-id="262fa-115">The following code example shows how to programmatically insert a behavior by accessing the <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A> property on the <xref:System.ServiceModel.Description.ServiceEndpoint> returned from the <xref:System.ServiceModel.ChannelFactory.Endpoint%2A> property prior to the creation of the channel object.</span></span>  
  
 [!code-csharp[ChannelFactoryBehaviors#10](../../../samples/snippets/csharp/VS_Snippets_CFX/channelfactorybehaviors/cs/client.cs#10)]
 [!code-vb[ChannelFactoryBehaviors#10](../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelfactorybehaviors/vb/client.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="262fa-116">См. также</span><span class="sxs-lookup"><span data-stu-id="262fa-116">See also</span></span>

- [\<behaviors>](../configure-apps/file-schema/wcf/behaviors.md)
