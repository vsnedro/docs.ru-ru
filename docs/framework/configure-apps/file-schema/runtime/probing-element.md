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
ms.openlocfilehash: e9e48ea97e1b70fef7fcc78a113e18c5fec23b7c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73115865"
---
# <a name="probing-element"></a><span data-ttu-id="57701-102">Элемент \<probing></span><span class="sxs-lookup"><span data-stu-id="57701-102">\<probing> Element</span></span>
<span data-ttu-id="57701-103">Задает базовые подкаталоги приложения для поиска средой CLR при загрузке сборок.</span><span class="sxs-lookup"><span data-stu-id="57701-103">Specifies application base subdirectories for the common language runtime to search when loading assemblies.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<probing>**  
  
## <a name="syntax"></a><span data-ttu-id="57701-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="57701-104">Syntax</span></span>  
  
```xml  
<probing privatePath="paths"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="57701-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="57701-105">Attributes and Elements</span></span>  
 <span data-ttu-id="57701-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="57701-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="57701-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="57701-107">Attributes</span></span>  
  
|<span data-ttu-id="57701-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="57701-108">Attribute</span></span>|<span data-ttu-id="57701-109">Описание</span><span class="sxs-lookup"><span data-stu-id="57701-109">Description</span></span>|  
|---------------|-----------------|  
|`privatePath`|<span data-ttu-id="57701-110">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="57701-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="57701-111">Указывает подкаталоги базового каталога приложения, которые могут содержать сборки.</span><span class="sxs-lookup"><span data-stu-id="57701-111">Specifies subdirectories of the application's base directory that might contain assemblies.</span></span> <span data-ttu-id="57701-112">Для каждого подкаталога следует выделить точку с запятой.</span><span class="sxs-lookup"><span data-stu-id="57701-112">Delimit each subdirectory with a semicolon.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="57701-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="57701-113">Child Elements</span></span>  

<span data-ttu-id="57701-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="57701-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="57701-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="57701-115">Parent Elements</span></span>  
  
|<span data-ttu-id="57701-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="57701-116">Element</span></span>|<span data-ttu-id="57701-117">Описание</span><span class="sxs-lookup"><span data-stu-id="57701-117">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="57701-118">Содержит сведения о перенаправлении версии сборки и о расположениях сборок.</span><span class="sxs-lookup"><span data-stu-id="57701-118">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="57701-119">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="57701-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="57701-120">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="57701-120">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="57701-121">Пример</span><span class="sxs-lookup"><span data-stu-id="57701-121">Example</span></span>  
 <span data-ttu-id="57701-122">В следующем примере показано, как задать базовые подкаталоги приложения, которые среда выполнения должна использовать для поиска сборок.</span><span class="sxs-lookup"><span data-stu-id="57701-122">The following example shows how to specify application base subdirectories the runtime should search for assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="57701-123">См. также</span><span class="sxs-lookup"><span data-stu-id="57701-123">See also</span></span>

- [<span data-ttu-id="57701-124">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="57701-124">Runtime settings schema</span></span>](index.md)
- [<span data-ttu-id="57701-125">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="57701-125">Configuration file schema</span></span>](../index.md)
- [<span data-ttu-id="57701-126">Укажите расположение сборки</span><span class="sxs-lookup"><span data-stu-id="57701-126">Specify an assembly's location</span></span>](../../../../standard/assembly/location.md)
- [<span data-ttu-id="57701-127">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="57701-127">How the runtime locates assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
