---
title: Элемент <probing>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/probing
- http://schemas.microsoft.com/.NetConfiguration/v2.0#probing
helpviewer_keywords:
- <probing> element
- container tags, <probing> element
- probing element
ms.assetid: 09c80fc9-1ba5-4192-89f7-3a79b2e4b024
ms.openlocfilehash: 1435ee8ea887b5d7d3e785eef0f25ffed14b1b97
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195276"
---
# <a name="probing-element"></a><span data-ttu-id="0ee0a-102">Элемент \<probing></span><span class="sxs-lookup"><span data-stu-id="0ee0a-102">\<probing> Element</span></span>

<span data-ttu-id="0ee0a-103">Задает базовые подкаталоги приложения для поиска средой CLR при загрузке сборок.</span><span class="sxs-lookup"><span data-stu-id="0ee0a-103">Specifies application base subdirectories for the common language runtime to search when loading assemblies.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<probing>**  
  
## <a name="syntax"></a><span data-ttu-id="0ee0a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0ee0a-104">Syntax</span></span>  
  
```xml  
<probing privatePath="paths"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0ee0a-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0ee0a-105">Attributes and Elements</span></span>  

 <span data-ttu-id="0ee0a-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0ee0a-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0ee0a-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0ee0a-107">Attributes</span></span>  
  
|<span data-ttu-id="0ee0a-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0ee0a-108">Attribute</span></span>|<span data-ttu-id="0ee0a-109">Описание</span><span class="sxs-lookup"><span data-stu-id="0ee0a-109">Description</span></span>|  
|---------------|-----------------|  
|`privatePath`|<span data-ttu-id="0ee0a-110">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="0ee0a-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="0ee0a-111">Указывает подкаталоги базового каталога приложения, которые могут содержать сборки.</span><span class="sxs-lookup"><span data-stu-id="0ee0a-111">Specifies subdirectories of the application's base directory that might contain assemblies.</span></span> <span data-ttu-id="0ee0a-112">Для каждого подкаталога следует выделить точку с запятой.</span><span class="sxs-lookup"><span data-stu-id="0ee0a-112">Delimit each subdirectory with a semicolon.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0ee0a-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0ee0a-113">Child Elements</span></span>  

<span data-ttu-id="0ee0a-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0ee0a-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0ee0a-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0ee0a-115">Parent Elements</span></span>  
  
|<span data-ttu-id="0ee0a-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="0ee0a-116">Element</span></span>|<span data-ttu-id="0ee0a-117">Описание</span><span class="sxs-lookup"><span data-stu-id="0ee0a-117">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="0ee0a-118">Содержит сведения о перенаправлении версии сборки и о расположениях сборок.</span><span class="sxs-lookup"><span data-stu-id="0ee0a-118">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="0ee0a-119">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0ee0a-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="0ee0a-120">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="0ee0a-120">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0ee0a-121">Пример</span><span class="sxs-lookup"><span data-stu-id="0ee0a-121">Example</span></span>  

 <span data-ttu-id="0ee0a-122">В следующем примере показано, как задать базовые подкаталоги приложения, которые среда выполнения должна использовать для поиска сборок.</span><span class="sxs-lookup"><span data-stu-id="0ee0a-122">The following example shows how to specify application base subdirectories the runtime should search for assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0ee0a-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0ee0a-123">See also</span></span>

- [<span data-ttu-id="0ee0a-124">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="0ee0a-124">Runtime settings schema</span></span>](index.md)
- [<span data-ttu-id="0ee0a-125">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="0ee0a-125">Configuration file schema</span></span>](../index.md)
- [<span data-ttu-id="0ee0a-126">Укажите расположение сборки</span><span class="sxs-lookup"><span data-stu-id="0ee0a-126">Specify an assembly's location</span></span>](../../../../standard/assembly/location.md)
- [<span data-ttu-id="0ee0a-127">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="0ee0a-127">How the runtime locates assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
