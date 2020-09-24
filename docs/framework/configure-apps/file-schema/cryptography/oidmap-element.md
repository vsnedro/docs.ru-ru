---
title: Элемент <oidMap>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidMap
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap
helpviewer_keywords:
- <oidMap> element
- oidMap element
ms.assetid: 7f0c2246-c070-4748-b96a-2f66a296c539
ms.openlocfilehash: 6c57810389acbd58e6d2e05277a6f26fa0aac8c6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149521"
---
# <a name="oidmap-element"></a><span data-ttu-id="a9cdd-102">Элемент \<oidMap></span><span class="sxs-lookup"><span data-stu-id="a9cdd-102">\<oidMap> Element</span></span>

<span data-ttu-id="a9cdd-103">Содержит сопоставления идентификатора объекта (OID) ASN. 1 для классов.</span><span class="sxs-lookup"><span data-stu-id="a9cdd-103">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oidMap>**

## <a name="syntax"></a><span data-ttu-id="a9cdd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a9cdd-104">Syntax</span></span>  
  
```xml  
<oidMap>
</oidMap>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a9cdd-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a9cdd-105">Attributes and Elements</span></span>  

 <span data-ttu-id="a9cdd-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a9cdd-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a9cdd-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a9cdd-107">Attributes</span></span>  

 <span data-ttu-id="a9cdd-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a9cdd-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a9cdd-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a9cdd-109">Child Elements</span></span>  
  
|<span data-ttu-id="a9cdd-110">Элемент</span><span class="sxs-lookup"><span data-stu-id="a9cdd-110">Element</span></span>|<span data-ttu-id="a9cdd-111">Описание</span><span class="sxs-lookup"><span data-stu-id="a9cdd-111">Description</span></span>|  
|-------------|-----------------|  
|[\<oidEntry>](oidentry-element.md)|<span data-ttu-id="a9cdd-112">Сопоставляет идентификатор объекта ASN. 1 с понятным именем.</span><span class="sxs-lookup"><span data-stu-id="a9cdd-112">Maps an ASN.1 OID to a friendly name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a9cdd-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a9cdd-113">Parent Elements</span></span>  
  
|<span data-ttu-id="a9cdd-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="a9cdd-114">Element</span></span>|<span data-ttu-id="a9cdd-115">Описание</span><span class="sxs-lookup"><span data-stu-id="a9cdd-115">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a9cdd-116">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a9cdd-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="a9cdd-117">Содержит параметры шифрования.</span><span class="sxs-lookup"><span data-stu-id="a9cdd-117">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="a9cdd-118">Содержит `cryptographySettings` элемент.</span><span class="sxs-lookup"><span data-stu-id="a9cdd-118">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a9cdd-119">Пример</span><span class="sxs-lookup"><span data-stu-id="a9cdd-119">Example</span></span>  

 <span data-ttu-id="a9cdd-120">В следующем примере показано, как использовать **\<oidMap>** элемент для включения СОПОСТАВЛЕНИЯ OID для алгоритма хэширования RIPEMD-160 к реализации этого хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="a9cdd-120">The following example shows how to use the **\<oidMap>** element to contain a mapping of an OID for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RIPEMD-160" class="MyCrypto"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"  name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a9cdd-121">См. также</span><span class="sxs-lookup"><span data-stu-id="a9cdd-121">See also</span></span>

- [<span data-ttu-id="a9cdd-122">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="a9cdd-122">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="a9cdd-123">Схема параметров шифрования</span><span class="sxs-lookup"><span data-stu-id="a9cdd-123">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a9cdd-124">службы шифрования</span><span class="sxs-lookup"><span data-stu-id="a9cdd-124">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="a9cdd-125">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="a9cdd-125">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
- [<span data-ttu-id="a9cdd-126">Отображение идентификаторов объектов на криптографические алгоритмы</span><span class="sxs-lookup"><span data-stu-id="a9cdd-126">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../map-object-identifiers-to-cryptography-algorithms.md)
