---
title: Практическое руководство. Указание типа учетных данных клиента
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security credentials, adding to SOAP messages
- WCF, security
ms.assetid: 10f51bee-5f92-4c1a-9126-fa5418535d8f
ms.openlocfilehash: b45d7b58d8a1fe79f9d7a8cff6e328b46633985c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293680"
---
# <a name="how-to-specify-the-client-credential-type"></a><span data-ttu-id="c4d1e-102">Практическое руководство. Указание типа учетных данных клиента</span><span class="sxs-lookup"><span data-stu-id="c4d1e-102">How to: Specify the Client Credential Type</span></span>

<span data-ttu-id="c4d1e-103">После установки режима безопасности (на уровне транспорта или сообщений) можно установить тип учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="c4d1e-103">After setting a security mode (either transport or message), you have the option of setting the client credential type.</span></span> <span data-ttu-id="c4d1e-104">Это свойство определяет тип учетных данных, которые клиент должен предоставить службе для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="c4d1e-104">This property specifies what type of credential the client must provide to the service for authentication.</span></span> <span data-ttu-id="c4d1e-105">Дополнительные сведения о настройке режима безопасности (необходимого шага перед настройкой типа учетных данных клиента) см. [в разделе как задать режим безопасности](how-to-set-the-security-mode.md).</span><span class="sxs-lookup"><span data-stu-id="c4d1e-105">For more information about setting the security mode (a necessary step before setting the client credential type), see [How to: Set the Security Mode](how-to-set-the-security-mode.md).</span></span>  
  
### <a name="to-set-the-client-credential-type-in-code"></a><span data-ttu-id="c4d1e-106">Установка типа учетных данных клиента в коде</span><span class="sxs-lookup"><span data-stu-id="c4d1e-106">To set the client credential type in code</span></span>  
  
1. <span data-ttu-id="c4d1e-107">Создайте экземпляр привязки, который будет использовать служба.</span><span class="sxs-lookup"><span data-stu-id="c4d1e-107">Create an instance of the binding that the service will use.</span></span> <span data-ttu-id="c4d1e-108">В этом примере используется привязка <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="c4d1e-108">This example uses the <xref:System.ServiceModel.WSHttpBinding> binding.</span></span>  
  
2. <span data-ttu-id="c4d1e-109">Присвойте свойству <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="c4d1e-109">Set the <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> property to an appropriate value.</span></span> <span data-ttu-id="c4d1e-110">В этом примере используется режим Message.</span><span class="sxs-lookup"><span data-stu-id="c4d1e-110">This example uses the Message mode.</span></span>  
  
3. <span data-ttu-id="c4d1e-111">Присвойте свойству <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="c4d1e-111">Set the <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> property to an appropriate value.</span></span> <span data-ttu-id="c4d1e-112">В этом примере используется проверка подлинности Windows (<xref:System.ServiceModel.MessageCredentialType.Windows>).</span><span class="sxs-lookup"><span data-stu-id="c4d1e-112">This example sets it to use Windows authentication (<xref:System.ServiceModel.MessageCredentialType.Windows>).</span></span>  
  
     [!code-csharp[c_ProgrammingSecurity#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#14)]
     [!code-vb[c_ProgrammingSecurity#14](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#14)]  
  
### <a name="to-set-the-client-credential-type-in-configuration"></a><span data-ttu-id="c4d1e-113">Установка типа учетных данных клиента в файле конфигурации</span><span class="sxs-lookup"><span data-stu-id="c4d1e-113">To set the client credential type in configuration</span></span>  
  
1. <span data-ttu-id="c4d1e-114">Добавьте [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) элемент в файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c4d1e-114">Add a [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) element to the configuration file.</span></span>  
  
2. <span data-ttu-id="c4d1e-115">Добавьте элемент в качестве дочернего элемента [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) .</span><span class="sxs-lookup"><span data-stu-id="c4d1e-115">As a child element, add a [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) element.</span></span>  
  
3. <span data-ttu-id="c4d1e-116">Добавьте соответствующую привязку.</span><span class="sxs-lookup"><span data-stu-id="c4d1e-116">Add an appropriate binding.</span></span> <span data-ttu-id="c4d1e-117">В этом примере используется [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="c4d1e-117">This example uses the [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>  
  
4. <span data-ttu-id="c4d1e-118">Добавьте [\<binding>](../configure-apps/file-schema/wcf/bindings.md) элемент и присвойте `name` атрибуту соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="c4d1e-118">Add a [\<binding>](../configure-apps/file-schema/wcf/bindings.md) element and set the `name` attribute to an appropriate value.</span></span> <span data-ttu-id="c4d1e-119">В этом примере используется имя "SecureBinding".</span><span class="sxs-lookup"><span data-stu-id="c4d1e-119">This example uses the name "SecureBinding".</span></span>  
  
5. <span data-ttu-id="c4d1e-120">Добавьте привязку `<security>`.</span><span class="sxs-lookup"><span data-stu-id="c4d1e-120">Add a `<security>` binding.</span></span> <span data-ttu-id="c4d1e-121">Присвойте атрибуту `mode` соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="c4d1e-121">Set the `mode` attribute to an appropriate value.</span></span> <span data-ttu-id="c4d1e-122">В данном примере используется значение `"Message"`.</span><span class="sxs-lookup"><span data-stu-id="c4d1e-122">This example sets it to `"Message"`.</span></span>  
  
6. <span data-ttu-id="c4d1e-123">Добавьте элемент `<message>` или `<transport>` в зависимости от режима безопасности.</span><span class="sxs-lookup"><span data-stu-id="c4d1e-123">Add either a `<message>` or `<transport>` element, as determined by the security mode.</span></span> <span data-ttu-id="c4d1e-124">Присвойте атрибуту `clientCredentialType` соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="c4d1e-124">Set the `clientCredentialType` attribute to an appropriate value.</span></span> <span data-ttu-id="c4d1e-125">В этом примере используется `"Windows"`.</span><span class="sxs-lookup"><span data-stu-id="c4d1e-125">This example uses `"Windows"`.</span></span>  
  
    ```xml  
    <system.serviceModel>  
      <bindings>  
        <wsHttpBinding>  
          <binding name="SecureBinding">  
            <security mode="Message">  
                 <message clientCredentialType="Windows" />  
             </security>  
          </binding>  
        </wsHttpBinding>  
      </bindings>  
    </system.serviceModel>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c4d1e-126">См. также</span><span class="sxs-lookup"><span data-stu-id="c4d1e-126">See also</span></span>

- [<span data-ttu-id="c4d1e-127">Защита служб</span><span class="sxs-lookup"><span data-stu-id="c4d1e-127">Securing Services</span></span>](securing-services.md)
- [<span data-ttu-id="c4d1e-128">Практическое руководство. Задание режима безопасности</span><span class="sxs-lookup"><span data-stu-id="c4d1e-128">How to: Set the Security Mode</span></span>](how-to-set-the-security-mode.md)
