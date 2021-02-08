---
description: Дополнительные сведения об интеграции System. Web. Routing
title: Интеграция с System.Web.Routing
ms.date: 03/30/2017
ms.assetid: 31fe2a4f-5c47-4e5d-8ee1-84c524609d41
ms.openlocfilehash: 8f396d5a3cad30f5cc67cb0cf44fad76a0bb54c9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793341"
---
# <a name="systemwebrouting-integration"></a>Интеграция с System.Web.Routing

При размещении службы Windows Communication Foundation (WCF) в службе IIS вы размещаете SVC-файл в виртуальном каталоге. Этот SVC-файл указывает фабрику узла службы, которую необходимо использовать, а также класс, реализующий эту службу. При выполнении запросов к службе вы задаете SVC файл в URI, например: `http://contoso.com/EmployeeServce.svc` . Для разработчиков служб REST такой тип URI не является оптимальным. URI для служб REST указывают определенный ресурс и обычно не имеют модулей. <xref:System.Web.Routing>Функция интеграции позволяет разместить службу WCF RESTful, которая реагирует на URI без расширения. Дополнительные сведения о маршрутизации см. в разделе [ASP.NET Routing](/previous-versions/aspnet/cc668201(v=vs.100)).  
  
## <a name="using-systemwebrouting-integration"></a>Использование интеграции System.Web.Routing  

 Для использования возможности интеграции <xref:System.Web.Routing> с помощью класса <xref:System.ServiceModel.Activation.ServiceRoute> создайте один или несколько маршрутов и добавьте их в <xref:System.Web.Routing.RouteTable> в файле Global.asax. Это маршруты указывают относительные URI, по которым отвечает служба. В приведенном ниже примере показано, как это сделать.  
  
```aspx-csharp  
<%@ Application Language="C#" %>  
<%@ Import Namespace="System.Web.Routing" %>  
<%@ Import Namespace="System.ServiceModel.Activation" %>  
<%@ Import Namespace="System.ServiceModel.Web " %>  
  
<script RunAt="server">  
    void Application_Start(object sender, EventArgs e)  
    {  
        RegisterRoutes(RouteTable.Routes);  
    }  
  
    private void RegisterRoutes(RouteCollection routes)  
    {  
        routes.Add(new ServiceRoute("Customers", new WebServiceHostFactory(), typeof(Service)));
   }  
</script>  
```  
  
 Все запросы направляются по относительному URI, который начинается с Customers службы `Service`.  
  
 В файл Web.config необходимо добавить модуль `System.Web.Routing.UrlRoutingModule`, установить атрибут `runAllManagedModulesForAllRequests` в значение `true` и добавить обработчик `UrlRoutingHandler` в элемент`<system.webServer>`, как показано в следующем примере.  
  
```xml  
<system.webServer>  
      <modules runAllManagedModulesForAllRequests="true">  
        <add name="UrlRoutingModule" type="System.Web.Routing.UrlRoutingModule, System.Web, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a" />  
      </modules>  
      <handlers>  
        <add name="UrlRoutingHandler" preCondition="integratedMode" verb="*" path="UrlRouting.axd"/>  
      </handlers>  
    </system.webServer>  
```  
  
 Это позволит загрузить модуль и обработчик, которые необходимы для маршрутизации. Дополнительные сведения см. в разделе [Маршрутизация](routing.md). Необходимо также установить атрибут `aspNetCompatibilityEnabled` в значение `true` в элементе `<serviceHostingEnvironment>`, как показано в следующем примере.  
  
```xml  
<system.serviceModel>  
    <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>  
        <!-- ... -->  
    </system.serviceModel>  
```  
  
 Класс, реализующий службу, должен соответствовать требованиям к совместимости ASP.NET, как показано в следующем примере.  
  
```csharp
[ServiceContract]  
[AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Allowed)]  
    public class Service  
    {  
        // ...  
    }  
```  
  
## <a name="see-also"></a>См. также

- [Модель веб-программирования HTTP WCF](wcf-web-http-programming-model.md)
- [Маршрутизация ASP.NET](/previous-versions/aspnet/cc668201(v=vs.100))
