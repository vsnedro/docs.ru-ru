---
title: Практическое руководство. Извлечение данных и реализация совместимой службы
ms.date: 03/30/2017
ms.assetid: f6f3a2b9-c8aa-4b0b-832c-ec2927bf1163
ms.openlocfilehash: 6bd67ec8dcc0e73d097796b44974dce00b9a4eb2
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601222"
---
# <a name="how-to-retrieve-metadata-and-implement-a-compliant-service"></a>Практическое руководство. Извлечение данных и реализация совместимой службы
Часто разработку и реализацию служб выполняют разные люди. В средах, в которых приложения с возможностью взаимодействия имеют большое значение, контракты можно разработать или описать на языке WSDL, и разработчик должен реализовать службу, соответствующую предоставляемому контракту. Также может потребоваться перенести существующую службу в Windows Communication Foundation (WCF), но сохранить формат подключения. Кроме того, дуплексные контракты требуют, чтобы вызывающие стороны также реализовывали контракт обратного вызова.  
  
 В таких случаях необходимо использовать [средство служебной программы метаданных ServiceModel (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) (или аналогичное средство) для создания интерфейса контракта службы на управляемом языке, который можно реализовать для удовлетворения требований контракта. Обычно [средство служебной программы метаданных ServiceModel (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) используется для получения контракта службы, который используется с фабрикой каналов или типом клиента WCF, а также с файлом конфигурации клиента, который устанавливает правильную привязку и адрес. Чтобы использовать созданный файл конфигурации, следует изменить его на файл конфигурации службы. Также может возникнуть необходимость в изменении контракта службы.  
  
### <a name="to-retrieve-data-and-implement-a-compliant-service"></a>Извлечение данных и реализация совместимой службы  
  
1. Используйте [служебную программу метаданных ServiceModel (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) для файлов метаданных или конечную точку метаданных для создания файла кода.  
  
2. Найдите часть выходного файла кода, содержащую требуемый интерфейс (если имеется более одного), отмеченный атрибутом <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>. В следующем примере кода показаны два интерфейса, созданные [средством служебной программы метаданных ServiceModel (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md). Первый интерфейс (`ISampleService`) представляет собой интерфейс контракта службы, который реализуется, чтобы создать совместимую службу. Второй интерфейс (`ISampleServiceChannel`) представляет собой вспомогательный интерфейс, используемый для клиентов и расширяющий как интерфейс контракта службы, так и канал <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>, и используется в клиентском приложении.  
  
     [!code-csharp[ClientProxyCodeSample#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/proxycode.cs#2)]  
  
3. Если в языке WSDL не указано ответное действие для всех операций, свойству <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A> созданных контрактов операций может быть присвоено значение подстановочного знака (*). Удалите этот параметр свойства. В противном случае при реализации метаданных контракта службы метаданные невозможно будет экспортировать для этих операций.  
  
4. Реализуйте интерфейс для класса и разместите службу. Пример см. в статьях [как реализовать контракт службы](../how-to-implement-a-wcf-contract.md)или в разделе "пример" приведена простая реализация ниже.  
  
5. В файле конфигурации клиента, создаваемом [средством служебной программы метаданных ServiceModel (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) , измените [\<client>](../../configure-apps/file-schema/wcf/client.md) раздел конфигурации на [\<services>](../../configure-apps/file-schema/wcf/services.md) раздел конфигурации. (Пример созданного файла конфигурации клиентского приложения см. в следующем разделе "Пример".)  
  
6. В [\<services>](../../configure-apps/file-schema/wcf/services.md) разделе конфигурации создайте `name` атрибут в [\<services>](../../configure-apps/file-schema/wcf/services.md) разделе конфигурации для реализации службы.  
  
7. Присвойте атрибуту `name` службы имя конфигурации для реализации службы.  
  
8. Добавьте элементы конфигурации конечной точки, использующие реализованный контракт службы, в раздел конфигурации службы.  
  
## <a name="example"></a>Пример  
 В следующем примере кода показана большая часть файла кода, созданного путем запуска [средства служебной программы метаданных ServiceModel (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) в отношении файлов метаданных.  
  
 В коде демонстрируется следующее.  
  
- Интерфейс контракта службы, который после реализации отвечает требованиям контракта (`ISampleService`).  
  
- Вспомогательный интерфейс, используемый для клиентов и расширяющий как интерфейс контракта службы, так и канал <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>. Этот интерфейс используется в клиентском приложении (`ISampleServiceChannel`).  
  
- Вспомогательный класс, расширяющий класс <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType> и используемый в клиентском приложении (`SampleServiceClient`).  
  
- Файл конфигурации, созданный из службы.  
  
- Простая реализация службы `ISampleService`.  
  
- Преобразование файла конфигурации на стороне клиента в версию на стороне службы.  
  
[!code-csharp[ClientProxyCodeSample#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/proxycode.cs#1)]

[!code-xml[ClientProxyCodeSample#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/client.exe.config#10)]

[!code-csharp[ClientProxyCodeSample#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/hostapplication.cs#5)]

[!code-xml[ClientProxyCodeSample#20](../../../../samples/snippets/csharp/VS_Snippets_CFX/clientproxycodesample/cs/hostapplication.exe.config#20)]
  
## <a name="see-also"></a>Дополнительно

- [Служебное средство ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)
