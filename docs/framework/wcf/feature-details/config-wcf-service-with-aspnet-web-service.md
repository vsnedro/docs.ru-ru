---
title: Практическое руководство. Настройка службы WCF для взаимодействия с клиентами веб-службы ASP.NET
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 48e1cd90-de80-4d6c-846e-631878955762
ms.openlocfilehash: 22713aba4f86fe493ba3d16ef09c2a71b6d55fe0
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389784"
---
# <a name="how-to-configure-wcf-service-to-interoperate-with-aspnet-web-service-clients"></a>Практическое руководство. Настройка службы WCF для взаимодействия с клиентами веб-службы ASP.NET

Для настройки конечной точки службы Windows Communication Foundation (WCF) для совместимости с ASP.NET клиентами web-сервисов используйте <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> тип в качестве обязательного типа для конечных точек службы.  
  
 В привязке можно дополнительно включить поддержку протокола HTTPS и проверку подлинности клиента на транспортном уровне. ASP.NET веб-сервисов не поддерживают кодирование сообщений <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> MTOM, поэтому свойство следует <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType>оставить в качестве значения по умолчанию, которое является . Клиенты веб-служб ASP.Net не поддерживают WS-Security, поэтому для <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> должно быть задано значение <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>.  
  
 Чтобы сделать метаданные для службы WCF доступными для ASP.NET инструментов генерации прокси-серверов Web service (т.е. [web Services Description Language Tool (Wsdl.exe),](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6(v%3dvs.100))Web Services Discovery Tool [(Disco.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cy2a3ybs(v=vs.100))и функции **Add Web Reference** в Visual Studio), следует предоставить конечную точку http/GET метаданных.  
  
## <a name="add-an-endpoint-in-code"></a>Добавление точки конца в код  
  
1. Создайте новый экземпляр класса <xref:System.ServiceModel.BasicHttpBinding>.  
  
2. Если требуется, включите безопасность транспортного уровня для привязки этой конечной точки службы, задав для привязки режим безопасности <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>. Для получения подробной информации, пожалуйста, смотрите [Транспортная безопасность](../../../../docs/framework/wcf/feature-details/transport-security.md).  
  
3. Добавьте новую конечную точку приложения в узел службы, используя созданный экземпляр привязки. Подробную информацию о том, как добавить конечную точку службы в коде, можно узнать о том, [как: создать конечную точку службы в Коде.](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)  
  
4. Включите конечную точку метаданных HTTP/GET для своей службы. Для получения подробной информации [см. Как: Опубликовать Метаданные для службы с использованием кода](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md).  
  
## <a name="add-an-endpoint-in-a-configuration-file"></a>Добавление точки конца в файл конфигурации  
  
1. Создайте новую конфигурацию привязки <xref:System.ServiceModel.BasicHttpBinding>. Для получения [подробной](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)информации см.  
  
2. Если требуется, включите безопасность транспортного уровня для конфигурации привязки этой конечной точки службы, задав для привязки режим безопасности <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>. Для получения подробной информации [см.](../../../../docs/framework/wcf/feature-details/transport-security.md)  
  
3. Настройте новую конечную точку приложения для службы, используя созданную конфигурацию привязки. Подробную информацию о том, как добавить конечную точку обслуживания в файл конфигурации, можно узнать: [«Как: Создать конечную точку обслуживания в конфигурации.](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
  
4. Включите конечную точку метаданных HTTP/GET для своей службы. Для получения подробной информации [см. Как: Опубликовать метаданные для службы с помощью файла конфигурации](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано, как добавить конечную точку WCF, совместимую с ASP.NET веб-сервисом в коде и в качестве альтернативы в файлах конфигурации.  
  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Создание конечной точки службы в коде](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)
- [Практическое руководство. Публикация метаданных для службы с использованием кода](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)
- [Практическое руководство. Задание привязки службы в конфигурации](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)
- [Практическое руководство. Создание конечной точки службы в конфигурации](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)
- [Практическое руководство. Публикация метаданных для службы с использованием файла конфигурации](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [Транспортная безопасность](../../../../docs/framework/wcf/feature-details/transport-security.md)
- [Использование метаданных](../../../../docs/framework/wcf/feature-details/using-metadata.md)
