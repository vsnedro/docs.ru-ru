---
title: <Directives>Элемент (.NET Native)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
ms.openlocfilehash: 0c6ebb8954e80f3f6dc6733f0e9d76094477689b
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202385"
---
# <a name="directives-element-net-native"></a><span data-ttu-id="6e172-102">\<Directives>Элемент (.NET Native)</span><span class="sxs-lookup"><span data-stu-id="6e172-102">\<Directives> Element (.NET Native)</span></span>
<span data-ttu-id="6e172-103">Корневой элемент в каждом файле директив среды выполнения для .NET Native.</span><span class="sxs-lookup"><span data-stu-id="6e172-103">The root element in every runtime directives file for .NET Native.</span></span>  
  
 `<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">`
  
## <a name="syntax"></a><span data-ttu-id="6e172-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6e172-104">Syntax</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->
</Directives>  
```  
  
## <a name="attributes"></a><span data-ttu-id="6e172-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6e172-105">Attributes</span></span>  
  
|<span data-ttu-id="6e172-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6e172-106">Attribute</span></span>|<span data-ttu-id="6e172-107">Описание</span><span class="sxs-lookup"><span data-stu-id="6e172-107">Description</span></span>|  
|---------------|-----------------|  
|`xmlns`|<span data-ttu-id="6e172-108">Пространство имен XML.</span><span class="sxs-lookup"><span data-stu-id="6e172-108">The XML namespace.</span></span> <span data-ttu-id="6e172-109">Его значение всегда равно `http://schemas.microsoft.com/netfx/2013/01/metadata` .</span><span class="sxs-lookup"><span data-stu-id="6e172-109">Its value is always `http://schemas.microsoft.com/netfx/2013/01/metadata`.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="6e172-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6e172-110">Child elements</span></span>  
  
|<span data-ttu-id="6e172-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="6e172-111">Element</span></span>|<span data-ttu-id="6e172-112">Описание</span><span class="sxs-lookup"><span data-stu-id="6e172-112">Description</span></span>|  
|-------------|-----------------|  
|[\<Application>](application-element-net-native.md)|<span data-ttu-id="6e172-113">Служит в качестве контейнера для типов и членов типов приложения, метаданные которого доступны для отражения.</span><span class="sxs-lookup"><span data-stu-id="6e172-113">Serves as a container for application-wide types and type members whose metadata is available for reflection.</span></span>|  
|[\<Library>](library-element-net-native.md)|<span data-ttu-id="6e172-114">Определяет сборку, чьи дочерние типы и члены типов требуют метаданные во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="6e172-114">Defines the assembly whose child types and type members require metadata at run time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e172-115">Комментарии</span><span class="sxs-lookup"><span data-stu-id="6e172-115">Remarks</span></span>  
 <span data-ttu-id="6e172-116">Каждый файл директив среды выполнения содержит только один элемент `<Directives>`.</span><span class="sxs-lookup"><span data-stu-id="6e172-116">Each runtime directives file can contain only one `<Directives>` element.</span></span>  
  
 <span data-ttu-id="6e172-117">`<Directives>`Элемент может содержать ноль или один [\<Application>](application-element-net-native.md) элемент, а также ноль, один или несколько [\<Library>](library-element-net-native.md) элементов.</span><span class="sxs-lookup"><span data-stu-id="6e172-117">The `<Directives>` element can contain zero or one [\<Application>](application-element-net-native.md) element, and zero, one, or more [\<Library>](library-element-net-native.md) elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e172-118">См. также статью</span><span class="sxs-lookup"><span data-stu-id="6e172-118">See also</span></span>

- [<span data-ttu-id="6e172-119">Ссылка на файл конфигурации директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="6e172-119">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="6e172-120">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="6e172-120">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
