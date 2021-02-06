---
description: Дополнительные сведения см. в статье Создание служб с возможностью взаимодействия WS-I Basic Profile 1,1
title: Создание служб, поддерживающих взаимодействие с базовым профилем WS-I 1.1
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- configuration [WCF], interoperable services
ms.assetid: 91b70a21-8f5c-4679-808c-2ed5fa6b2013
ms.openlocfilehash: 46e2d925dfe431957198b1d53b40d28adf6fb1c4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646183"
---
# <a name="creating-ws-i-basic-profile-11-interoperable-services"></a>Создание служб, поддерживающих взаимодействие с базовым профилем WS-I 1.1

Чтобы настроить конечную точку службы WCF для взаимодействия с клиентами веб-службы ASP.NET, выполните следующие действия.  
  
- использовать в качестве типа привязки для конечной точки службы тип <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType>;  
  
- не использовать функции обратного вызова и сеансового контракта и не управлять поведением транзакций на конечной точке службы.  
  
В привязке можно дополнительно включить поддержку протокола HTTPS и проверку подлинности клиента на транспортном уровне.  
  
Следующие функции класса <xref:System.ServiceModel.BasicHttpBinding> требуют функциональность, выходящую за рамки спецификации WS-I Basic Profile, версия 1.1.  
  
- Кодирование сообщения подсистемы оптимизации передачи сообщений MTOM управляется свойством <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType>. Не изменяйте значение этого свойства по умолчанию - <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType> (не использовать MTOM).  
  
- Безопасность сообщения управляется значением <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> и обеспечивает поддержку WS-Security, совместимую с основным профилем безопасности WS-I версии 1.0. Не изменяйте значение этого свойства по умолчанию - <xref:System.ServiceModel.SecurityMode.Transport?displayProperty=nameWithType> (не использовать WS-Security).  
  
Чтобы сделать метаданные для службы WCF доступными для ASP.NET, используйте средства создания клиентов веб-службы: [средство языка описания веб-служб (Wsdl.exe)](/previous-versions/dotnet/netframework-4.0/7h3ystb6(v=vs.100)), [средство обнаружения веб-служб (Disco.exe)](/previous-versions/dotnet/netframework-4.0/cy2a3ybs(v=vs.100))и функцию **Добавить веб-ссылку** в Visual Studio. Включить публикацию метаданных. Дополнительные сведения см. в разделе [Публикация конечных точек метаданных](publishing-metadata-endpoints.md).  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  

 В следующем примере кода показано, как добавить конечную точку WCF, совместимую с клиентами веб-службы ASP.NET, в коде и, Кроме того, в файле конфигурации.  
  
### <a name="code"></a>Код  

 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]  
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]  
  
## <a name="see-also"></a>См. также

- [Взаимодействие с веб-службами ASP.NET](./feature-details/interop-with-aspnet-web-services.md)
