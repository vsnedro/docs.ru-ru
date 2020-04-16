---
title: Взаимодействие с веб-службами ASP.NET
ms.date: 03/30/2017
ms.assetid: 622422f8-6651-442f-b8be-e654a4aabcac
ms.openlocfilehash: 41810d8044e4b7ff3193950a914edbf1e61cffb1
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2020
ms.locfileid: "81464089"
---
# <a name="interoperability-with-aspnet-web-services"></a>Взаимодействие с веб-службами ASP.NET
Совместимость между ASP.NET Web-сервисов и веб-сервисами Windows Communication Foundation (WCF) может быть достигнута путем обеспечения соответствия услуг, реализованных с использованием обеих технологий, спецификации WS-I Basic Profile 1.1. ASP.NET web-сервисов, которые соответствуют БАЗОВОму профилю WS-I 1.1, совместимы с <xref:System.ServiceModel.BasicHttpBinding>клиентами WCF с помощью системы WCF, предоставляемой привязкой.  
  
 Используйте ASP.NET 2.0 <xref:System.Web.Services.WebService> вариант <xref:System.Web.Services.WebMethodAttribute> добавления и атрибутов в интерфейс, а не к классу, и написания класса для реализации интерфейса, как показано в следующем примере кода.  
  
```csharp
[WebService]  
public interface IEcho  
{  
    [WebMethod]  
    string Echo(string input);  
}  
  
public class Service : IEcho  
{  
  
   public string Echo(string input)  
   {  
        return input;  
    }  
}  
```  
  
 Использование этого варианта предпочтительно, так как интерфейс с атрибутом <xref:System.Web.Services.WebService> составляет контракт для операций, выполняемых службой, доступный для повторного использования в различных классах, которые могут реализовывать этот же контракт другими способами.  
  
 Избегайте использования атрибута <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> для маршрутизации сообщений методами по полному имени элемента текста сообщения протокола SOAP, а не по заголовку HTTP `SOAPAction`. WCF использует `SOAPAction` заголовок HTTP для заголовка сообщений.  
  
 XML-код, в который тип сериализуется сериализатором <xref:System.Xml.Serialization.XmlSerializer>, по умолчанию семантически идентичен XML-коду, в который тип сериализуется сериализатором <xref:System.Runtime.Serialization.DataContractSerializer>, при условии, что пространство имен для XML задано явным образом. При определении типа данных для использования в службах ASP.NETWeb в ожидании принятия WCF сделайте следующее:  
  
- Задавайте тип с использованием классов .NET Framework, а не схемы XML.  
  
- Добавляйте в класс только атрибуты <xref:System.SerializableAttribute> и <xref:System.Xml.Serialization.XmlRootAttribute>, используя последний для явного задания пространства имен для типа. Не добавляйте дополнительные атрибуты из пространства имен <xref:System.Xml.Serialization> для задания способа преобразования класса .NET Framework в XML.  
  
- Используя этот подход, вы впоследствии сможете превратить классы .NET в контракты данных, добавив атрибуты <xref:System.Runtime.Serialization.DataContractAttribute> и <xref:System.Runtime.Serialization.DataMemberAttribute>, без значительного изменения XML-кода, в который классы сериализуются для передачи. Типы, используемые в сообщениях ASP.NET Web-сервисов, могут обрабатываться в виде контрактов с данными приложениями WCF, что, среди прочего, дает более высокую производительность в приложениях WCF.  
  
 Избегайте использования параметров проверки подлинности, предусмотренных в службах IIS. Клиенты WCF не поддерживают их. Если служба должна быть защищена, используйте опции, предоставляемые WCF, потому что эти параметры являются надежными и основаны на стандартных протоколах.  
  
## <a name="performance-impact-caused-by-loading-the-servicemodel-httpmodule"></a>Влияние загрузки модуля ServiceModel HttpModule на производительность  
 В платформе .NET Framework 3.0 модуль WCF `HttpModule` устанавливался в корневой файл Web.config таким образом, что любое приложение ASP.NET поддерживало WCF. Это может влиять на производительность, поэтому можно удалить `ServiceModel` из файла Web.config, как показано в следующем примере.  
  
```xml  
<httpModules>  
    <remove name="ServiceModel" />  
</httpModules>
```  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Настройка службы WCF для взаимодействия с клиентами веб-службы ASP.NET](../../../../docs/framework/wcf/feature-details/config-wcf-service-with-aspnet-web-service.md)
