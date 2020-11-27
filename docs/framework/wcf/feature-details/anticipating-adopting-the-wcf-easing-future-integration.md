---
title: 'Планирование перехода на платформу Windows Communication Foundation: упрощение будущей интеграции'
ms.date: 03/30/2017
ms.assetid: 3028bba8-6355-4ee0-9ecd-c56e614cb474
ms.openlocfilehash: ead28354a3687bcca22a1a0eb5ccc9f15f0c69d2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266575"
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-integration"></a>Планирование перехода на платформу Windows Communication Foundation: упрощение будущей интеграции

Если вы используете ASP.NET сегодня и предложит использовать WCF в будущем, в этом разделе приводятся рекомендации по обеспечению совместной работы новых веб-служб ASP.NET и приложений WCF.  
  
## <a name="general-recommendations"></a>Основные рекомендации  

 Используйте для создания новых служб ASP.NET 2.0. Это обеспечит доступ к усовершенствованиям, появившимся в новой версии. Тем не менее он также позволяет использовать компоненты ASP.NET 2,0 вместе с компонентами WCF в одном приложении.  
  
## <a name="protocols"></a>Протоколы  

 Используйте новую функцию ASP.NET 2.0 для проверки соответствия спецификации WS-I Basic Profile 1.1:  
  
```csharp  
[WebService(Namespace = "http://tempuri.org/")]  
[WebServiceBinding(  
     ConformsTo = WsiProfiles.BasicProfile1_1,  
     EmitConformanceClaims=true)]  
public interface IEcho  
```  
  
 Веб-службы ASP.NET, которые соответствуют стандартному профилю WS-I 1,1, будут взаимодействовать с клиентами WCF с помощью предопределенной привязки WCF, <xref:System.ServiceModel.BasicHttpBinding> .  
  
## <a name="service-development"></a>Разработка служб  

 Избегайте использования атрибута <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> для маршрутизации сообщений методами по полному имени элемента текста сообщения протокола SOAP вместо заголовка HTTP SOAPAction. WCF использует заголовок SOAPAction HTTP для маршрутизации сообщений.  
  
## <a name="data-representation"></a>Представление данных  

 XML-код, в который тип сериализуется сериализатором <xref:System.Xml.Serialization.XmlSerializer>, по умолчанию семантически идентичен XML-коду, в который тип сериализуется сериализатором <xref:System.Runtime.Serialization.DataContractSerializer>, при условии, что пространство имен для XML задано явным образом. При определении типа данных для использования с веб-службами ASP.NET в будущем для внедрения WCF выполните следующие действия.  
  
1. Задавайте тип с использованием классов .NET Framework, а не схемы XML.  
  
2. Добавляйте в класс только атрибуты <xref:System.SerializableAttribute> и <xref:System.Xml.Serialization.XmlRootAttribute>, используя последний для явного задания пространства имен для типа. Не добавляйте дополнительные атрибуты из пространства имен <xref:System.Xml.Serialization> для задания способа преобразования класса .NET Framework в XML.  
  
 Используя этот подход, вы впоследствии сможете превратить классы .NET в контракты данных, добавив атрибуты <xref:System.Runtime.Serialization.DataContractAttribute> и <xref:System.Runtime.Serialization.DataMemberAttribute>, без значительного изменения XML-кода, в который классы сериализуются для передачи. Типы, используемые в сообщениях ASP.NET веб-служб, будут обрабатываться в виде контрактов данных приложениями WCF, а также с другими преимуществами, более высокой производительностью в приложениях WCF.  
  
## <a name="security"></a>Безопасность  

 Избегайте использования параметров проверки подлинности, предусмотренных в службах IIS. Клиенты WCF не поддерживают их. Если необходимо обеспечить защиту службы, используйте параметры, предоставляемые WCF, так как эти параметры расширены и основаны на стандартных протоколах.  
  
## <a name="see-also"></a>См. также

- [Планирование перехода на платформу Windows Communication Foundation: упрощение будущей миграции](anticipating-adopting-wcf-migration.md)
