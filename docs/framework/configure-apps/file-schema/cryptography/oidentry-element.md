---
title: Элемент <oidEntry>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap/oidEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidEntry
helpviewer_keywords:
- <oidEntry> element
- oidEntry element
ms.assetid: 22fb88b0-bf27-489c-9ca0-e65950ac136c
ms.openlocfilehash: 2207c934f5864890d9b7a5e22c43a1d53e29aaa5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91187112"
---
# <a name="oidentry-element"></a><span data-ttu-id="986a6-102">Элемент \<oidEntry></span><span class="sxs-lookup"><span data-stu-id="986a6-102">\<oidEntry> Element</span></span>

<span data-ttu-id="986a6-103">Сопоставляет идентификатор объекта (OID) ASN.1 с понятным именем.</span><span class="sxs-lookup"><span data-stu-id="986a6-103">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidMap>**](oidmap-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oidEntry>**

## <a name="syntax"></a><span data-ttu-id="986a6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="986a6-104">Syntax</span></span>  
  
```xml  
<oidEntry OID="object identifier number" name="friendly name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="986a6-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="986a6-105">Attributes and Elements</span></span>  

 <span data-ttu-id="986a6-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="986a6-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="986a6-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="986a6-107">Attributes</span></span>  
  
|<span data-ttu-id="986a6-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="986a6-108">Attribute</span></span>|<span data-ttu-id="986a6-109">Описание</span><span class="sxs-lookup"><span data-stu-id="986a6-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="986a6-110">**КОДА**</span><span class="sxs-lookup"><span data-stu-id="986a6-110">**OID**</span></span>|<span data-ttu-id="986a6-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="986a6-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="986a6-112">Указывает идентификатор объекта ASN. 1, соответствующий алгоритму, реализуемому вашим классом.</span><span class="sxs-lookup"><span data-stu-id="986a6-112">Specifies the ASN.1 OID corresponding to the algorithm implemented by your class.</span></span>|  
|<span data-ttu-id="986a6-113">**name**</span><span class="sxs-lookup"><span data-stu-id="986a6-113">**name**</span></span>|<span data-ttu-id="986a6-114">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="986a6-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="986a6-115">Задает значение для атрибута **Name** в [\<nameEntry>](nameentry-element.md) теге.</span><span class="sxs-lookup"><span data-stu-id="986a6-115">Specifies the value for the **name** attribute in the [\<nameEntry>](nameentry-element.md) tag.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="986a6-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="986a6-116">Child Elements</span></span>  

 <span data-ttu-id="986a6-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="986a6-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="986a6-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="986a6-118">Parent Elements</span></span>  
  
|<span data-ttu-id="986a6-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="986a6-119">Element</span></span>|<span data-ttu-id="986a6-120">Описание</span><span class="sxs-lookup"><span data-stu-id="986a6-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="986a6-121">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="986a6-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="986a6-122">Содержит параметры шифрования.</span><span class="sxs-lookup"><span data-stu-id="986a6-122">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="986a6-123">Содержит `cryptographySettings` элемент.</span><span class="sxs-lookup"><span data-stu-id="986a6-123">Contains the `cryptographySettings` element.</span></span>|  
|`oidMap`|<span data-ttu-id="986a6-124">Содержит сопоставления идентификатора объекта (OID) ASN. 1 для классов.</span><span class="sxs-lookup"><span data-stu-id="986a6-124">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="986a6-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="986a6-125">Remarks</span></span>  

 <span data-ttu-id="986a6-126">Идентификаторы объектов ASN. 1 обозначают алгоритмы в некоторых криптографических форматах.</span><span class="sxs-lookup"><span data-stu-id="986a6-126">ASN.1 object identifiers identify algorithms in some cryptographic formats.</span></span> <span data-ttu-id="986a6-127">Сопоставьте идентификаторы объектов с понятными именами для алгоритмов, которые необходимо опознать.</span><span class="sxs-lookup"><span data-stu-id="986a6-127">Map object identifiers to friendly names for the algorithms you want to identify.</span></span>  
  
## <a name="example"></a><span data-ttu-id="986a6-128">Пример</span><span class="sxs-lookup"><span data-stu-id="986a6-128">Example</span></span>  

 <span data-ttu-id="986a6-129">В следующем примере показано, как с помощью **\<oidEntry>** элемента сопоставлять идентификатор объекта для алгоритма хэширования RIPEMD-160 к реализации этого хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="986a6-129">The following example shows how to use the **\<oidEntry>** element to map an object identifier for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
            <oidEntry OID="1.3.36.3.2.1"   name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="986a6-130">См. также</span><span class="sxs-lookup"><span data-stu-id="986a6-130">See also</span></span>

- [<span data-ttu-id="986a6-131">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="986a6-131">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="986a6-132">Схема параметров шифрования</span><span class="sxs-lookup"><span data-stu-id="986a6-132">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="986a6-133">службы шифрования</span><span class="sxs-lookup"><span data-stu-id="986a6-133">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="986a6-134">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="986a6-134">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
- [<span data-ttu-id="986a6-135">Отображение идентификаторов объектов на криптографические алгоритмы</span><span class="sxs-lookup"><span data-stu-id="986a6-135">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../map-object-identifiers-to-cryptography-algorithms.md)
