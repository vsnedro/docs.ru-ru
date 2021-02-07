---
description: Дополнительные сведения см. в статье как использовать поставщик ролей ASP.NET со службой.
title: Практическое руководство. Использование поставщика ролей ASP.NET со службой
ms.date: 03/30/2017
ms.assetid: 88d33a81-8ac7-48de-978c-5c5b1257951e
ms.openlocfilehash: 24bf9ad72d3634baf1d7120e4e60ccde5a4078a9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99734117"
---
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a>Практическое руководство. Использование поставщика ролей ASP.NET со службой

Поставщик ролей ASP.NET (в сочетании с поставщиком членства ASP.NET) — это функция, позволяющая разработчикам ASP.NET создавать веб-сайты, позволяющие пользователям создавать учетную запись с сайтом и назначать роли для авторизации. Эта возможность позволяет любому пользователю создать на сайте учетную запись и при входе получать монопольный доступ к сайту и его службам. В этом заключается отличие от безопасности Windows, по условиям которой пользователи обязаны создавать ученые записи в домене Windows. Вместо этого любой пользователь, предоставляющий свои учетные данные (сочетание имени пользователя и пароля), может использовать сайт и его службы.  
  
Пример приложения см. в разделе [поставщик членства и роли](../samples/membership-and-role-provider.md). Дополнительные сведения о функции поставщика членства в ASP.NET см. в разделе [как использовать поставщик членства ASP.NET](how-to-use-the-aspnet-membership-provider.md).  
  
Возможность поставщика ролей использует базу данных SQL Server для хранения информации о пользователях. Разработчики Windows Communication Foundation (WCF) могут воспользоваться преимуществами этих функций в целях обеспечения безопасности. При интеграции в приложение WCF пользователи должны указать сочетание имени пользователя и пароля для клиентского приложения WCF. Чтобы позволить WCF использовать базу данных, необходимо создать экземпляр <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> класса, установить его <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> свойство в значение <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles> и добавить экземпляр в коллекцию поведений в <xref:System.ServiceModel.ServiceHost> , где размещена служба.  
  
## <a name="configure-the-role-provider"></a>Настройка поставщика ролей  
  
1. В файле Web.config в `system.web` элементе <> добавьте `roleManager` элемент <> и присвойте его `enabled` атрибуту значение `true` .  
  
2. Задайте для атрибута `defaultProvider` значение `SqlRoleProvider`.  
  
3. В качестве дочернего `roleManager` элемента <> добавьте `providers` элемент <>.  
  
4. В качестве дочернего `providers` элемента <> добавьте `add` элемент <> со следующими атрибутами, для которых заданы соответствующие значения: `name` , `type` , `connectionStringName` и `applicationName` , как показано в следующем примере.  
  
    ```xml  
    <!-- Configure the Sql Role Provider. -->  
    <roleManager enabled ="true"
     defaultProvider ="SqlRoleProvider" >  
       <providers>  
         <add name ="SqlRoleProvider"
           type="System.Web.Security.SqlRoleProvider"
           connectionStringName="SqlConn"
           applicationName="MembershipAndRoleProviderSample"/>  
       </providers>  
    </roleManager>  
    ```  
  
## <a name="configure-the-service-to-use-the-role-provider"></a>Настройка службы для использования поставщика ролей  
  
1. В файле Web.config добавьте [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) элемент.  
  
2. Добавьте [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) элемент в `system.ServiceModel` элемент> <.  
  
3. Добавьте в [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) `behaviors` элемент> <.  
  
4. Добавьте [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) элемент и присвойте `name` атрибуту соответствующее значение.  
  
5. Добавьте в [\<serviceAuthorization>](../../configure-apps/file-schema/wcf/serviceauthorization-element.md) `behavior` элемент> <.  
  
6. Задайте для атрибута `principalPermissionMode` значение `UseAspNetRoles`.  
  
7. Задайте для атрибута `roleProviderName` значение `SqlRoleProvider`. В следующем примере показан фрагмент файла конфигурации.  
  
    ```xml  
    <behaviors>  
     <serviceBehaviors>  
      <behavior name="CalculatorServiceBehavior">  
       <serviceAuthorization principalPermissionMode ="UseAspNetRoles"  
                             roleProviderName ="SqlRoleProvider" />  
      </behavior>  
     </serviceBehaviors>  
    </behaviors>  
    ```  
  
## <a name="see-also"></a>См. также

- [Поставщик членства и ролей](../samples/membership-and-role-provider.md)
- [Практическое руководство. Использование поставщика членства ASP.NET](how-to-use-the-aspnet-membership-provider.md)
