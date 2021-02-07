---
description: Дополнительные сведения см. в статье как использовать поставщик роли диспетчера авторизации ASP.NET со службой.
title: Практическое руководство. Использование поставщика ролей диспетчера авторизации ASP.NET со службой
ms.date: 03/30/2017
ms.assetid: f21deb81-91ef-49ef-94d6-494785143271
ms.openlocfilehash: 24d6bbbf2181189104fb0df0068130c402fd2f68
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99734130"
---
# <a name="how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service"></a>Практическое руководство. Использование поставщика ролей диспетчера авторизации ASP.NET со службой

При размещении веб-службы в ASP.NET можно интегрировать диспетчер авторизации в приложение, чтобы обеспечить авторизацию для службы. Диспетчер авторизации позволяет разработчику приложения определить отдельные операции, которые можно сгруппировать для образования задач. Администратор затем может авторизовать роли на выполнение определенных задач или отдельных операций. Диспетчер авторизации предоставляет средство администрирования в виде оснастки консоли управления (MMC) для управления ролями, задачами, операциями и пользователями. Администратор может настроить хранилище политик диспетчера авторизации в XML-файле, Active Directory или в хранилище Active Directory Application Mode (ADAM).  
  
 Диспетчер авторизации интегрирован в приложение путем настройки поставщика роли ASP.NET диспетчера авторизации для приложения ASP.NET, в котором размещена веб-служба. Как и другие поставщики ролей ASP.NET, поставщик роли диспетчера авторизации ASP.NET настраивается с помощью `providers` элемента> <.  
  
 Следующий пример кода представляет собой отрывок файла конфигурации для веб-службы, за счет которого диспетчер авторизации интегрируется в приложение.  
  
```xml  
<system.web>  
    <roleManager enabled="true" defaultProvider="AzManRoleProvider">  
      <providers>  
        <add name="AzManRoleProvider"  
             type="System.Web.Security.AuthorizationStoreRoleProvider, System.Web, Version=2.0.0.0, Culture=neutral, publicKeyToken=b03f5f7f11d50a3a"  
             connectionStringName="AzManPolicyStoreConnectionString"
             applicationName="SecureService"/>  
      </providers>  
    </roleManager>  
</system.web>  
```  
  
 Дополнительные сведения об интеграции поставщика ролей ASP.NET с приложением WCF см. [в разделе как использовать поставщик ролей ASP.NET со службой](how-to-use-the-aspnet-role-provider-with-a-service.md). Дополнительные сведения об использовании диспетчера авторизации с ASP.NET см. [в разделе как использовать диспетчер авторизации (AzMan) с ASP.NET 2,0](/previous-versions/msp-n-p/ff649313(v=pandp.10)).  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Использование поставщика ролей ASP.NET со службой](how-to-use-the-aspnet-role-provider-with-a-service.md)
