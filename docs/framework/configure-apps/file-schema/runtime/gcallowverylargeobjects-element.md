---
title: Элемент <gcAllowVeryLargeObjects>
ms.date: 03/30/2017
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
ms.openlocfilehash: 78a42596aae6c3ea0d94ac759d11ed52d0ace539
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178233"
---
# <a name="gcallowverylargeobjects-element"></a><span data-ttu-id="61dce-102">Элемент \<gcAllowVeryLargeObjects></span><span class="sxs-lookup"><span data-stu-id="61dce-102">\<gcAllowVeryLargeObjects> Element</span></span>

<span data-ttu-id="61dce-103">На 64 разрядных платформах позволяет использовать массивы, размер которых превышает 2 гигабайта (ГБ).</span><span class="sxs-lookup"><span data-stu-id="61dce-103">On 64-bit platforms, enables arrays that are greater than 2 gigabytes (GB) in total size.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<gcAllowVeryLargeObjects>**  
  
## <a name="syntax"></a><span data-ttu-id="61dce-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="61dce-104">Syntax</span></span>  
  
```xml  
<gcAllowVeryLargeObjects
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="61dce-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="61dce-105">Attributes and Elements</span></span>  

 <span data-ttu-id="61dce-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="61dce-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="61dce-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="61dce-107">Attributes</span></span>  
  
|<span data-ttu-id="61dce-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="61dce-108">Attribute</span></span>|<span data-ttu-id="61dce-109">Описание</span><span class="sxs-lookup"><span data-stu-id="61dce-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="61dce-110">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="61dce-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="61dce-111">Указывает, включены ли на 64-разрядных платформах массивы размером более 2 ГБ.</span><span class="sxs-lookup"><span data-stu-id="61dce-111">Specifies whether arrays that are greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="61dce-112">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="61dce-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="61dce-113">Значение</span><span class="sxs-lookup"><span data-stu-id="61dce-113">Value</span></span>|<span data-ttu-id="61dce-114">Описание</span><span class="sxs-lookup"><span data-stu-id="61dce-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="61dce-115">Массивы объемом более 2 ГБ не включены.</span><span class="sxs-lookup"><span data-stu-id="61dce-115">Arrays greater than 2 GB in total size are not enabled.</span></span> <span data-ttu-id="61dce-116">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="61dce-116">This is the default.</span></span>|  
|`true`|<span data-ttu-id="61dce-117">Массивы объемом более 2 ГБ включены на 64-разрядных платформах.</span><span class="sxs-lookup"><span data-stu-id="61dce-117">Arrays greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="61dce-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="61dce-118">Child Elements</span></span>  

 <span data-ttu-id="61dce-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="61dce-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="61dce-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="61dce-120">Parent Elements</span></span>  
  
|<span data-ttu-id="61dce-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="61dce-121">Element</span></span>|<span data-ttu-id="61dce-122">Описание</span><span class="sxs-lookup"><span data-stu-id="61dce-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="61dce-123">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="61dce-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="61dce-124">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="61dce-124">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="61dce-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="61dce-125">Remarks</span></span>  

 <span data-ttu-id="61dce-126">Использование этого элемента в файле конфигурации приложения позволяет использовать массивы размером более 2 ГБ, но не изменяет другие ограничения на размер объекта или размер массива:</span><span class="sxs-lookup"><span data-stu-id="61dce-126">Using this element in your application configuration file enables arrays that are larger than 2 GB in size, but does not change other limits on object size or array size:</span></span>  
  
- <span data-ttu-id="61dce-127">Максимальное число элементов в массиве — <xref:System.UInt32.MaxValue?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="61dce-127">The maximum number of elements in an array is <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="61dce-128">Максимальный индекс в любом отдельном измерении — 2 147 483 591 (0x7FFFFFC7) для массивов байтов и массивов однобайтовых структур, а также 2 146 435 071 (0X7FEFFFFF) для других типов.</span><span class="sxs-lookup"><span data-stu-id="61dce-128">The maximum index in any single dimension is 2,147,483,591 (0x7FFFFFC7) for byte arrays and arrays of single-byte structures, and 2,146,435,071 (0X7FEFFFFF) for other types.</span></span>  
  
- <span data-ttu-id="61dce-129">Максимальный размер строк и других объектов, не являющихся массивами, не изменяется.</span><span class="sxs-lookup"><span data-stu-id="61dce-129">The maximum size for strings and other non-array objects is unchanged.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="61dce-130">Перед включением этой функции убедитесь, что приложение не включает в себя ненадежный код, который предполагает, что размер всех массивов меньше 2 ГБ.</span><span class="sxs-lookup"><span data-stu-id="61dce-130">Before enabling this feature, ensure that your application does not include unsafe code that assumes that all arrays are smaller than 2 GB in size.</span></span> <span data-ttu-id="61dce-131">Например, ненадежный код, использующий массивы как буферы, может быть уязвим для переполнения буфера, если он написан на основе предположения, что массивы не будут превышать 2 ГБ.</span><span class="sxs-lookup"><span data-stu-id="61dce-131">For example, unsafe code that uses arrays as buffers might be susceptible to buffer overruns if it is written on the assumption that arrays will not exceed 2 GB.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61dce-132">Пример</span><span class="sxs-lookup"><span data-stu-id="61dce-132">Example</span></span>  

 <span data-ttu-id="61dce-133">В следующем примере показано, как включить эту функцию для приложения.</span><span class="sxs-lookup"><span data-stu-id="61dce-133">The following example shows how to enable this feature for an application.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <gcAllowVeryLargeObjects enabled="true" />  
  </runtime>  
</configuration>  
```  
  
## <a name="supported-in"></a><span data-ttu-id="61dce-134">Поддерживается в</span><span class="sxs-lookup"><span data-stu-id="61dce-134">Supported in</span></span>

<span data-ttu-id="61dce-135">.NET Framework 4,5 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="61dce-135">.NET Framework 4.5 and later versions</span></span>

## <a name="see-also"></a><span data-ttu-id="61dce-136">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="61dce-136">See also</span></span>

- [<span data-ttu-id="61dce-137">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="61dce-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="61dce-138">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="61dce-138">Configuration File Schema</span></span>](../index.md)
