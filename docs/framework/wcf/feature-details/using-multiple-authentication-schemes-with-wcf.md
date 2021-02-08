---
description: 'Дополнительные сведения: использование нескольких схем проверки подлинности в WCF'
title: Использование в WCF нескольких схем проверки подлинности
ms.date: 03/30/2017
ms.assetid: f32a56a0-e2b2-46bf-a302-29e1275917f9
ms.openlocfilehash: fd03a13c5d38bbf26e2b6079d1320bc389c9f20b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99779716"
---
# <a name="using-multiple-authentication-schemes-with-wcf"></a>Использование в WCF нескольких схем проверки подлинности

В WCF теперь можно указать несколько схем проверки подлинности на одной конечной точке. Кроме того, службы, размещенные на веб-серверах, могут наследовать свои параметры проверки подлинности непосредственно из IIS. Резидентные службы могут указывать, какие схемы проверки подлинности можно использовать. Дополнительные сведения о настройке параметров проверки подлинности в IIS см. в разделе [Проверка подлинности IIS](https://go.microsoft.com/fwlink/?LinkId=232458) .  
  
## <a name="iis-hosted-services"></a>Службы, размещенные в IIS  

 Для служб, размещенных в IIS, задайте схемы проверки подлинности, которые планируется использовать в IIS. Затем в файле web.config службы в конфигурации привязки укажите тип clientCredential в виде "InheritedFromHost", как показано в следующем фрагменте кода XML:  
  
```xml  
<bindings>  
      <basicHttpBinding>  
        <binding name="secureBinding">  
          <security mode="Transport">  
            <transport clientCredentialType="InheritedFromHost" />  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
```  
  
 Можно указать, что для службы необходимо использовать только подмножество схем проверки подлинности с помощью Сервицеаусентикатионбехавиор или \<serviceAuthenticationManager> элемента. Настраивая это в коде, используйте ServiceAuthenticationBehavior, как показано в следующем фрагменте кода.  
  
```csharp  
// ...  
ServiceAuthenticationBehavior sab = null;  
sab = serviceHost.Description.Behaviors.Find<ServiceAuthenticationBehavior>();  
  
if (sab == null)  
{  
    sab = new ServiceAuthenticationBehavior();  
    sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
    serviceHost.Description.Behaviors.Add(sab);  
}  
else  
{  
     sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
}  
// ...  
```  
  
 При настройке этого элемента в файле конфигурации используйте элемент, \<serviceAuthenticationManager> как показано в следующем фрагменте кода XML.  
  
```xml  
<behaviors>  
      <serviceBehaviors>  
        <behavior name="limitedAuthBehavior">  
          <serviceAuthenticationManager authenticationSchemes="Negotiate, Digest, Basic"/>  
          <!-- ... -->  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
```  
  
 Это гарантирует использование только подмножество перечисленных здесь схем проверки подлинности для применения на конечной точке службы в зависимости от того, что было выбрано на IIS. Это означает, что разработчик может исключить, например, простую проверку подлинности из списка путем исключения ее из списка serviceAuthenticationManager, и она не будет применена на конечной точке службы, даже если она активирована в IIS.  
  
## <a name="self-hosted-services"></a>Резидентные службы  

 Резидентные службы настраиваются несколько иначе, так как отсутствует наследование параметров из IIS. Здесь вы используете \<serviceAuthenticationManager> Element или сервицеаусентикатионбехавиор, чтобы указать параметры проверки подлинности, которые будут унаследованы. Соответствующий код выглядит следующим образом:  
  
```csharp  
// ...  
ServiceAuthenticationBehavior sab = null;  
sab = serviceHost.Description.Behaviors.Find<ServiceAuthenticationBehavior>();  
  
if (sab == null)  
{  
    sab = new ServiceAuthenticationBehavior();  
    sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
    serviceHost.Description.Behaviors.Add(sab);  
}  
else  
{  
     sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
}  
// ...  
```  
  
 В конфигурации это выглядит следующим образом:  
  
```xml  
<behaviors>  
      <serviceBehaviors>  
        <behavior name="limitedAuthBehavior">  
          <serviceAuthenticationManager authenticationSchemes="Negotiate, Digest, Basic"/>  
          <!-- ... -->  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
```  
  
 Затем можно указать InheritFromHost в параметрах привязки, как показано в следующем фрагменте кода XML.  
  
```xml  
<bindings>  
      <basicHttpBinding>  
        <binding name="secureBinding">  
          <security mode="Transport">  
            <transport clientCredentialType="InheritedFromHost" />  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
```  
  
 Кроме того, можно определить схемы проверки подлинности в пользовательской привязке, задав схемы проверки подлинности на элементе привязки транспорта HTTP, как показано в следующем фрагменте конфигурации.  
  
```xml  
<binding name="multipleBinding">  
      <textMessageEncoding/>  
      <httpTransport authenticationScheme="Negotiate, Ntlm, Digest, Basic" />  
    </binding>  
```  
  
## <a name="see-also"></a>См. также

- [Привязки и безопасность](bindings-and-security.md)
- [Конечные точки: адреса, привязки и контракты](endpoints-addresses-bindings-and-contracts.md)
- [Настройка привязок, предоставляемых системой](configuring-system-provided-bindings.md)
- [Возможности безопасности при использовании пользовательских привязок](security-capabilities-with-custom-bindings.md)
- [Привязки](bindings.md)
- [Пользовательские привязки](../extending/custom-bindings.md)
