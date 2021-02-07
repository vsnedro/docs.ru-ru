---
description: См. Дополнительные сведения о настройке службы WCF для взаимодействия с клиентами веб-службы ASP.NET.
title: Практическое руководство. Настройка службы WCF для взаимодействия с клиентами веб-службы ASP.NET
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 48e1cd90-de80-4d6c-846e-631878955762
ms.openlocfilehash: 180307763054f8dfe5696fb0bbf294ec2b5ee3db
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99743399"
---
# <a name="how-to-configure-wcf-service-to-interoperate-with-aspnet-web-service-clients"></a>Практическое руководство. Настройка службы WCF для взаимодействия с клиентами веб-службы ASP.NET

Чтобы настроить конечную точку службы Windows Communication Foundation (WCF) для взаимодействия с клиентами веб-службы ASP.NET, используйте <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> тип в качестве типа привязки для конечной точки службы.  
  
 В привязке можно дополнительно включить поддержку протокола HTTPS и проверку подлинности клиента на транспортном уровне. Клиенты веб-службы ASP.NET не поддерживают кодирование сообщений MTOM, поэтому <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> свойство должно оставаться в качестве значения по умолчанию, то есть <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType> . Клиенты веб-службы ASP.NET не поддерживают протокол WS-Security, поэтому <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> для параметра должно быть задано значение <xref:System.ServiceModel.BasicHttpSecurityMode.Transport> .  
  
 Чтобы метаданные службы WCF были доступны для средств создания прокси веб-службы ASP.NET (то есть [средства языка описания веб-служб (Wsdl.exe)](/previous-versions/dotnet/netframework-4.0/7h3ystb6(v=vs.100)), [средства обнаружения веб-служб (Disco.exe)](/previous-versions/dotnet/netframework-4.0/cy2a3ybs(v=vs.100))и функции **добавления веб-ссылки** в Visual Studio, необходимо предоставить конечную точку метаданных HTTP/GET.  
  
## <a name="add-an-endpoint-in-code"></a>Добавление конечной точки в код  
  
1. Создайте новый экземпляр класса <xref:System.ServiceModel.BasicHttpBinding>.  
  
2. Если требуется, включите безопасность транспортного уровня для привязки этой конечной точки службы, задав для привязки режим безопасности <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>. Дополнительные сведения см. в разделе [Безопасность транспорта](transport-security.md).  
  
3. Добавьте новую конечную точку приложения в узел службы, используя созданный экземпляр привязки. Дополнительные сведения о добавлении конечной точки службы в код см. в разделе [инструкции. Создание конечной точки службы в коде](how-to-create-a-service-endpoint-in-code.md).  
  
4. Включите конечную точку метаданных HTTP/GET для своей службы. Дополнительные сведения см. [в разделе инструкции. Публикация метаданных для службы с помощью кода](how-to-publish-metadata-for-a-service-using-code.md).  
  
## <a name="add-an-endpoint-in-a-configuration-file"></a>Добавление конечной точки в файл конфигурации  
  
1. Создайте новую конфигурацию привязки <xref:System.ServiceModel.BasicHttpBinding>. Дополнительные сведения см. в разделе [как указать привязку службы в конфигурации](../how-to-specify-a-service-binding-in-configuration.md).  
  
2. Если требуется, включите безопасность транспортного уровня для конфигурации привязки этой конечной точки службы, задав для привязки режим безопасности <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>. Дополнительные сведения см. в разделе [Безопасность транспорта](transport-security.md).  
  
3. Настройте новую конечную точку приложения для службы, используя созданную конфигурацию привязки. Дополнительные сведения о добавлении конечной точки службы в файл конфигурации см. в разделе [инструкции. Создание конечной точки службы в конфигурации](how-to-create-a-service-endpoint-in-configuration.md).  
  
4. Включите конечную точку метаданных HTTP/GET для своей службы. Дополнительные сведения см. в разделе [инструкции. Публикация метаданных для службы с помощью файла конфигурации](how-to-publish-metadata-for-a-service-using-a-configuration-file.md).  
  
## <a name="example"></a>Пример  

 В следующем примере кода показано, как добавить конечную точку WCF, совместимую с клиентами веб-службы ASP.NET, в коде, а также в файлах конфигурации.  
  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Создание конечной точки службы в коде](how-to-create-a-service-endpoint-in-code.md)
- [Практическое руководство. Публикация метаданных для службы с использованием кода](how-to-publish-metadata-for-a-service-using-code.md)
- [Практическое руководство. Задание привязки службы в конфигурации](../how-to-specify-a-service-binding-in-configuration.md)
- [Практическое руководство. Создание конечной точки службы в конфигурации](how-to-create-a-service-endpoint-in-configuration.md)
- [Практическое руководство. Публикация метаданных для службы с использованием файла конфигурации](how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [Безопасность транспорта](transport-security.md)
- [Использование метаданных](using-metadata.md)
