---
title: Использование в WCF нескольких схем проверки подлинности
ms.date: 03/30/2017
ms.assetid: f32a56a0-e2b2-46bf-a302-29e1275917f9
ms.openlocfilehash: 3aae9bff4300af97f7b179d9d8115340a26e715a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289429"
---
# <a name="using-multiple-authentication-schemes-with-wcf"></a><span data-ttu-id="acf49-102">Использование в WCF нескольких схем проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="acf49-102">Using Multiple Authentication Schemes with WCF</span></span>

<span data-ttu-id="acf49-103">В WCF теперь можно указать несколько схем проверки подлинности на одной конечной точке.</span><span class="sxs-lookup"><span data-stu-id="acf49-103">WCF now allows you to specify multiple authentication schemes on a single endpoint.</span></span> <span data-ttu-id="acf49-104">Кроме того, службы, размещенные на веб-серверах, могут наследовать свои параметры проверки подлинности непосредственно из IIS.</span><span class="sxs-lookup"><span data-stu-id="acf49-104">Furthermore web hosted services can inherit their authentication settings directly from IIS.</span></span> <span data-ttu-id="acf49-105">Резидентные службы могут указывать, какие схемы проверки подлинности можно использовать.</span><span class="sxs-lookup"><span data-stu-id="acf49-105">Self-hosted services can specify what authentication schemes can be used.</span></span> <span data-ttu-id="acf49-106">Дополнительные сведения о настройке параметров проверки подлинности в IIS см. в разделе [Проверка подлинности IIS](https://go.microsoft.com/fwlink/?LinkId=232458) .</span><span class="sxs-lookup"><span data-stu-id="acf49-106">For more information about setting authentication settings in IIS, see [IIS Authentication](https://go.microsoft.com/fwlink/?LinkId=232458)</span></span>  
  
## <a name="iis-hosted-services"></a><span data-ttu-id="acf49-107">Службы, размещенные в IIS</span><span class="sxs-lookup"><span data-stu-id="acf49-107">IIS-Hosted Services</span></span>  

 <span data-ttu-id="acf49-108">Для служб, размещенных в IIS, задайте схемы проверки подлинности, которые планируется использовать в IIS.</span><span class="sxs-lookup"><span data-stu-id="acf49-108">For IIS-hosted services, set the authentication schemes you wish to use in IIS.</span></span> <span data-ttu-id="acf49-109">Затем в файле web.config службы в конфигурации привязки укажите тип clientCredential в виде "InheritedFromHost", как показано в следующем фрагменте кода XML:</span><span class="sxs-lookup"><span data-stu-id="acf49-109">Then in your service’s web.config file, in your binding configuration specify clientCredential type as "InheritedFromHost" as shown in the following XML snippet:</span></span>  
  
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
  
 <span data-ttu-id="acf49-110">Можно указать, что для службы необходимо использовать только подмножество схем проверки подлинности с помощью Сервицеаусентикатионбехавиор или \<serviceAuthenticationManager> элемента.</span><span class="sxs-lookup"><span data-stu-id="acf49-110">You can specify that you only want a subset of authentication schemes to be used with your service using the ServiceAuthenticationBehavior or the \<serviceAuthenticationManager> element.</span></span> <span data-ttu-id="acf49-111">Настраивая это в коде, используйте ServiceAuthenticationBehavior, как показано в следующем фрагменте кода.</span><span class="sxs-lookup"><span data-stu-id="acf49-111">When configuring this in code use the ServiceAuthenticationBehavior as shown in the following code snippet.</span></span>  
  
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
  
 <span data-ttu-id="acf49-112">При настройке этого элемента в файле конфигурации используйте элемент, \<serviceAuthenticationManager> как показано в следующем фрагменте кода XML.</span><span class="sxs-lookup"><span data-stu-id="acf49-112">When configuring this in a config file, use the \<serviceAuthenticationManager> element as shown in the following XML snippet.</span></span>  
  
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
  
 <span data-ttu-id="acf49-113">Это гарантирует использование только подмножество перечисленных здесь схем проверки подлинности для применения на конечной точке службы в зависимости от того, что было выбрано на IIS.</span><span class="sxs-lookup"><span data-stu-id="acf49-113">This will ensure that only a subset of the authentication schemes listed here will be considered for applying on the service endpoint, depending on what is selected in the IIS.</span></span> <span data-ttu-id="acf49-114">Это означает, что разработчик может исключить, например, простую проверку подлинности из списка путем исключения ее из списка serviceAuthenticationManager, и она не будет применена на конечной точке службы, даже если она активирована в IIS.</span><span class="sxs-lookup"><span data-stu-id="acf49-114">This means that a developer can exclude say Basic auth from the list by omitting it from the serviceAuthenticationManager listing and even if it is enabled in IIS, it will not be applied on the service endpoint</span></span>  
  
## <a name="self-hosted-services"></a><span data-ttu-id="acf49-115">Резидентные службы</span><span class="sxs-lookup"><span data-stu-id="acf49-115">Self-Hosted Services</span></span>  

 <span data-ttu-id="acf49-116">Резидентные службы настраиваются несколько иначе, так как отсутствует наследование параметров из IIS.</span><span class="sxs-lookup"><span data-stu-id="acf49-116">Self-hosted services are configured a bit differently since there is no IIS to inherit settings from.</span></span> <span data-ttu-id="acf49-117">Здесь вы используете \<serviceAuthenticationManager> Element или сервицеаусентикатионбехавиор, чтобы указать параметры проверки подлинности, которые будут унаследованы.</span><span class="sxs-lookup"><span data-stu-id="acf49-117">Here you use the \<serviceAuthenticationManager> element or ServiceAuthenticationBehavior to specify the authentication settings that will be inherited.</span></span> <span data-ttu-id="acf49-118">Соответствующий код выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="acf49-118">In code it looks like this:</span></span>  
  
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
  
 <span data-ttu-id="acf49-119">В конфигурации это выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="acf49-119">In config, it looks like this:</span></span>  
  
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
  
 <span data-ttu-id="acf49-120">Затем можно указать InheritFromHost в параметрах привязки, как показано в следующем фрагменте кода XML.</span><span class="sxs-lookup"><span data-stu-id="acf49-120">And then you can specify InheritFromHost in your binding settings as shown in the following XML snippet.</span></span>  
  
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
  
 <span data-ttu-id="acf49-121">Кроме того, можно определить схемы проверки подлинности в пользовательской привязке, задав схемы проверки подлинности на элементе привязки транспорта HTTP, как показано в следующем фрагменте конфигурации.</span><span class="sxs-lookup"><span data-stu-id="acf49-121">Alternatively, you can specify the authentication schemes in a custom binding, by setting the authentication schemes on the HTTP transport binding element, as shown in the following config snippet.</span></span>  
  
```xml  
<binding name="multipleBinding">  
      <textMessageEncoding/>  
      <httpTransport authenticationScheme="Negotiate, Ntlm, Digest, Basic" />  
    </binding>  
```  
  
## <a name="see-also"></a><span data-ttu-id="acf49-122">См. также</span><span class="sxs-lookup"><span data-stu-id="acf49-122">See also</span></span>

- [<span data-ttu-id="acf49-123">Привязки и безопасность</span><span class="sxs-lookup"><span data-stu-id="acf49-123">Bindings and Security</span></span>](bindings-and-security.md)
- [<span data-ttu-id="acf49-124">Конечные точки: адреса, привязки и контракты</span><span class="sxs-lookup"><span data-stu-id="acf49-124">Endpoints: Addresses, Bindings, and Contracts</span></span>](endpoints-addresses-bindings-and-contracts.md)
- [<span data-ttu-id="acf49-125">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="acf49-125">Configuring System-Provided Bindings</span></span>](configuring-system-provided-bindings.md)
- [<span data-ttu-id="acf49-126">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="acf49-126">Security Capabilities with Custom Bindings</span></span>](security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="acf49-127">Привязки</span><span class="sxs-lookup"><span data-stu-id="acf49-127">Bindings</span></span>](bindings.md)
- [<span data-ttu-id="acf49-128">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="acf49-128">Custom Bindings</span></span>](../extending/custom-bindings.md)
