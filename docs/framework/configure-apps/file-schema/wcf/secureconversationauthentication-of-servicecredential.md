---
title: <secureConversationAuthentication> из <serviceCredential>
ms.date: 03/30/2017
ms.assetid: 0bd3fac7-befd-4a45-ba51-c200b33be0fd
ms.openlocfilehash: be2a9298a78de1503271f41076b9f5bb63c73f74
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91162247"
---
# <a name="secureconversationauthentication-of-servicecredential"></a><span data-ttu-id="6f1b3-102">\<secureConversationAuthentication> из \<serviceCredential></span><span class="sxs-lookup"><span data-stu-id="6f1b3-102">\<secureConversationAuthentication> of \<serviceCredential></span></span>

<span data-ttu-id="6f1b3-103">Задает параметры службы безопасного обмена данными.</span><span class="sxs-lookup"><span data-stu-id="6f1b3-103">Specifies the settings for a secure conversation service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<secureConversationAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="6f1b3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6f1b3-104">Syntax</span></span>  
  
```xml  
<secureConversationAuthentication securityStateEncoderType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6f1b3-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6f1b3-105">Attributes and Elements</span></span>  

 <span data-ttu-id="6f1b3-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6f1b3-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6f1b3-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6f1b3-107">Attributes</span></span>  
  
|<span data-ttu-id="6f1b3-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6f1b3-108">Attribute</span></span>|<span data-ttu-id="6f1b3-109">Описание</span><span class="sxs-lookup"><span data-stu-id="6f1b3-109">Description</span></span>|  
|---------------|-----------------|  
|`securityStateEncoderType`|<span data-ttu-id="6f1b3-110">Строка, указывающая используемый тип <xref:System.ServiceModel.Security.SecurityStateEncoder>.</span><span class="sxs-lookup"><span data-stu-id="6f1b3-110">A string that specifies the type of <xref:System.ServiceModel.Security.SecurityStateEncoder> to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6f1b3-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6f1b3-111">Child Elements</span></span>  

 <span data-ttu-id="6f1b3-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="6f1b3-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6f1b3-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6f1b3-113">Parent Elements</span></span>  
  
|<span data-ttu-id="6f1b3-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="6f1b3-114">Element</span></span>|<span data-ttu-id="6f1b3-115">Описание</span><span class="sxs-lookup"><span data-stu-id="6f1b3-115">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="6f1b3-116">Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="6f1b3-116">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f1b3-117">Remarks</span><span class="sxs-lookup"><span data-stu-id="6f1b3-117">Remarks</span></span>  

 <span data-ttu-id="6f1b3-118">Данный элемент конфигурации используется для указания списка известных типов утверждений для сериализации файлов cookie маркера контекста безопасности (SCT), а также в качестве кодировщика для шифрования и защиты данных файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="6f1b3-118">Use this configuration element to specify a list of known claim types for the Security Context Token (SCT) cookies serialization, as well as an encoder to encode and secure cookies information.</span></span> <span data-ttu-id="6f1b3-119">Дополнительные сведения о маркерах контекста безопасности см. в разделе <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span><span class="sxs-lookup"><span data-stu-id="6f1b3-119">For more information on SCT, see <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f1b3-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6f1b3-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Security.SecureConversationServiceCredential>
