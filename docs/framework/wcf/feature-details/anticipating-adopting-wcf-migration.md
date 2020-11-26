---
title: 'Планирование перехода на платформу Windows Communication Foundation: упрощение будущей миграции'
ms.date: 03/30/2017
ms.assetid: f49664d9-e9e0-425c-a259-93f0a569d01b
ms.openlocfilehash: bf3155f19e42787746d59ce7b593273522e2840a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96245059"
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-migration"></a>Планирование перехода на платформу Windows Communication Foundation: упрощение будущей миграции

Чтобы упростить миграцию новых приложений ASP.NET в WCF, следуйте приведенным выше рекомендациям, а также приведенным ниже рекомендациям.  
  
## <a name="protocols"></a>Протоколы  

 Отключите поддержку ASP.NET 2.0 для SOAP 1.2:  
  
```xml  
<configuration>  
     <system.web>  
      <webServices >  
          <protocols>  
           <remove name="HttpSoap12"/>  
          </protocols>
      </webServices>  
     </system.web>
</configuration>  
```  
  
 Это рекомендуется, так как WCF требует, чтобы сообщения, которые были согласованы с различными протоколами, например SOAP 1,1 и SOAP 1,2, могли использовать разные конечные точки. Если веб-служба ASP.NET 2,0 настроена для поддержки как SOAP 1,1, так и SOAP 1,2, которая является конфигурацией по умолчанию, то она не может быть перенесена в одну конечную точку WCF по исходному адресу, которая наверняка будет совместима со всеми существующими клиентами веб-службы ASP.NET. Кроме того, выбор версии SOAP 1.2 вместо версии 1.1 будет более строго ограничивать клиентуру службы.  
  
## <a name="service-development"></a>Разработка служб  

 WCF позволяет определять контракты служб, применяя <xref:System.ServiceModel.ServiceContractAttribute> либо к интерфейсам, либо к классам. Рекомендуется применять этот атрибут для интерфейса, а не для класса, поскольку при этом создается определение контракта, который может быть по-разному реализован любым количеством классов. ASP.NET 2.0 поддерживает возможность применения атрибута <xref:System.Web.Services.WebService> для интерфейсов и классов. Однако, как уже было сказано, в ASP.NET 2.0 существует недостаток, из-за которого параметр Namespace атрибута <xref:System.Web.Services.WebService> не имеет силы, если этот атрибут применяется для интерфейса, а не класса. Поскольку как правило, рекомендуется изменять пространство имен службы по умолчанию, `http://tempuri.org` используя параметр Namespace <xref:System.Web.Services.WebService> атрибута, он должен продолжить определение веб-служб ASP.NET, применяя <xref:System.ServiceModel.ServiceContractAttribute> атрибут к интерфейсам или к классам.  
  
- Обеспечьте минимально возможный код в методах, с помощью которых определяются эти интерфейсы. Заставьте их делегировать свою работу в другие классы. Новые типы служб WCF могут также делегировать свои важный работу этим классам.  
  
- Обеспечьте явные имена для операций службы, используя параметр `MessageName` атрибута <xref:System.Web.Services.WebMethodAttribute>.  
  
    ```csharp  
    [WebMethod(MessageName="ExplicitName")]  
    string Echo(string input);  
    ```  
  
     Это важно, так как имена по умолчанию для операций в ASP.NET отличаются от имен по умолчанию, предоставляемых WCF. Обеспечение явных имен исключает необходимость полагаться на имена по умолчанию.  
  
- Не реализуйте операции веб-службы ASP.NET с помощью полиморфизмных методов, так как WCF не поддерживает реализацию операций с методами с использованием полиморфизма.  
  
- Используйте атрибут <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>, чтобы обеспечить явные значения для заголовков SOAPAction HTTP, по которым запросы HTTP будут направляться в методы.  
  
    ```csharp  
    [WebMethod]  
    [SoapDocumentMethod(RequestElementName="ExplicitAction")]  
    string Echo(string input);  
    ```  
  
     При использовании этого подхода не придется полагаться на значения SOAPAction по умолчанию, используемые ASP.NET и WCF.  
  
- Избегайте использования расширений SOAP. Если требуются расширения SOAP, определите, является ли цель, для которой они считаются, функцией, уже предоставляемой WCF. Если это действительно так, снова рассмотрите вариант выбора, чтобы не внедрять WCF немедленно.  
  
## <a name="state-management"></a>Управление состоянием  

 Избегайте поддержания состояния в службах. Не только поддержание состояния, как правило, нарушает масштабируемость приложения, но механизмы управления состоянием ASP.NET и WCF сильно отличаются, хотя WCF поддерживает механизмы ASP.NET в режиме совместимости ASP.NET.  
  
## <a name="exception-handling"></a>Обработка исключений  

 При разработке структур типов данных, которые должны передаваться и приниматься службой, разработайте также структуры для представления различных типов исключений, которые могут происходить в службе и подлежать передаче клиенту.  
  
```csharp  
[Serializable]  
[XmlRoot(Namespace="ExplicitNamespace", IsNullable=true)]  
public partial class AnticipatedException
{
    private string anticipatedExceptionInformationField;  

    public string AnticipatedExceptionInformation
    {  
        get {
            return this.anticipatedExceptionInformationField;  
        }  
        set {  
            this.anticipatedExceptionInformationField = value;  
        }  
    }  
}  
```  
  
 Предоставьте таким классам возможность сериализовать себя в XML:  
  
```csharp  
public XmlNode ToXML()  
{  
     XmlSerializer serializer = new XmlSerializer(  
      typeof(AnticipatedException));  
     MemoryStream memoryStream = new MemoryStream();  
     XmlTextWriter writer = new XmlTextWriter(  
     memoryStream, UnicodeEncoding.UTF8);  
     serializer.Serialize(writer, this);  
     XmlDocument document = new XmlDocument();  
     document.LoadXml(new string(  
     UnicodeEncoding.UTF8.GetChars(  
     memoryStream.GetBuffer())).Trim());  
    return document.DocumentElement;  
}  
```  
  
 Затем классы могут использоваться для предоставления сведений в отношении явно вызванных экземпляров <xref:System.Web.Services.Protocols.SoapException>:  
  
```csharp  
AnticipatedException exception = new AnticipatedException();  
exception.AnticipatedExceptionInformation = "…";  
throw new SoapException(  
     "Fault occurred",  
     SoapException.ClientFaultCode,  
     Context.Request.Url.AbsoluteUri,  
     exception.ToXML());  
```  
  
 Эти классы исключений можно легко использовать с <xref:System.ServiceModel.FaultException%601> классом WCF для создания нового `FaultException<AnticipatedException>(anticipatedException);`  
  
## <a name="security"></a>Безопасность  

 Ниже приведены некоторые рекомендации по безопасности.  
  
- Избегайте использования профилей ASP.NET 2,0, так как их использование приведет к ограничению использования режима интеграции ASP.NET, если служба была перенесена в WCF.  
  
- Избегайте использования списков управления доступом для управления доступом к службам, так как ASP.NET веб-службы поддерживают списки ACL с помощью службы IIS (IIS), WCF не — так как веб-службы ASP.NET зависят от служб IIS для размещения, и WCF не обязательно должна размещаться в IIS.  
  
- Не принимайте во внимание использование поставщиков ролей ASP.NET 2.0 для авторизации доступа к ресурсам службы.  
  
## <a name="see-also"></a>См. также

- [Планирование перехода на платформу Windows Communication Foundation: упрощение будущей интеграции](anticipating-adopting-the-wcf-easing-future-integration.md)
