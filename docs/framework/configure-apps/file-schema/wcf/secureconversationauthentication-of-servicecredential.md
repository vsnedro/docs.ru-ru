---
title: <secureConversationAuthentication> из <serviceCredential>
ms.date: 03/30/2017
ms.assetid: 0bd3fac7-befd-4a45-ba51-c200b33be0fd
ms.openlocfilehash: 336969c654f332ae3d838d8fd6d1c4243838539c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399945"
---
# <a name="secureconversationauthentication-of-servicecredential"></a><span data-ttu-id="fbfa7-102">\<secureConversationAuthentication> из \<serviceCredential></span><span class="sxs-lookup"><span data-stu-id="fbfa7-102">\<secureConversationAuthentication> of \<serviceCredential></span></span>
<span data-ttu-id="fbfa7-103">Задает параметры службы безопасного обмена данными.</span><span class="sxs-lookup"><span data-stu-id="fbfa7-103">Specifies the settings for a secure conversation service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<secureConversationAuthentication>**  
  
## <a name="syntax"></a><span data-ttu-id="fbfa7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fbfa7-104">Syntax</span></span>  
  
```xml  
<secureConversationAuthentication securityStateEncoderType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fbfa7-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fbfa7-105">Attributes and Elements</span></span>  
 <span data-ttu-id="fbfa7-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="fbfa7-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fbfa7-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fbfa7-107">Attributes</span></span>  
  
|<span data-ttu-id="fbfa7-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="fbfa7-108">Attribute</span></span>|<span data-ttu-id="fbfa7-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="fbfa7-109">Description</span></span>|  
|---------------|-----------------|  
|`securityStateEncoderType`|<span data-ttu-id="fbfa7-110">Строка, указывающая используемый тип <xref:System.ServiceModel.Security.SecurityStateEncoder>.</span><span class="sxs-lookup"><span data-stu-id="fbfa7-110">A string that specifies the type of <xref:System.ServiceModel.Security.SecurityStateEncoder> to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fbfa7-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fbfa7-111">Child Elements</span></span>  
 <span data-ttu-id="fbfa7-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="fbfa7-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fbfa7-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fbfa7-113">Parent Elements</span></span>  
  
|<span data-ttu-id="fbfa7-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="fbfa7-114">Element</span></span>|<span data-ttu-id="fbfa7-115">Описание</span><span class="sxs-lookup"><span data-stu-id="fbfa7-115">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="fbfa7-116">Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="fbfa7-116">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fbfa7-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="fbfa7-117">Remarks</span></span>  
 <span data-ttu-id="fbfa7-118">Данный элемент конфигурации используется для указания списка известных типов утверждений для сериализации файлов cookie маркера контекста безопасности (SCT), а также в качестве кодировщика для шифрования и защиты данных файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="fbfa7-118">Use this configuration element to specify a list of known claim types for the Security Context Token (SCT) cookies serialization, as well as an encoder to encode and secure cookies information.</span></span> <span data-ttu-id="fbfa7-119">Дополнительные сведения о маркерах контекста безопасности см. в разделе <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span><span class="sxs-lookup"><span data-stu-id="fbfa7-119">For more information on SCT, see <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbfa7-120">См. также</span><span class="sxs-lookup"><span data-stu-id="fbfa7-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Security.SecureConversationServiceCredential>
