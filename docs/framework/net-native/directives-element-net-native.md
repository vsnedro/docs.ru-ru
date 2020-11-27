---
title: <Directives> Элемент (.NET Native)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
ms.openlocfilehash: 524c30872e218f6428491507bbfb4ca54b6061b1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96251104"
---
# <a name="directives-element-net-native"></a><span data-ttu-id="c8f7d-102">\<Directives> Элемент (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="c8f7d-102">\<Directives> Element (.NET Native)</span></span>

<span data-ttu-id="c8f7d-103">Корневой элемент в каждом файле директив среды выполнения для .NET Native.</span><span class="sxs-lookup"><span data-stu-id="c8f7d-103">The root element in every runtime directives file for .NET Native.</span></span>  
  
 `<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">`
  
## <a name="syntax"></a><span data-ttu-id="c8f7d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c8f7d-104">Syntax</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->
</Directives>  
```  
  
## <a name="attributes"></a><span data-ttu-id="c8f7d-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c8f7d-105">Attributes</span></span>  
  
|<span data-ttu-id="c8f7d-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c8f7d-106">Attribute</span></span>|<span data-ttu-id="c8f7d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c8f7d-107">Description</span></span>|  
|---------------|-----------------|  
|`xmlns`|<span data-ttu-id="c8f7d-108">Пространство имен XML.</span><span class="sxs-lookup"><span data-stu-id="c8f7d-108">The XML namespace.</span></span> <span data-ttu-id="c8f7d-109">Его значение всегда равно `http://schemas.microsoft.com/netfx/2013/01/metadata` .</span><span class="sxs-lookup"><span data-stu-id="c8f7d-109">Its value is always `http://schemas.microsoft.com/netfx/2013/01/metadata`.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="c8f7d-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c8f7d-110">Child elements</span></span>  
  
|<span data-ttu-id="c8f7d-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="c8f7d-111">Element</span></span>|<span data-ttu-id="c8f7d-112">Описание</span><span class="sxs-lookup"><span data-stu-id="c8f7d-112">Description</span></span>|  
|-------------|-----------------|  
|[\<Application>](application-element-net-native.md)|<span data-ttu-id="c8f7d-113">Служит в качестве контейнера для типов и членов типов приложения, метаданные которого доступны для отражения.</span><span class="sxs-lookup"><span data-stu-id="c8f7d-113">Serves as a container for application-wide types and type members whose metadata is available for reflection.</span></span>|  
|[\<Library>](library-element-net-native.md)|<span data-ttu-id="c8f7d-114">Определяет сборку, чьи дочерние типы и члены типов требуют метаданные во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="c8f7d-114">Defines the assembly whose child types and type members require metadata at run time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8f7d-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="c8f7d-115">Remarks</span></span>  

 <span data-ttu-id="c8f7d-116">Каждый файл директив среды выполнения содержит только один элемент `<Directives>`.</span><span class="sxs-lookup"><span data-stu-id="c8f7d-116">Each runtime directives file can contain only one `<Directives>` element.</span></span>  
  
 <span data-ttu-id="c8f7d-117">`<Directives>`Элемент может содержать ноль или один [\<Application>](application-element-net-native.md) элемент, а также ноль, один или несколько [\<Library>](library-element-net-native.md) элементов.</span><span class="sxs-lookup"><span data-stu-id="c8f7d-117">The `<Directives>` element can contain zero or one [\<Application>](application-element-net-native.md) element, and zero, one, or more [\<Library>](library-element-net-native.md) elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8f7d-118">См. также</span><span class="sxs-lookup"><span data-stu-id="c8f7d-118">See also</span></span>

- [<span data-ttu-id="c8f7d-119">Ссылка на файл конфигурации директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="c8f7d-119">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="c8f7d-120">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="c8f7d-120">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
