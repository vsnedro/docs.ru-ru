---
title: Элемент <cryptoClasses>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClasses
helpviewer_keywords:
- <cryptoClasses> element
- cryptoClasses element
ms.assetid: 290d5f96-946d-4f02-babb-1d31ec0b8295
ms.openlocfilehash: c93fadf51297d59ab499e25de283700364903049
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155250"
---
# <a name="cryptoclasses-element"></a><span data-ttu-id="e335e-102">Элемент \<cryptoClasses></span><span class="sxs-lookup"><span data-stu-id="e335e-102">\<cryptoClasses> Element</span></span>
<span data-ttu-id="e335e-103">Содержит список криптографических классов, сопоставленных с понятным именем в [\<nameEntry>](nameentry-element.md) элементе.</span><span class="sxs-lookup"><span data-stu-id="e335e-103">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoClasses>**  
  
## <a name="syntax"></a><span data-ttu-id="e335e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e335e-104">Syntax</span></span>  
  
```xml  
<cryptoClasses>
</cryptoClasses>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e335e-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e335e-105">Attributes and Elements</span></span>  
 <span data-ttu-id="e335e-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e335e-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e335e-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e335e-107">Attributes</span></span>  
 <span data-ttu-id="e335e-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e335e-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e335e-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e335e-109">Child Elements</span></span>  
  
|<span data-ttu-id="e335e-110">Элемент</span><span class="sxs-lookup"><span data-stu-id="e335e-110">Element</span></span>|<span data-ttu-id="e335e-111">Описание</span><span class="sxs-lookup"><span data-stu-id="e335e-111">Description</span></span>|  
|-------------|-----------------|  
|[\<cryptoClass>](cryptoclass-element.md)|<span data-ttu-id="e335e-112">Содержит криптографический класс, сопоставленный с понятным именем в **\<nameEntry>** элементе.</span><span class="sxs-lookup"><span data-stu-id="e335e-112">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e335e-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e335e-113">Parent Elements</span></span>  
  
|<span data-ttu-id="e335e-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="e335e-114">Element</span></span>|<span data-ttu-id="e335e-115">Описание</span><span class="sxs-lookup"><span data-stu-id="e335e-115">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e335e-116">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e335e-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="e335e-117">Содержит параметры шифрования.</span><span class="sxs-lookup"><span data-stu-id="e335e-117">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="e335e-118">Содержит сопоставления классов с понятными именами.</span><span class="sxs-lookup"><span data-stu-id="e335e-118">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="e335e-119">Содержит `cryptographySettings` элемент.</span><span class="sxs-lookup"><span data-stu-id="e335e-119">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e335e-120">Пример</span><span class="sxs-lookup"><span data-stu-id="e335e-120">Example</span></span>  
 <span data-ttu-id="e335e-121">В следующем примере показано, как использовать **\<cryptoClass>** элемент для ссылки на криптографический класс и для настройки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="e335e-121">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="e335e-122">Затем можно передать строку "RSA" в <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> метод и использовать <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> метод для возврата `MyCryptoRSAClass` объекта.</span><span class="sxs-lookup"><span data-stu-id="e335e-122">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
               <!-- Other cryptography classes go here. -->  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
             <!-- Mappings to other cryptography classes go here. -->  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e335e-123">См. также</span><span class="sxs-lookup"><span data-stu-id="e335e-123">See also</span></span>

- <xref:System.Security.Cryptography>
- [<span data-ttu-id="e335e-124">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="e335e-124">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="e335e-125">Схема параметров криптографии</span><span class="sxs-lookup"><span data-stu-id="e335e-125">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e335e-126">Службы шифрования</span><span class="sxs-lookup"><span data-stu-id="e335e-126">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="e335e-127">System. Security. Cryptography. CryptoConfig. CreateFromName</span><span class="sxs-lookup"><span data-stu-id="e335e-127">System.Security.Cryptography.CryptoConfig.CreateFromName</span></span>](xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A)
- [<span data-ttu-id="e335e-128">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="e335e-128">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
