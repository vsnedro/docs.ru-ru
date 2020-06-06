---
title: Элемент <cryptographySettings>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptographySettings
helpviewer_keywords:
- cryptographySettings element
- <cryptographySettings> element
ms.assetid: 6201b7da-bcb7-49f7-b9f5-ba1fe05573b9
ms.openlocfilehash: fe6de09213c6f980e8eb205a318aae50033b2a84
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155236"
---
# <a name="cryptographysettings-element"></a><span data-ttu-id="9b89e-102">Элемент \<cryptographySettings></span><span class="sxs-lookup"><span data-stu-id="9b89e-102">\<cryptographySettings> Element</span></span>
<span data-ttu-id="9b89e-103">Содержит параметры шифрования.</span><span class="sxs-lookup"><span data-stu-id="9b89e-103">Contains cryptography settings.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptographySettings>**

## <a name="syntax"></a><span data-ttu-id="9b89e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9b89e-104">Syntax</span></span>  
  
```xml  
      <cryptographySettings>
</cryptographySettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b89e-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9b89e-105">Attributes and Elements</span></span>  
 <span data-ttu-id="9b89e-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9b89e-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b89e-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9b89e-107">Attributes</span></span>  
 <span data-ttu-id="9b89e-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="9b89e-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9b89e-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9b89e-109">Child Elements</span></span>  
  
|<span data-ttu-id="9b89e-110">Элемент</span><span class="sxs-lookup"><span data-stu-id="9b89e-110">Element</span></span>|<span data-ttu-id="9b89e-111">Описание</span><span class="sxs-lookup"><span data-stu-id="9b89e-111">Description</span></span>|  
|-------------|-----------------|  
|[\<cryptoNameMapping>](cryptonamemapping-element.md)|<span data-ttu-id="9b89e-112">Содержит сопоставления классов с понятными именами.</span><span class="sxs-lookup"><span data-stu-id="9b89e-112">Contains mappings of classes to friendly names.</span></span>|  
|[\<oidMap>](oidmap-element.md)|<span data-ttu-id="9b89e-113">Содержит сопоставления идентификатора объекта (OID) ASN. 1 для классов.</span><span class="sxs-lookup"><span data-stu-id="9b89e-113">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9b89e-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9b89e-114">Parent Elements</span></span>  
  
|<span data-ttu-id="9b89e-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="9b89e-115">Element</span></span>|<span data-ttu-id="9b89e-116">Описание</span><span class="sxs-lookup"><span data-stu-id="9b89e-116">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9b89e-117">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9b89e-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`mscorlib`|<span data-ttu-id="9b89e-118">Содержит `cryptographySettings` элемент.</span><span class="sxs-lookup"><span data-stu-id="9b89e-118">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9b89e-119">Пример</span><span class="sxs-lookup"><span data-stu-id="9b89e-119">Example</span></span>  
 <span data-ttu-id="9b89e-120">В следующем примере показано, как использовать **\<cryptographySettings>** элемент для хранения сопоставлений имен криптографии и СОПОСТАВЛЕНИЯ OID.</span><span class="sxs-lookup"><span data-stu-id="9b89e-120">The following example shows how use the **\<cryptographySettings>** element to contain cryptography name mappings and OID mappings.</span></span> <span data-ttu-id="9b89e-121">В этом примере среда выполнения настраивается таким образом, что <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> возвращает `MyHashClass` объект, а `MyCryptoClass` класс сопоставляется с идентификатором объекта 1.3.36.2.1.</span><span class="sxs-lookup"><span data-stu-id="9b89e-121">This example configures the runtime so that <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> returns a `MyHashClass` object and the `MyCryptoClass` class maps to the object identifier 1.3.36.2.1.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyHash="MyHashClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="System.Security.Cryptography.HashAlgorithm"  
                       class="MyHash"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"   name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9b89e-122">См. также</span><span class="sxs-lookup"><span data-stu-id="9b89e-122">See also</span></span>

- [<span data-ttu-id="9b89e-123">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="9b89e-123">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="9b89e-124">Схема параметров криптографии</span><span class="sxs-lookup"><span data-stu-id="9b89e-124">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="9b89e-125">Службы шифрования</span><span class="sxs-lookup"><span data-stu-id="9b89e-125">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
