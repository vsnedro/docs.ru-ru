---
title: Элемент <cryptoNameMapping>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoNameMapping
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping
helpviewer_keywords:
- <cryptoNameMapping> element
- cryptoNameMapping element
ms.assetid: c59c9494-149b-4ce6-b38d-371f896ae85c
ms.openlocfilehash: d31c5cd52ffe0e2a6eb5784735e76436d216444b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155223"
---
# <a name="cryptonamemapping-element"></a><span data-ttu-id="76044-102">Элемент \<cryptoNameMapping></span><span class="sxs-lookup"><span data-stu-id="76044-102">\<cryptoNameMapping> Element</span></span>
<span data-ttu-id="76044-103">Содержит сопоставления классов с понятными именами.</span><span class="sxs-lookup"><span data-stu-id="76044-103">Contains mappings of classes to friendly names.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoNameMapping>**

## <a name="syntax"></a><span data-ttu-id="76044-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="76044-104">Syntax</span></span>  
  
```xml  
      <cryptoNameMapping>
</cryptoNameMapping>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="76044-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="76044-105">Attributes and Elements</span></span>  
 <span data-ttu-id="76044-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="76044-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="76044-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="76044-107">Attributes</span></span>  
 <span data-ttu-id="76044-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="76044-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="76044-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="76044-109">Child Elements</span></span>  
  
|<span data-ttu-id="76044-110">Элемент</span><span class="sxs-lookup"><span data-stu-id="76044-110">Element</span></span>|<span data-ttu-id="76044-111">Описание</span><span class="sxs-lookup"><span data-stu-id="76044-111">Description</span></span>|  
|-------------|-----------------|  
|`cryptoClasses`|<span data-ttu-id="76044-112">Содержит список криптографических классов, сопоставленных с понятным именем в **\<nameEntry>** элементе.</span><span class="sxs-lookup"><span data-stu-id="76044-112">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|`nameEntry`|<span data-ttu-id="76044-113">Сопоставляет имя класса с понятным именем алгоритма, что позволяет одному классу иметь несколько понятных имен.</span><span class="sxs-lookup"><span data-stu-id="76044-113">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="76044-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="76044-114">Parent Elements</span></span>  
  
|<span data-ttu-id="76044-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="76044-115">Element</span></span>|<span data-ttu-id="76044-116">Описание</span><span class="sxs-lookup"><span data-stu-id="76044-116">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="76044-117">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="76044-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="76044-118">Содержит параметры шифрования.</span><span class="sxs-lookup"><span data-stu-id="76044-118">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="76044-119">Содержит сопоставления классов с понятными именами.</span><span class="sxs-lookup"><span data-stu-id="76044-119">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="76044-120">Содержит \<cryptographySettings> элемент.</span><span class="sxs-lookup"><span data-stu-id="76044-120">Contains the \<cryptographySettings> element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="76044-121">Пример</span><span class="sxs-lookup"><span data-stu-id="76044-121">Example</span></span>  
 <span data-ttu-id="76044-122">В следующем примере показано, как использовать **\<cryptoNameMapping>** элемент для ссылки на криптографический класс и настройки среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="76044-122">The following example shows how to use the **\<cryptoNameMapping>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="76044-123">Затем можно передать строку "RSA" в <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> метод и использовать <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> метод для возврата `MyCryptoRSAClass` объекта.</span><span class="sxs-lookup"><span data-stu-id="76044-123">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="76044-124">См. также</span><span class="sxs-lookup"><span data-stu-id="76044-124">See also</span></span>

- [<span data-ttu-id="76044-125">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="76044-125">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="76044-126">Схема параметров криптографии</span><span class="sxs-lookup"><span data-stu-id="76044-126">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="76044-127">Службы шифрования</span><span class="sxs-lookup"><span data-stu-id="76044-127">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="76044-128">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="76044-128">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
