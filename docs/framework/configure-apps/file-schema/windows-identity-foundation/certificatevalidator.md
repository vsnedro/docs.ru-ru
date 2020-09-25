---
title: <certificateValidator>
ms.date: 03/30/2017
ms.assetid: 86161897-c20f-4ad8-9d7f-050c247251bf
author: BrucePerlerMS
ms.openlocfilehash: 8476600769b6099bb885566de4c908c78a2dbbda
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201382"
---
# \<certificateValidator>

<span data-ttu-id="f304b-101">Указывает пользовательский тип для проверки сертификата.</span><span class="sxs-lookup"><span data-stu-id="f304b-101">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="f304b-102">Этот тип используется только в том случае, если `certificateValidationMode` атрибут [\<certificateValidation>](certificatevalidation.md) элемента имеет значение Custom.</span><span class="sxs-lookup"><span data-stu-id="f304b-102">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<certificateValidation>**](certificatevalidation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateValidator>**  
  
## <a name="syntax"></a><span data-ttu-id="f304b-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f304b-103">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <certificateValidation>  
      <certificateValidator type=xs:string>  
      </certificateValidator>  
    </certificateValidation>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f304b-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f304b-104">Attributes and Elements</span></span>  

 <span data-ttu-id="f304b-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f304b-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f304b-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f304b-106">Attributes</span></span>  
  
|<span data-ttu-id="f304b-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f304b-107">Attribute</span></span>|<span data-ttu-id="f304b-108">Описание</span><span class="sxs-lookup"><span data-stu-id="f304b-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f304b-109">type</span><span class="sxs-lookup"><span data-stu-id="f304b-109">type</span></span>|<span data-ttu-id="f304b-110">Указывает пользовательский тип, производный от <xref:System.IdentityModel.Selectors.X509CertificateValidator> класса.</span><span class="sxs-lookup"><span data-stu-id="f304b-110">Specifies a custom type that derives from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span> <span data-ttu-id="f304b-111">`certificateValidationMode`Чтобы использовать этот тип, присвойте атрибуту [\<certificateValidation>](certificatevalidation.md) элемента значение Custom.</span><span class="sxs-lookup"><span data-stu-id="f304b-111">Set the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element to "Custom" to use this type.</span></span> <span data-ttu-id="f304b-112">Дополнительные сведения об указании `type` атрибута см. в разделе [ссылки на пользовательские типы](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="f304b-112">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="f304b-113">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="f304b-113">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f304b-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f304b-114">Child Elements</span></span>  

 <span data-ttu-id="f304b-115">Нет</span><span class="sxs-lookup"><span data-stu-id="f304b-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f304b-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f304b-116">Parent Elements</span></span>  
  
|<span data-ttu-id="f304b-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="f304b-117">Element</span></span>|<span data-ttu-id="f304b-118">Описание</span><span class="sxs-lookup"><span data-stu-id="f304b-118">Description</span></span>|  
|-------------|-----------------|  
|[\<certificateValidation>](certificatevalidation.md)|<span data-ttu-id="f304b-119">Управляет параметрами, которые обработчики маркеров используют для проверки сертификатов.</span><span class="sxs-lookup"><span data-stu-id="f304b-119">Controls the settings that token handlers use to validate certificates.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f304b-120">Пример</span><span class="sxs-lookup"><span data-stu-id="f304b-120">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="Custom"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine">  
    <certificateValidator type="MyNamespace.CustomValidator, MyAssembly" />
</certificateValidation>
```
