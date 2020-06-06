---
title: Элементы директив среды выполнения
ms.date: 03/30/2017
ms.assetid: 3fe5848c-ecd7-4136-970b-8e48d250bde6
ms.openlocfilehash: c900516382c8e526a6b0021bb2b681486283f3ab
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73128172"
---
# <a name="runtime-directive-elements"></a><span data-ttu-id="80158-102">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="80158-102">Runtime Directive Elements</span></span>
<span data-ttu-id="80158-103">Формат файла директив (rd.xml) среды выполнения поддерживает следующие элементы директивы среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="80158-103">The runtime directives (rd.xml) file format supports the following runtime directive elements.</span></span> <span data-ttu-id="80158-104">Иерархическое представление см. в разделе [Справочник по конфигурационному файлу директив среды выполнения (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md).</span><span class="sxs-lookup"><span data-stu-id="80158-104">See [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md) for a hierarchical representation.</span></span>  
  
 [\<Application>](application-element-net-native.md)  
 <span data-ttu-id="80158-105">Применяется политика отражения среды выполнения для всех типов, используемых в приложении и служит в качестве контейнера для приложения типы и члены типов, метаданные которого доступны для отражения во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="80158-105">Applies runtime reflection policy to all types used by the app, and serves as a container for application-wide types and type members whose metadata is available for reflection at run time.</span></span> <span data-ttu-id="80158-106">Это дочерний [\<Directives>](directives-element-net-native.md) элемент элемента.</span><span class="sxs-lookup"><span data-stu-id="80158-106">This is a child of the [\<Directives>](directives-element-net-native.md) element.</span></span>  
  
 [\<Assembly>](assembly-element-net-native.md)  
 <span data-ttu-id="80158-107">Применяет политику среды выполнения ко всем типам в сборке.</span><span class="sxs-lookup"><span data-stu-id="80158-107">Applies runtime policy to all the types in an assembly.</span></span> <span data-ttu-id="80158-108">Это дочерний элемент [\<Application>](application-element-net-native.md) элементов и [\<Library>](library-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="80158-108">This is a child of the [\<Application>](application-element-net-native.md) and [\<Library>](library-element-net-native.md) elements.</span></span>  
  
 [\<AttributeImplies>](attributeimplies-element-net-native.md)  
 <span data-ttu-id="80158-109">Если содержащая его [\<Type>](type-element-net-native.md) директива является атрибутом, применяет политику среды выполнения к элементам кода, к которым применяется этот атрибут.</span><span class="sxs-lookup"><span data-stu-id="80158-109">If its containing [\<Type>](type-element-net-native.md) directive is an attribute, applies runtime policy to code elements to which that attribute is applied.</span></span>  
  
 [\<Directives>](directives-element-net-native.md)  
 <span data-ttu-id="80158-110">Корневой элемент в каждом файле директив среды выполнения для .NET Native.</span><span class="sxs-lookup"><span data-stu-id="80158-110">The root element in every runtime directives file for .NET Native.</span></span> <span data-ttu-id="80158-111">Его дочерними элементами являются [\<Application>](application-element-net-native.md) и [\<Library>](library-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="80158-111">Its child elements are [\<Application>](application-element-net-native.md) and [\<Library>](library-element-net-native.md).</span></span>  
  
 [\<Event>](event-element-net-native.md)  
 <span data-ttu-id="80158-112">Применяет политику среды выполнения к событию.</span><span class="sxs-lookup"><span data-stu-id="80158-112">Applies runtime policy to an event.</span></span> <span data-ttu-id="80158-113">Это дочерний элемент [\<Type>](type-element-net-native.md) элементов и [\<TypeInstantiation>](typeinstantiation-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="80158-113">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [\<Field>](field-element-net-native.md)  
 <span data-ttu-id="80158-114">Применяет политику среды выполнения к полю.</span><span class="sxs-lookup"><span data-stu-id="80158-114">Applies runtime policy to a field.</span></span> <span data-ttu-id="80158-115">Это дочерний элемент [\<Type>](type-element-net-native.md) элементов и [\<TypeInstantiation>](typeinstantiation-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="80158-115">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [\<GenericParameter>](genericparameter-element-net-native.md)  
 <span data-ttu-id="80158-116">Применяет политику среды выполнения к параметру типа универсального типа или метода.</span><span class="sxs-lookup"><span data-stu-id="80158-116">Applies runtime policy to the parameter type of a generic type or method.</span></span>  
  
 [\<ImpliesType>](impliestype-element-net-native.md)  
 <span data-ttu-id="80158-117">Применяет политику среды выполнения к типу, если политика была применена к содержащему типу или методу.</span><span class="sxs-lookup"><span data-stu-id="80158-117">Applies runtime policy to a type, if that policy has been applied to the containing type or method.</span></span>  
  
 [\<Library>](library-element-net-native.md)  
 <span data-ttu-id="80158-118">Применяет политику среды выполнения ко всем типам в сборке.</span><span class="sxs-lookup"><span data-stu-id="80158-118">Applies runtime policy to all the types in an assembly.</span></span> <span data-ttu-id="80158-119">Это дочерний элемент [\<Application>](application-element-net-native.md) элементов и [\<Library>](library-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="80158-119">This is a child of the [\<Application>](application-element-net-native.md) and [\<Library>](library-element-net-native.md) elements.</span></span>  
  
 [\<Method>](method-element-net-native.md)  
 <span data-ttu-id="80158-120">Применяет политику среды выполнения к методу.</span><span class="sxs-lookup"><span data-stu-id="80158-120">Applies runtime policy to a method.</span></span> <span data-ttu-id="80158-121">Это дочерний элемент [\<Type>](type-element-net-native.md) элементов и [\<TypeInstantiation>](typeinstantiation-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="80158-121">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [\<MethodInstantiation>](methodinstantiation-element-net-native.md)  
 <span data-ttu-id="80158-122">Применяет политику среды выполнения к сконструированному универсальному методу.</span><span class="sxs-lookup"><span data-stu-id="80158-122">Applies runtime policy to a constructed generic method.</span></span> <span data-ttu-id="80158-123">Это дочерний элемент [\<Type>](type-element-net-native.md) элементов и [\<TypeInstantiation>](typeinstantiation-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="80158-123">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [\<Namespace>](namespace-element-net-native.md)  
 <span data-ttu-id="80158-124">Применяет политику среды выполнения ко всем типам в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="80158-124">Applies runtime policy to all the types in a namespace.</span></span>  
  
 [\<Parameter>](parameter-element-net-native.md)  
 <span data-ttu-id="80158-125">Применяет политику среды выполнения к типу аргумента, переданного методу.</span><span class="sxs-lookup"><span data-stu-id="80158-125">Applies runtime policy to the type of the argument passed to a method.</span></span>  
  
 [\<Property>](property-element-net-native.md)  
 <span data-ttu-id="80158-126">Применяет политику среды выполнения к свойству.</span><span class="sxs-lookup"><span data-stu-id="80158-126">Applies runtime policy to a property.</span></span> <span data-ttu-id="80158-127">Это дочерний элемент [\<Type>](type-element-net-native.md) элементов и [\<TypeInstantiation>](typeinstantiation-element-net-native.md) .</span><span class="sxs-lookup"><span data-stu-id="80158-127">This is a child of the [\<Type>](type-element-net-native.md) and [\<TypeInstantiation>](typeinstantiation-element-net-native.md) elements.</span></span>  
  
 [\<Subtypes>](subtypes-element-net-native.md)  
 <span data-ttu-id="80158-128">Применяет политику среды выполнения для всех классов, унаследованных из содержащего типа.</span><span class="sxs-lookup"><span data-stu-id="80158-128">Applies runtime policy to all classes inherited from the containing type.</span></span>  
  
 [\<Type>](type-element-net-native.md)  
 <span data-ttu-id="80158-129">Применяет политику среды выполнения к типу.</span><span class="sxs-lookup"><span data-stu-id="80158-129">Applies runtime policy to a type.</span></span>  
  
 [\<TypeInstantiation>](typeinstantiation-element-net-native.md)  
 <span data-ttu-id="80158-130">Применяет политику среды выполнения к сконструированному универсальному типу.</span><span class="sxs-lookup"><span data-stu-id="80158-130">Applies runtime policy to a constructed generic type.</span></span>  
  
 [\<TypeParameter>](typeparameter-element-net-native.md)  
 <span data-ttu-id="80158-131">Применяет политику среды выполнения к типу, представленному аргументом <xref:System.Type>, переданным методу.</span><span class="sxs-lookup"><span data-stu-id="80158-131">Applies runtime policy to the type represented by a <xref:System.Type> argument passed to a method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80158-132">См. также</span><span class="sxs-lookup"><span data-stu-id="80158-132">See also</span></span>

- [<span data-ttu-id="80158-133">Справочник по конфигурационному файлу rd.xml</span><span class="sxs-lookup"><span data-stu-id="80158-133">rd.xml Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
