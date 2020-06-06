---
title: Ссылка на файл конфигурации директив среды выполнения (rd.xml)
ms.date: 03/30/2017
ms.assetid: 8241523f-d8e1-4fb6-bf6a-b29bfe07b38a
ms.openlocfilehash: e74d34693446cca645003a9f93bc1777849e3182
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "76738404"
---
# <a name="runtime-directives-rdxml-configuration-file-reference"></a><span data-ttu-id="d9d17-102">Ссылка на файл конфигурации директив среды выполнения (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="d9d17-102">Runtime Directives (rd.xml) Configuration File Reference</span></span>

<span data-ttu-id="d9d17-103">Файл директив среды выполнения (. rd.xml) — это файл конфигурации XML, который определяет, доступны ли элементы в указанной программе для отражения.</span><span class="sxs-lookup"><span data-stu-id="d9d17-103">A runtime directives (.rd.xml) file is an XML configuration file that specifies whether designated program elements are available for reflection.</span></span> <span data-ttu-id="d9d17-104">Ниже приведен пример файла директив среды выполнения:</span><span class="sxs-lookup"><span data-stu-id="d9d17-104">Here’s an example of a runtime directives file:</span></span>

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
  <Application>
    <Namespace Name="Contoso.Cloud.AppServices" Serialize="Required Public" />
    <Namespace Name="ContosoClient.ViewModels" Serialize="Required Public" />
    <Namespace Name="ContosoClient.DataModel" Serialize="Required Public" />
    <Namespace Name="Contoso.Reader.UtilityLib" Serialize="Required Public" />

    <Namespace Name="System.Collections.ObjectModel" >
      <TypeInstantiation Name="ObservableCollection"
            Arguments="ContosoClient.DataModel.ProductItem" Serialize="Public" />
      <TypeInstantiation Name="ReadOnlyObservableCollection"
            Arguments="ContosoClient.DataModel.ProductGroup" Serialize="Public" />
    </Namespace>
  </Application>
</Directives>
```

## <a name="the-structure-of-a-runtime-directives-file"></a><span data-ttu-id="d9d17-105">Структура файла директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="d9d17-105">The structure of a runtime directives file</span></span>

<span data-ttu-id="d9d17-106">Файл директив среды выполнения использует пространство имен `http://schemas.microsoft.com/netfx/2013/01/metadata`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-106">The runtime directives file uses the `http://schemas.microsoft.com/netfx/2013/01/metadata` namespace.</span></span>

<span data-ttu-id="d9d17-107">Корневой элемент — элемент [Directives](directives-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="d9d17-107">The root element is the [Directives](directives-element-net-native.md) element.</span></span> <span data-ttu-id="d9d17-108">Он может содержать ноль или больше элементов [Library](library-element-net-native.md) и ноль или один элемент [Application](application-element-net-native.md), как показано в следующей структуре.</span><span class="sxs-lookup"><span data-stu-id="d9d17-108">It can contain zero or more [Library](library-element-net-native.md) elements, and zero or one [Application](application-element-net-native.md) element, as shown in the following structure.</span></span> <span data-ttu-id="d9d17-109">Атрибуты элемента [Application](application-element-net-native.md) могут определять политику отражения среды выполнения для приложения или служить контейнером для дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="d9d17-109">The attributes of the [Application](application-element-net-native.md) element can define application-wide runtime reflection policy, or it can serve as a container for child elements.</span></span> <span data-ttu-id="d9d17-110">Элемент [Library](library-element-net-native.md), с другой стороны, это просто контейнер.</span><span class="sxs-lookup"><span data-stu-id="d9d17-110">The [Library](library-element-net-native.md) element, on the other hand, is simply a container.</span></span> <span data-ttu-id="d9d17-111">Дочерние элементы элементов [Application](application-element-net-native.md) и [Library](library-element-net-native.md) определяют типы, методы, поля, свойства и события, доступные для отражения.</span><span class="sxs-lookup"><span data-stu-id="d9d17-111">The children of the [Application](application-element-net-native.md) and [Library](library-element-net-native.md) elements define the types, methods, fields, properties, and events that are available for reflection.</span></span>

<span data-ttu-id="d9d17-112">Для получения справочной информации выберите элементы из приведенной ниже структуры или см. раздел [Элементы директив среды выполнения](runtime-directive-elements.md).</span><span class="sxs-lookup"><span data-stu-id="d9d17-112">For reference information, choose elements from the following structure or see [Runtime Directive Elements](runtime-directive-elements.md).</span></span> <span data-ttu-id="d9d17-113">В следующей иерархии многоточие отмечает рекурсивную структуру.</span><span class="sxs-lookup"><span data-stu-id="d9d17-113">In the following hierarchy, the ellipsis marks a recursive structure.</span></span> <span data-ttu-id="d9d17-114">Информация в скобках указывает, является этот элемент необязательным или обязательным, и если он используется, сколько экземпляров (один или несколько) разрешено.</span><span class="sxs-lookup"><span data-stu-id="d9d17-114">The information in brackets indicates whether that element is optional or required, and if it is used, how many instances (one or many) are allowed.</span></span>

- <span data-ttu-id="d9d17-115">[Directives](directives-element-net-native.md) [1:1]</span><span class="sxs-lookup"><span data-stu-id="d9d17-115">[Directives](directives-element-net-native.md) [1:1]</span></span>
  - <span data-ttu-id="d9d17-116">[Application](application-element-net-native.md) [0:1]</span><span class="sxs-lookup"><span data-stu-id="d9d17-116">[Application](application-element-net-native.md) [0:1]</span></span>
    - <span data-ttu-id="d9d17-117">[Assembly](assembly-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="d9d17-117">[Assembly](assembly-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="d9d17-118">[Пространство имен](namespace-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="d9d17-118">[Namespace](namespace-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="d9d17-119">.</span><span class="sxs-lookup"><span data-stu-id="d9d17-119">.</span></span> <span data-ttu-id="d9d17-120">.</span><span class="sxs-lookup"><span data-stu-id="d9d17-120">.</span></span>
      - <span data-ttu-id="d9d17-121">[Введите](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="d9d17-121">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="d9d17-122">.</span><span class="sxs-lookup"><span data-stu-id="d9d17-122">.</span></span> <span data-ttu-id="d9d17-123">.</span><span class="sxs-lookup"><span data-stu-id="d9d17-123">.</span></span>
      - <span data-ttu-id="d9d17-124">[TypeInstantiation](typeinstantiation-element-net-native.md) (сконструированный универсальный тип) [0: M].</span><span class="sxs-lookup"><span data-stu-id="d9d17-124">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="d9d17-125">.</span><span class="sxs-lookup"><span data-stu-id="d9d17-125">.</span></span> <span data-ttu-id="d9d17-126">.</span><span class="sxs-lookup"><span data-stu-id="d9d17-126">.</span></span>
    - <span data-ttu-id="d9d17-127">[Namespace](namespace-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="d9d17-127">[Namespace](namespace-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="d9d17-128">[Пространство имен](namespace-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="d9d17-128">[Namespace](namespace-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="d9d17-129">.</span><span class="sxs-lookup"><span data-stu-id="d9d17-129">.</span></span> <span data-ttu-id="d9d17-130">.</span><span class="sxs-lookup"><span data-stu-id="d9d17-130">.</span></span>
      - <span data-ttu-id="d9d17-131">[Введите](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="d9d17-131">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="d9d17-132">.</span><span class="sxs-lookup"><span data-stu-id="d9d17-132">.</span></span> <span data-ttu-id="d9d17-133">.</span><span class="sxs-lookup"><span data-stu-id="d9d17-133">.</span></span>
      - <span data-ttu-id="d9d17-134">[TypeInstantiation](typeinstantiation-element-net-native.md) (сконструированный универсальный тип) [0: M].</span><span class="sxs-lookup"><span data-stu-id="d9d17-134">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="d9d17-135">.</span><span class="sxs-lookup"><span data-stu-id="d9d17-135">.</span></span> <span data-ttu-id="d9d17-136">.</span><span class="sxs-lookup"><span data-stu-id="d9d17-136">.</span></span>
    - <span data-ttu-id="d9d17-137">[Type](type-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="d9d17-137">[Type](type-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="d9d17-138">[Subtypes](subtypes-element-net-native.md) (подклассы содержащего типа) [O:1]</span><span class="sxs-lookup"><span data-stu-id="d9d17-138">[Subtypes](subtypes-element-net-native.md) (subclasses of the containing type) [O:1]</span></span>
      - <span data-ttu-id="d9d17-139">[Введите](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="d9d17-139">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="d9d17-140">.</span><span class="sxs-lookup"><span data-stu-id="d9d17-140">.</span></span> <span data-ttu-id="d9d17-141">.</span><span class="sxs-lookup"><span data-stu-id="d9d17-141">.</span></span>
      - <span data-ttu-id="d9d17-142">[TypeInstantiation](typeinstantiation-element-net-native.md) (сконструированный универсальный тип) [0: M].</span><span class="sxs-lookup"><span data-stu-id="d9d17-142">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="d9d17-143">.</span><span class="sxs-lookup"><span data-stu-id="d9d17-143">.</span></span> <span data-ttu-id="d9d17-144">.</span><span class="sxs-lookup"><span data-stu-id="d9d17-144">.</span></span>
      - <span data-ttu-id="d9d17-145">[AttributeImplies](attributeimplies-element-net-native.md) (содержащий тип является атрибутом) [O:1]</span><span class="sxs-lookup"><span data-stu-id="d9d17-145">[AttributeImplies](attributeimplies-element-net-native.md) (containing type is an attribute) [O:1]</span></span>
      - <span data-ttu-id="d9d17-146">[GenericParameter](genericparameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="d9d17-146">[GenericParameter](genericparameter-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="d9d17-147">[Method](method-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="d9d17-147">[Method](method-element-net-native.md) [0:M]</span></span>
        - <span data-ttu-id="d9d17-148">[Parameter](parameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="d9d17-148">[Parameter](parameter-element-net-native.md) [0:M]</span></span>
        - <span data-ttu-id="d9d17-149">[TypeParameter](typeparameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="d9d17-149">[TypeParameter](typeparameter-element-net-native.md) [0:M]</span></span>
        - <span data-ttu-id="d9d17-150">[GenericParameter](genericparameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="d9d17-150">[GenericParameter](genericparameter-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="d9d17-151">[MethodInstantiation](methodinstantiation-element-net-native.md) (сконструированного универсального типа) [0:M]</span><span class="sxs-lookup"><span data-stu-id="d9d17-151">[MethodInstantiation](methodinstantiation-element-net-native.md) (constructed generic method) [0:M]</span></span>
      - <span data-ttu-id="d9d17-152">[Property](property-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="d9d17-152">[Property](property-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="d9d17-153">[Field](field-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="d9d17-153">[Field](field-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="d9d17-154">[Event](event-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="d9d17-154">[Event](event-element-net-native.md) [0:M]</span></span>
    - <span data-ttu-id="d9d17-155">[TypeInstantiation](typeinstantiation-element-net-native.md) (сконструированного универсального типа) [0:M]</span><span class="sxs-lookup"><span data-stu-id="d9d17-155">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M]</span></span>
      - <span data-ttu-id="d9d17-156">[Введите](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="d9d17-156">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="d9d17-157">.</span><span class="sxs-lookup"><span data-stu-id="d9d17-157">.</span></span> <span data-ttu-id="d9d17-158">.</span><span class="sxs-lookup"><span data-stu-id="d9d17-158">.</span></span>
      - <span data-ttu-id="d9d17-159">[TypeInstantiation](typeinstantiation-element-net-native.md) (сконструированный универсальный тип) [0: M].</span><span class="sxs-lookup"><span data-stu-id="d9d17-159">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="d9d17-160">.</span><span class="sxs-lookup"><span data-stu-id="d9d17-160">.</span></span> <span data-ttu-id="d9d17-161">.</span><span class="sxs-lookup"><span data-stu-id="d9d17-161">.</span></span>
      - <span data-ttu-id="d9d17-162">[Method](method-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="d9d17-162">[Method](method-element-net-native.md) [0:M]</span></span>
        - <span data-ttu-id="d9d17-163">[Parameter](parameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="d9d17-163">[Parameter](parameter-element-net-native.md) [0:M]</span></span>
        - <span data-ttu-id="d9d17-164">[TypeParameter](typeparameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="d9d17-164">[TypeParameter](typeparameter-element-net-native.md) [0:M]</span></span>
        - <span data-ttu-id="d9d17-165">[GenericParameter](genericparameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="d9d17-165">[GenericParameter](genericparameter-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="d9d17-166">[MethodInstantiation](methodinstantiation-element-net-native.md) (сконструированного универсального типа) [0:M]</span><span class="sxs-lookup"><span data-stu-id="d9d17-166">[MethodInstantiation](methodinstantiation-element-net-native.md) (constructed generic method) [0:M]</span></span>
      - <span data-ttu-id="d9d17-167">[Property](property-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="d9d17-167">[Property](property-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="d9d17-168">[Field](field-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="d9d17-168">[Field](field-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="d9d17-169">[Event](event-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="d9d17-169">[Event](event-element-net-native.md) [0:M]</span></span>
  - <span data-ttu-id="d9d17-170">[Library](library-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="d9d17-170">[Library](library-element-net-native.md) [0:M]</span></span>
    - <span data-ttu-id="d9d17-171">[Assembly](assembly-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="d9d17-171">[Assembly](assembly-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="d9d17-172">[Пространство имен](namespace-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="d9d17-172">[Namespace](namespace-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="d9d17-173">.</span><span class="sxs-lookup"><span data-stu-id="d9d17-173">.</span></span> <span data-ttu-id="d9d17-174">.</span><span class="sxs-lookup"><span data-stu-id="d9d17-174">.</span></span>
      - <span data-ttu-id="d9d17-175">[Введите](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="d9d17-175">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="d9d17-176">.</span><span class="sxs-lookup"><span data-stu-id="d9d17-176">.</span></span> <span data-ttu-id="d9d17-177">.</span><span class="sxs-lookup"><span data-stu-id="d9d17-177">.</span></span>
      - <span data-ttu-id="d9d17-178">[TypeInstantiation](typeinstantiation-element-net-native.md) (сконструированный универсальный тип) [0: M].</span><span class="sxs-lookup"><span data-stu-id="d9d17-178">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="d9d17-179">.</span><span class="sxs-lookup"><span data-stu-id="d9d17-179">.</span></span> <span data-ttu-id="d9d17-180">.</span><span class="sxs-lookup"><span data-stu-id="d9d17-180">.</span></span>
    - <span data-ttu-id="d9d17-181">[Namespace](namespace-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="d9d17-181">[Namespace](namespace-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="d9d17-182">[Пространство имен](namespace-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="d9d17-182">[Namespace](namespace-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="d9d17-183">.</span><span class="sxs-lookup"><span data-stu-id="d9d17-183">.</span></span> <span data-ttu-id="d9d17-184">.</span><span class="sxs-lookup"><span data-stu-id="d9d17-184">.</span></span>
      - <span data-ttu-id="d9d17-185">[Введите](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="d9d17-185">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="d9d17-186">.</span><span class="sxs-lookup"><span data-stu-id="d9d17-186">.</span></span> <span data-ttu-id="d9d17-187">.</span><span class="sxs-lookup"><span data-stu-id="d9d17-187">.</span></span>
      - <span data-ttu-id="d9d17-188">[TypeInstantiation](typeinstantiation-element-net-native.md) (сконструированный универсальный тип) [0: M].</span><span class="sxs-lookup"><span data-stu-id="d9d17-188">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="d9d17-189">.</span><span class="sxs-lookup"><span data-stu-id="d9d17-189">.</span></span> <span data-ttu-id="d9d17-190">.</span><span class="sxs-lookup"><span data-stu-id="d9d17-190">.</span></span>
    - <span data-ttu-id="d9d17-191">[Type](type-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="d9d17-191">[Type](type-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="d9d17-192">[Subtypes](subtypes-element-net-native.md) (подклассы содержащего типа) [O:1]</span><span class="sxs-lookup"><span data-stu-id="d9d17-192">[Subtypes](subtypes-element-net-native.md) (subclasses of the containing type) [O:1]</span></span>
      - <span data-ttu-id="d9d17-193">[Введите](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="d9d17-193">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="d9d17-194">.</span><span class="sxs-lookup"><span data-stu-id="d9d17-194">.</span></span> <span data-ttu-id="d9d17-195">.</span><span class="sxs-lookup"><span data-stu-id="d9d17-195">.</span></span>
      - <span data-ttu-id="d9d17-196">[TypeInstantiation](typeinstantiation-element-net-native.md) (сконструированный универсальный тип) [0: M].</span><span class="sxs-lookup"><span data-stu-id="d9d17-196">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="d9d17-197">.</span><span class="sxs-lookup"><span data-stu-id="d9d17-197">.</span></span> <span data-ttu-id="d9d17-198">.</span><span class="sxs-lookup"><span data-stu-id="d9d17-198">.</span></span>
      - <span data-ttu-id="d9d17-199">[AttributeImplies](attributeimplies-element-net-native.md) (содержащий тип является атрибутом) [O:1]</span><span class="sxs-lookup"><span data-stu-id="d9d17-199">[AttributeImplies](attributeimplies-element-net-native.md) (containing type is an attribute) [O:1]</span></span>
      - <span data-ttu-id="d9d17-200">[GenericParameter](genericparameter-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="d9d17-200">[GenericParameter](genericparameter-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="d9d17-201">[Method](method-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="d9d17-201">[Method](method-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="d9d17-202">[MethodInstantiation](methodinstantiation-element-net-native.md) (сконструированного универсального типа) [0:M]</span><span class="sxs-lookup"><span data-stu-id="d9d17-202">[MethodInstantiation](methodinstantiation-element-net-native.md) (constructed generic method) [0:M]</span></span>
      - <span data-ttu-id="d9d17-203">[Property](property-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="d9d17-203">[Property](property-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="d9d17-204">[Field](field-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="d9d17-204">[Field](field-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="d9d17-205">[Event](event-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="d9d17-205">[Event](event-element-net-native.md) [0:M]</span></span>
    - <span data-ttu-id="d9d17-206">[TypeInstantiation](typeinstantiation-element-net-native.md) (сконструированного универсального типа) [0:M]</span><span class="sxs-lookup"><span data-stu-id="d9d17-206">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M]</span></span>
      - <span data-ttu-id="d9d17-207">[Введите](type-element-net-native.md) [0: M].</span><span class="sxs-lookup"><span data-stu-id="d9d17-207">[Type](type-element-net-native.md) [0:M] .</span></span> <span data-ttu-id="d9d17-208">.</span><span class="sxs-lookup"><span data-stu-id="d9d17-208">.</span></span> <span data-ttu-id="d9d17-209">.</span><span class="sxs-lookup"><span data-stu-id="d9d17-209">.</span></span>
      - <span data-ttu-id="d9d17-210">[TypeInstantiation](typeinstantiation-element-net-native.md) (сконструированный универсальный тип) [0: M].</span><span class="sxs-lookup"><span data-stu-id="d9d17-210">[TypeInstantiation](typeinstantiation-element-net-native.md) (constructed generic type) [0:M] .</span></span> <span data-ttu-id="d9d17-211">.</span><span class="sxs-lookup"><span data-stu-id="d9d17-211">.</span></span> <span data-ttu-id="d9d17-212">.</span><span class="sxs-lookup"><span data-stu-id="d9d17-212">.</span></span>
      - <span data-ttu-id="d9d17-213">[Method](method-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="d9d17-213">[Method](method-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="d9d17-214">[MethodInstantiation](methodinstantiation-element-net-native.md) (сконструированного универсального типа) [0:M]</span><span class="sxs-lookup"><span data-stu-id="d9d17-214">[MethodInstantiation](methodinstantiation-element-net-native.md) (constructed generic method) [0:M]</span></span>
      - <span data-ttu-id="d9d17-215">[Property](property-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="d9d17-215">[Property](property-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="d9d17-216">[Field](field-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="d9d17-216">[Field](field-element-net-native.md) [0:M]</span></span>
      - <span data-ttu-id="d9d17-217">[Event](event-element-net-native.md) [0:M]</span><span class="sxs-lookup"><span data-stu-id="d9d17-217">[Event](event-element-net-native.md) [0:M]</span></span>

<span data-ttu-id="d9d17-218">Элемент [Application](application-element-net-native.md) может не иметь атрибутов или иметь атрибуты политики, рассмотренные в разделе [Директивы и политика среды выполнения](#Directives).</span><span class="sxs-lookup"><span data-stu-id="d9d17-218">The [Application](application-element-net-native.md) element can have no attributes, or it can have the policy attributes discussed in the [Runtime directive and policy section](#Directives).</span></span>

<span data-ttu-id="d9d17-219">Элемент [Library](library-element-net-native.md) имеет один атрибут `Name`, который определяет имя библиотеки или сборки без расширения файла.</span><span class="sxs-lookup"><span data-stu-id="d9d17-219">A [Library](library-element-net-native.md) element has a single attribute, `Name`, that specifies the name of a library or assembly, without its file extension.</span></span> <span data-ttu-id="d9d17-220">Например, следующий элемент [Library](library-element-net-native.md) применяется к сборке с именем Extensions.dll.</span><span class="sxs-lookup"><span data-stu-id="d9d17-220">For example, the following [Library](library-element-net-native.md) element applies to an assembly named Extensions.dll.</span></span>

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
  <Application>
     <!-- Child elements go here -->
  </Application>
  <Library Name="Extensions">
     <!-- Child elements go here -->
  </Library>
</Directives>
```

<a name="Directives"></a>

## <a name="runtime-directives-and-policy"></a><span data-ttu-id="d9d17-221">Директивы и политики среды выполнения</span><span class="sxs-lookup"><span data-stu-id="d9d17-221">Runtime directives and policy</span></span>

<span data-ttu-id="d9d17-222">Сам элемент [Application](application-element-net-native.md), а также дочерние элементы элементов [Library](library-element-net-native.md) и [Application](application-element-net-native.md) определяют политику, то есть способ, с помощью которого приложение может применять отражение к программному элементу.</span><span class="sxs-lookup"><span data-stu-id="d9d17-222">The [Application](application-element-net-native.md) element itself and the child elements of the [Library](library-element-net-native.md) and [Application](application-element-net-native.md) elements express policy; that is, they define the way in which an app can apply reflection to a program element.</span></span> <span data-ttu-id="d9d17-223">Тип политики определяется с помощью атрибута элемента (например, `Serialize`).</span><span class="sxs-lookup"><span data-stu-id="d9d17-223">The policy type is defined by an attribute of the element (for example, `Serialize`).</span></span> <span data-ttu-id="d9d17-224">Значение политики определяется значением атрибута (например, `Serialize="Required"`).</span><span class="sxs-lookup"><span data-stu-id="d9d17-224">The policy value is defined by the attribute’s value (for example, `Serialize="Required"`).</span></span>

<span data-ttu-id="d9d17-225">Любая политика, заданная с помощью атрибута элемента применяется ко всем дочерним элементам, которые не определяют значение этой политики.</span><span class="sxs-lookup"><span data-stu-id="d9d17-225">Any policy specified by an attribute of an element applies to all child elements that don’t specify a value for that policy.</span></span> <span data-ttu-id="d9d17-226">Например, если политика определяется элементом [Type](type-element-net-native.md), эта политика применяется для всех вложенных типов и членов, для которых политика не указана явно.</span><span class="sxs-lookup"><span data-stu-id="d9d17-226">For example, if a policy is specified by a [Type](type-element-net-native.md) element, that policy applies to all contained types and members for which a policy is not explicitly specified.</span></span>

<span data-ttu-id="d9d17-227">Политика, которая может быть определена элементами [Application](application-element-net-native.md), [Assembly](assembly-element-net-native.md), [AttributeImplies](attributeimplies-element-net-native.md), [Namespace](namespace-element-net-native.md), [Subtypes](subtypes-element-net-native.md) и [Type](type-element-net-native.md), отличается от политики, которая может быть определена для отдельных членов (элементами [Method](method-element-net-native.md), [Property](property-element-net-native.md), [Field](field-element-net-native.md) и [Event](event-element-net-native.md)).</span><span class="sxs-lookup"><span data-stu-id="d9d17-227">The policy that can be expressed by the [Application](application-element-net-native.md), [Assembly](assembly-element-net-native.md), [AttributeImplies](attributeimplies-element-net-native.md), [Namespace](namespace-element-net-native.md), [Subtypes](subtypes-element-net-native.md), and [Type](type-element-net-native.md) elements differs from the policy that can be expressed for individual members (by the [Method](method-element-net-native.md), [Property](property-element-net-native.md), [Field](field-element-net-native.md), and [Event](event-element-net-native.md) elements).</span></span>

### <a name="specifying-policy-for-assemblies-namespaces-and-types"></a><span data-ttu-id="d9d17-228">Задание политики для сборок, пространств имен и типов</span><span class="sxs-lookup"><span data-stu-id="d9d17-228">Specifying policy for assemblies, namespaces, and types</span></span>

<span data-ttu-id="d9d17-229">Элементы [Application](application-element-net-native.md), [Assembly](assembly-element-net-native.md), [AttributeImplies](attributeimplies-element-net-native.md), [Namespace](namespace-element-net-native.md), [Subtypes](subtypes-element-net-native.md) и [Type](type-element-net-native.md) поддерживают следующие типы политик:</span><span class="sxs-lookup"><span data-stu-id="d9d17-229">The [Application](application-element-net-native.md), [Assembly](assembly-element-net-native.md), [AttributeImplies](attributeimplies-element-net-native.md), [Namespace](namespace-element-net-native.md), [Subtypes](subtypes-element-net-native.md), and [Type](type-element-net-native.md) elements support the following policy types:</span></span>

- <span data-ttu-id="d9d17-230">`Activate`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-230">`Activate`.</span></span> <span data-ttu-id="d9d17-231">Управляет доступом среды выполнения к конструкторам для включения активации экземпляров.</span><span class="sxs-lookup"><span data-stu-id="d9d17-231">Controls runtime access to constructors, to enable activation of instances.</span></span>

- <span data-ttu-id="d9d17-232">`Browse`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-232">`Browse`.</span></span> <span data-ttu-id="d9d17-233">Управляет запросами для получения сведений об элементах программы, но не включает доступ среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="d9d17-233">Controls querying for information about program elements but does not enable any runtime access.</span></span>

- <span data-ttu-id="d9d17-234">`Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-234">`Dynamic`.</span></span> <span data-ttu-id="d9d17-235">Управляет доступом среды выполнения ко всем членам типа, включая конструкторы, методы, поля, свойства и события, чтобы включить динамическое программирование.</span><span class="sxs-lookup"><span data-stu-id="d9d17-235">Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span>

- <span data-ttu-id="d9d17-236">`Serialize`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-236">`Serialize`.</span></span> <span data-ttu-id="d9d17-237">Управляет доступом среды выполнения к конструкторам, полям и свойствам, позволяющим сериализовать и десериализовать экземпляры типа с помощью таких библиотек сторонних поставщиков, как сериализатор Newtonsoft JSON.</span><span class="sxs-lookup"><span data-stu-id="d9d17-237">Controls runtime access to constructors, fields, and properties, to enable type instances to be serialized and serialized by third-party libraries such as the Newtonsoft JSON serializer.</span></span>

- <span data-ttu-id="d9d17-238">`DataContractSerializer`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-238">`DataContractSerializer`.</span></span> <span data-ttu-id="d9d17-239">Определяет политику для сериализации, в которой используется класс <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d9d17-239">Controls policy for serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>

- <span data-ttu-id="d9d17-240">`DataContractJsonSerializer`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-240">`DataContractJsonSerializer`.</span></span> <span data-ttu-id="d9d17-241">Определяет политику для сериализации JSON, в которой используется класс <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d9d17-241">Controls policy for JSON serialization that uses the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType> class.</span></span>

- <span data-ttu-id="d9d17-242">`XmlSerializer`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-242">`XmlSerializer`.</span></span> <span data-ttu-id="d9d17-243">Определяет политику для сериализации XML, в которой используется класс <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d9d17-243">Controls policy for XML serialization that uses the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> class.</span></span>

- <span data-ttu-id="d9d17-244">`MarshalObject`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-244">`MarshalObject`.</span></span> <span data-ttu-id="d9d17-245">Определяет политику для маршалинга ссылочных типов в WinRT и COM.</span><span class="sxs-lookup"><span data-stu-id="d9d17-245">Controls policy for marshaling reference types to WinRT and COM.</span></span>

- <span data-ttu-id="d9d17-246">`MarshalDelegate`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-246">`MarshalDelegate`.</span></span> <span data-ttu-id="d9d17-247">Определяет политики для маршалинга типов делегатов как указателей функции на машинный код.</span><span class="sxs-lookup"><span data-stu-id="d9d17-247">Controls policy for marshaling delegate types as function pointers to native code.</span></span>

- <span data-ttu-id="d9d17-248">`MarshalStructure` .</span><span class="sxs-lookup"><span data-stu-id="d9d17-248">`MarshalStructure` .</span></span> <span data-ttu-id="d9d17-249">Определяет политику для маршалинга структуры в машинный код.</span><span class="sxs-lookup"><span data-stu-id="d9d17-249">Controls policy for marshaling structures to native code.</span></span>

<span data-ttu-id="d9d17-250">Параметры, связанные с этими типами политики:</span><span class="sxs-lookup"><span data-stu-id="d9d17-250">The settings associated with these policy types are:</span></span>

- <span data-ttu-id="d9d17-251">`All`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-251">`All`.</span></span> <span data-ttu-id="d9d17-252">Включить политику для всех типов и членов, которые не удаляет цепочка инструментов.</span><span class="sxs-lookup"><span data-stu-id="d9d17-252">Enable the policy for all types and members that the tool chain does not remove.</span></span>

- <span data-ttu-id="d9d17-253">`Auto`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-253">`Auto`.</span></span> <span data-ttu-id="d9d17-254">Использовать поведение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d9d17-254">Use the default behavior.</span></span> <span data-ttu-id="d9d17-255">(Отсутствие назначения политики эквивалентно установке политики `Auto`, если только эта политика не переопределяется, например, родительским элементом.)</span><span class="sxs-lookup"><span data-stu-id="d9d17-255">(Not specifying a policy is equivalent to setting that policy to `Auto` unless that policy is overridden, for example by a parent element.)</span></span>

- <span data-ttu-id="d9d17-256">`Excluded`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-256">`Excluded`.</span></span> <span data-ttu-id="d9d17-257">Выключить политику для программного элемента.</span><span class="sxs-lookup"><span data-stu-id="d9d17-257">Disable the policy for the program element.</span></span>

- <span data-ttu-id="d9d17-258">`Public`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-258">`Public`.</span></span> <span data-ttu-id="d9d17-259">Включить политику для открытых типов и членов, если только цепочка средство не определяет, что элемент является необязательным и поэтому удаляет его.</span><span class="sxs-lookup"><span data-stu-id="d9d17-259">Enable the policy for public types or members unless the tool chain determines that the member is unnecessary and therefore removes it.</span></span> <span data-ttu-id="d9d17-260">(В последнем случае необходимо использовать `Required Public` чтобы обеспечить сохранение элемента с возможностями отражения.)</span><span class="sxs-lookup"><span data-stu-id="d9d17-260">(In the latter case, you must use `Required Public` to ensure that the member is kept and has reflection capabilities.)</span></span>

- <span data-ttu-id="d9d17-261">`PublicAndInternal`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-261">`PublicAndInternal`.</span></span> <span data-ttu-id="d9d17-262">Включить политику для открытых и внутренних типов и членов, если цепочка инструментов не удаляет их.</span><span class="sxs-lookup"><span data-stu-id="d9d17-262">Enable the policy for public and internal types or members if the tool chain doesn't remove them.</span></span>

- <span data-ttu-id="d9d17-263">`Required Public`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-263">`Required Public`.</span></span> <span data-ttu-id="d9d17-264">Требует, чтобы цепочка инструментов поддерживала открытые типы и члены, независимо то того, используются они или нет, и включала для них политику.</span><span class="sxs-lookup"><span data-stu-id="d9d17-264">Require the tool chain to keep public types and members whether or not they are used, and enable the policy for them.</span></span>

- <span data-ttu-id="d9d17-265">`Required PublicAndInternal`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-265">`Required PublicAndInternal`.</span></span> <span data-ttu-id="d9d17-266">Требует, чтобы цепочка инструментов поддерживала открытые и закрытые типы и члены, независимо то того, используются они или нет, и включала для них политику.</span><span class="sxs-lookup"><span data-stu-id="d9d17-266">Require the tool chain to keep both public and internal types and members whether or not they are used, and enable the policy for them.</span></span>

- <span data-ttu-id="d9d17-267">`Required All`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-267">`Required All`.</span></span> <span data-ttu-id="d9d17-268">Требует, чтобы цепочка инструментов поддерживала все типы и члены, независимо то того, используются они или нет, и включала для них политику.</span><span class="sxs-lookup"><span data-stu-id="d9d17-268">Require the tool chain to keep all types and members whether or not they are used, and enable the policy for them.</span></span>

<span data-ttu-id="d9d17-269">Например, следующий файл директив среды выполнения определяет политику для всех типов и членов в сборке DataClasses.dll.</span><span class="sxs-lookup"><span data-stu-id="d9d17-269">For example, the following runtime directives file defines policy for all types and members in the assembly DataClasses.dll.</span></span> <span data-ttu-id="d9d17-270">Он включает отражение для сериализации все открытых свойств, обзор для всех типов и членов типа, активацию для всех типов (из-за атрибута `Dynamic` атрибут), а также отражение для всех открытых типов и членов.</span><span class="sxs-lookup"><span data-stu-id="d9d17-270">It enables reflection for serialization of all public properties, enables browsing for all types and type members, enables activation for all types (because of the `Dynamic` attribute), and enables reflection for all public types and members.</span></span>

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="Required Public"
                Browse="All" Activate="PublicAndInternal"
                Dynamic="Public"  />
   </Application>
   <Library Name="UtilityLibrary">
     <!-- Child elements go here -->
   </Library>
</Directives>
```

### <a name="specifying-policy-for-members"></a><span data-ttu-id="d9d17-271">Задание политики для членов</span><span class="sxs-lookup"><span data-stu-id="d9d17-271">Specifying policy for members</span></span>

<span data-ttu-id="d9d17-272">Элементы [Property](property-element-net-native.md) и [Field](field-element-net-native.md) поддерживают следующие типы политик:</span><span class="sxs-lookup"><span data-stu-id="d9d17-272">The [Property](property-element-net-native.md) and [Field](field-element-net-native.md) elements support the following policy types:</span></span>

- <span data-ttu-id="d9d17-273">`Browse` — Управляет запросами для получения сведений о члене, но не включает доступ среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="d9d17-273">`Browse` - Controls querying for information about this member but does not enable any runtime access.</span></span>

- <span data-ttu-id="d9d17-274">`Dynamic` — Управляет доступом среды выполнения ко всем членам типа, включая конструкторы, методы, поля, свойства и события, чтобы включить динамическое программирование.</span><span class="sxs-lookup"><span data-stu-id="d9d17-274">`Dynamic` - Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span> <span data-ttu-id="d9d17-275">Также управляет запросами сведений о содержащем типе.</span><span class="sxs-lookup"><span data-stu-id="d9d17-275">Also controls querying for information about the containing type.</span></span>

- <span data-ttu-id="d9d17-276">`Serialize` — Управляет доступом среды выполнения к членам, позволяющим сериализовать и десериализовать экземпляры типа с помощью таких библиотек, как, например, сериализатор Newtonsoft JSON.</span><span class="sxs-lookup"><span data-stu-id="d9d17-276">`Serialize` - Controls runtime access to the member to enable type instances to be serialized and deserialized by libraries such as the Newtonsoft JSON serializer.</span></span> <span data-ttu-id="d9d17-277">Эта политика может применяться для конструкторов, полей и свойств.</span><span class="sxs-lookup"><span data-stu-id="d9d17-277">This policy can be applied to constructors, fields, and properties.</span></span>

<span data-ttu-id="d9d17-278">Элементы [Method](method-element-net-native.md) и [Event](event-element-net-native.md) поддерживают следующие типы политик:</span><span class="sxs-lookup"><span data-stu-id="d9d17-278">The [Method](method-element-net-native.md) and [Event](event-element-net-native.md) elements support the following policy types:</span></span>

- <span data-ttu-id="d9d17-279">`Browse` — Управляет запросами для получения сведений о члене, но не включает доступ среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="d9d17-279">`Browse` - Controls querying for information about this member but doesn’t enable any runtime access.</span></span>

- <span data-ttu-id="d9d17-280">`Dynamic` — Управляет доступом среды выполнения ко всем членам типа, включая конструкторы, методы, поля, свойства и события, чтобы включить динамическое программирование.</span><span class="sxs-lookup"><span data-stu-id="d9d17-280">`Dynamic` - Controls runtime access to all type members, including constructors, methods, fields, properties, and events, to enable dynamic programming.</span></span> <span data-ttu-id="d9d17-281">Также управляет запросами сведений о содержащем типе.</span><span class="sxs-lookup"><span data-stu-id="d9d17-281">Also controls querying for information about the containing type.</span></span>

 <span data-ttu-id="d9d17-282">Параметры, связанные с этими типами политики:</span><span class="sxs-lookup"><span data-stu-id="d9d17-282">The settings associated with these policy types are:</span></span>

- <span data-ttu-id="d9d17-283">`Auto` — Использовать поведение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d9d17-283">`Auto` - Use the default behavior.</span></span> <span data-ttu-id="d9d17-284">(Отсутствие назначения политики эквивалентно установке политики `Auto`, если только что-то ее не переопределяет.)</span><span class="sxs-lookup"><span data-stu-id="d9d17-284">(Not specifying a policy is equivalent to setting that policy to `Auto` unless something overrides it.)</span></span>

- <span data-ttu-id="d9d17-285">`Excluded` — никогда не включать метаданные для члена.</span><span class="sxs-lookup"><span data-stu-id="d9d17-285">`Excluded` - Never include metadata for the member.</span></span>

- <span data-ttu-id="d9d17-286">`Included`- включить политику, если родительский тип присутствует в выходных данных.</span><span class="sxs-lookup"><span data-stu-id="d9d17-286">`Included` - Enable the policy if the parent type is present in the output.</span></span>

- <span data-ttu-id="d9d17-287">`Required` — Требует, чтобы цепочка инструментов поддерживала этот член, даже если он не используется, и включала для него политику.</span><span class="sxs-lookup"><span data-stu-id="d9d17-287">`Required` - Require the tool chain to keep this member even if appears to be unused, and enable policy for it.</span></span>

## <a name="runtime-directives-file-semantics"></a><span data-ttu-id="d9d17-288">Семантика файла директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="d9d17-288">Runtime directives file semantics</span></span>

<span data-ttu-id="d9d17-289">Политики могут быть определены одновременно для элементов более высокого уровня и более низкого уровня.</span><span class="sxs-lookup"><span data-stu-id="d9d17-289">Policy can be defined simultaneously for both higher-level and lower-level elements.</span></span> <span data-ttu-id="d9d17-290">Например, можно определить политики для сборки, а также для некоторых типов, содержащегося в этой сборке.</span><span class="sxs-lookup"><span data-stu-id="d9d17-290">For example, policy can be defined for an assembly, and for some of the types contained in that assembly.</span></span> <span data-ttu-id="d9d17-291">Если конкретный элемент нижнего уровня не представлен, он наследует политику родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="d9d17-291">If a particular lower-level element is not represented, it inherits the policy of its parent.</span></span> <span data-ttu-id="d9d17-292">Например, если элемент `Assembly` присутствует, а элементы `Type` нет, то политика, указанная в элементе `Assembly`, применяется для каждого типа в сборке.</span><span class="sxs-lookup"><span data-stu-id="d9d17-292">For example, if an `Assembly` element is present but `Type` elements are not, the policy specified in the `Assembly` element applies to each type in the assembly.</span></span> <span data-ttu-id="d9d17-293">Несколько элементов могут также применить политику к одному и тому же программному элементу.</span><span class="sxs-lookup"><span data-stu-id="d9d17-293">Multiple elements can also apply policy to the same program element.</span></span> <span data-ttu-id="d9d17-294">Например, отдельные элементы [Assembly](assembly-element-net-native.md) могут определять один и тот же элемент политики для одной сборки по-разному.</span><span class="sxs-lookup"><span data-stu-id="d9d17-294">For example, separate [Assembly](assembly-element-net-native.md) elements might define the same policy element for the same assembly differently.</span></span> <span data-ttu-id="d9d17-295">В следующих разделах объясняется, как политики для конкретного типа разрешается в таких случаях.</span><span class="sxs-lookup"><span data-stu-id="d9d17-295">The following sections explain how the policy for a particular type is resolved in those cases.</span></span>

<span data-ttu-id="d9d17-296">Элемент [Type](type-element-net-native.md) или [Method](method-element-net-native.md) универсального типа или метода применяет свою политику для всех экземпляров, которые не имеют собственной политики.</span><span class="sxs-lookup"><span data-stu-id="d9d17-296">A [Type](type-element-net-native.md) or [Method](method-element-net-native.md) element of a generic type or method applies its policy to all instantiations that do not have their own policy.</span></span> <span data-ttu-id="d9d17-297">Например, элемент `Type`, который определяет политику для <xref:System.Collections.Generic.List%601>, применяется для всех сконструированных экземпляров универсального типа, если только он переопределяется для определенного сконструированного универсального типа (например, `List<Int32>`) элементом `TypeInstantiation` .</span><span class="sxs-lookup"><span data-stu-id="d9d17-297">For example, a `Type` element that specifies policy for <xref:System.Collections.Generic.List%601> applies to all constructed instances of that generic type, unless it's overridden for a particular constructed generic type (such as a `List<Int32>`) by a `TypeInstantiation` element.</span></span> <span data-ttu-id="d9d17-298">В противном случае, элементы определяют политику для именованного программного элемента.</span><span class="sxs-lookup"><span data-stu-id="d9d17-298">Otherwise, elements define policy for the program element named.</span></span>

<span data-ttu-id="d9d17-299">Если элемент является неоднозначным, ядро ищет совпадения и при обнаружении точного совпадения, будет ее использовать.</span><span class="sxs-lookup"><span data-stu-id="d9d17-299">When an element is ambiguous, the engine looks for matches, and if it finds an exact match, it will use it.</span></span> <span data-ttu-id="d9d17-300">При обнаружении нескольких совпадений будет предупреждение или ошибка.</span><span class="sxs-lookup"><span data-stu-id="d9d17-300">If it finds multiple matches, there will be a warning or error.</span></span>

### <a name="if-two-directives-apply-policy-to-the-same-program-element"></a><span data-ttu-id="d9d17-301">Если две директивы применяют политику к одному и тому же программному элементу</span><span class="sxs-lookup"><span data-stu-id="d9d17-301">If two directives apply policy to the same program element</span></span>

<span data-ttu-id="d9d17-302">Если два элемента в разных файлах директив среды выполнения пытаются установить один и тот же тип политики для одного программного элемента (например, сборки или типа) в разные значения, конфликт разрешается следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d9d17-302">If two elements in different runtime directives files try to set the same policy type for the same program element (such as an assembly or type) to different values, the conflict is resolved as follows:</span></span>

1. <span data-ttu-id="d9d17-303">Если элемент `Excluded` присутствует, он имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="d9d17-303">If the `Excluded` element is present, it has precedence.</span></span>

2. <span data-ttu-id="d9d17-304">`Required`имеет приоритет над не `Required`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-304">`Required` has precedence over not `Required`.</span></span>

3. <span data-ttu-id="d9d17-305">`All`имеет приоритет перед `PublicAndInternal`, который имеет приоритет над `Public`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-305">`All` has precedence over `PublicAndInternal`, which has precedence over `Public`.</span></span>

4. <span data-ttu-id="d9d17-306">Любой явный параметр имеет приоритет над `Auto`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-306">Any explicit setting has precedence over `Auto`.</span></span>

<span data-ttu-id="d9d17-307">Например, если один проект включает следующие два файла директив среды выполнения, устанавливается политика сериализации для DataClasses.dll на `Required Public` и `All`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-307">For example, if a single project includes the following two runtime directives files, the serialization policy for DataClasses.dll is set to both `Required Public` and `All`.</span></span> <span data-ttu-id="d9d17-308">В этом случае политика сериализации будет разрешаться как `Required All`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-308">In this case, the serialization policy would be resolved as `Required All`.</span></span>

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="Required Public"/>
   </Application>
   <Library Name="DataClasses">
      <!-- any other elements -->
   </Library>
</Directives>
```

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="All" />
   </Application>
   <Library Name="DataClasses">
      <!-- any other elements -->
   </Library>
</Directives>
```

<span data-ttu-id="d9d17-309">Однако, если две директивы в файле директив среды выполнения пытаются задать один и тот же тип политики одному программному элементу, то инструмент определения схемы XML отображает сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="d9d17-309">However, if two directives in a single runtime directives file try to set the same policy type for the same program element, the XML Scheme Definition tool displays an error message.</span></span>

### <a name="if-child-and-parent-elements-apply-the-same-policy-type"></a><span data-ttu-id="d9d17-310">Если один и тот же тип политики применяется дочерними и родительскими элементами</span><span class="sxs-lookup"><span data-stu-id="d9d17-310">If child and parent elements apply the same policy type</span></span>

<span data-ttu-id="d9d17-311">Дочерние элементы переопределяют свои родительские элементы, в том числе параметр `Excluded`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-311">Child elements override their parent elements, including the `Excluded` setting.</span></span> <span data-ttu-id="d9d17-312">Переопределение — основная причина, по которой требуется указать `Auto`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-312">Overriding is the main reason you would want to specify `Auto`.</span></span>

<span data-ttu-id="d9d17-313">В следующем примере параметр политики сериализации для значения everything в `DataClasses`, который не находится в`DataClasses.ViewModels`, был бы `Required Public`, а значение everything в `DataClasses` и `DataClasses.ViewModels` было бы `All`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-313">In the following example, the serialization policy setting for everything in `DataClasses` that’s not in `DataClasses.ViewModels` would be `Required Public`, and everything that's in both `DataClasses` and `DataClasses.ViewModels` would be `All`.</span></span>

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="Required Public" >
         <Namespace Name="DataClasses.ViewModels" Serialize="All" />
      </Assembly>
   </Application>
   <Library Name="DataClasses">
      <!-- any other elements -->
   </Library>
</Directives>
```

### <a name="if-open-generics-and-instantiated-elements-apply-the-same-policy-type"></a><span data-ttu-id="d9d17-314">Если открытые универсальные типы и элементы экземпляра применяют один и тот же тип политики</span><span class="sxs-lookup"><span data-stu-id="d9d17-314">If open generics and instantiated elements apply the same policy type</span></span>

<span data-ttu-id="d9d17-315">В следующем примере `Dictionary<int,int>` назначается как политика  `Browse`, только если ядро имеет еще одну причину присвоить политику `Browse` (что было бы в противном случае поведением по умолчанию); В каждом экземпляре <xref:System.Collections.Generic.Dictionary%602> все члены будут доступны для просмотра.</span><span class="sxs-lookup"><span data-stu-id="d9d17-315">In the following example, `Dictionary<int,int>` is assigned the `Browse` policy only if the engine has another reason to give it the `Browse` policy (which would otherwise be the default behavior); every other instantiation of <xref:System.Collections.Generic.Dictionary%602> will have all of its members browsable.</span></span>

```xml
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">
   <Application>
      <Assembly Name="DataClasses" Serialize="Required Public" >
         <Namespace Name="DataClasses.ViewModels" Serialize="All" />
      </Assembly>
      <Namespace Name="DataClasses.Generics" />
      <Type Name="Dictionary" Browse="All" />
      <TypeInstantiation Name="Dictionary"
                         Arguments="System.Int32,System.Int32" Browse="Auto" />
   </Application>
   <Library Name="DataClasses">
      <!-- any other elements -->
   </Library>
</Directives>
```

### <a name="how-policy-is-inferred"></a><span data-ttu-id="d9d17-316">Как определяется политика</span><span class="sxs-lookup"><span data-stu-id="d9d17-316">How policy is inferred</span></span>

<span data-ttu-id="d9d17-317">Каждый тип политики имеет разный набор правил, определяющих, как присутствие этого типа политики влияет на другие конструкции.</span><span class="sxs-lookup"><span data-stu-id="d9d17-317">Each policy type has a different set of rules that determine how the presence of that policy type affects other constructs.</span></span>

#### <a name="the-effect-of-browse-policy"></a><span data-ttu-id="d9d17-318">Эффект политики Browse (Просмотр)</span><span class="sxs-lookup"><span data-stu-id="d9d17-318">The effect of Browse policy</span></span>

<span data-ttu-id="d9d17-319">Применение политики `Browse` для типа включает в себя следующие изменения политики:</span><span class="sxs-lookup"><span data-stu-id="d9d17-319">Applying the `Browse` policy to a type involves the following policy changes:</span></span>

- <span data-ttu-id="d9d17-320">Базовый тип типа помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-320">The base type of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="d9d17-321">Если экземпляр универсального типа, версия типа без создания экземпляра помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-321">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="d9d17-322">Если тип является делегатом, метод `Invoke` типа помечается политикой `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-322">If the type is a delegate, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="d9d17-323">Каждый интерфейс типа помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-323">Each interface of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="d9d17-324">Тип каждого атрибута примененного к типу помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-324">The type of each attribute applied to the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="d9d17-325">Если тип является универсальным, каждое ограничение типа помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-325">If the type is generic, each constraint type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="d9d17-326">Если тип универсален, типы, по которым создается экземпляр типа, помечаются политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-326">If the type is generic, the types over which the type is instantiated are marked with the `Browse` policy.</span></span>

<span data-ttu-id="d9d17-327">Применение политики `Browse` для метода включает в себя следующие изменения политики:</span><span class="sxs-lookup"><span data-stu-id="d9d17-327">Applying the `Browse` policy to a method involves the following policy changes:</span></span>

- <span data-ttu-id="d9d17-328">Каждый тип параметра метода помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-328">Each parameter type of the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="d9d17-329">Возвращаемый тип метода помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-329">The return type of the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="d9d17-330">Содержащий тип метода помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-330">The containing type of the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="d9d17-331">Если метод является экземпляром универсального метода, универсальный метод без экземпляра помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-331">If the method is an instantiated generic method, the uninstantiated generic method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="d9d17-332">Тип каждого атрибута, примененного к методу, помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-332">The type of each attribute applied to the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="d9d17-333">Если метод является универсальным, каждое ограничение типа помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-333">If the method is generic, each constraint type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="d9d17-334">Если метод универсален, типы, по которым создается экземпляр метода, помечаются политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-334">If the method is generic, the types over which the method is instantiated are marked with the `Browse` policy.</span></span>

<span data-ttu-id="d9d17-335">Применение политики `Browse` для поля включает в себя следующие изменения политики:</span><span class="sxs-lookup"><span data-stu-id="d9d17-335">Applying the `Browse` policy to a field involves the following policy changes:</span></span>

- <span data-ttu-id="d9d17-336">Тип каждого атрибута, примененного к полю, помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-336">The type of each attribute applied to the field is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="d9d17-337">Тип поля помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-337">The type of the field is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="d9d17-338">Тип, к которому принадлежит поле помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-338">The type to which the field belongs is marked with the `Browse` policy.</span></span>

#### <a name="the-effect-of-dynamic-policy"></a><span data-ttu-id="d9d17-339">Эффект политики Dynamic (Динамическая)</span><span class="sxs-lookup"><span data-stu-id="d9d17-339">The effect of Dynamic policy</span></span>

<span data-ttu-id="d9d17-340">Применение политики `Dynamic` для типа включает в себя следующие изменения политики:</span><span class="sxs-lookup"><span data-stu-id="d9d17-340">Applying the `Dynamic` policy to a type involves the following policy changes:</span></span>

- <span data-ttu-id="d9d17-341">Базовый тип типа помечается политикой `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-341">The base type of the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="d9d17-342">Если экземпляр универсального типа, версия типа без создания экземпляра помечается политикой `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-342">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="d9d17-343">Если тип является делегатом, метод `Invoke` типа помечается политикой `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-343">If the type is a delegate type, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="d9d17-344">Каждый интерфейс типа помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-344">Each interface of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="d9d17-345">Тип каждого атрибута примененного к типу помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-345">The type of each attribute applied to the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="d9d17-346">Если тип является универсальным, каждое ограничение типа помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-346">If the type is generic, each constraint type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="d9d17-347">Если тип универсален, типы, по которым создается экземпляр типа, помечаются политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-347">If the type is generic, the types over which the type is instantiated are marked with the `Browse` policy.</span></span>

<span data-ttu-id="d9d17-348">Применение политики `Dynamic` для метода включает в себя следующие изменения политики:</span><span class="sxs-lookup"><span data-stu-id="d9d17-348">Applying the `Dynamic` policy to a method involves the following policy changes:</span></span>

- <span data-ttu-id="d9d17-349">Каждый тип параметра метода помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-349">Each parameter type of the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="d9d17-350">Возвращаемый тип метода помечается политикой `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-350">The return type of the method is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="d9d17-351">Содержащий тип метода помечается политикой `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-351">The containing type of the method is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="d9d17-352">Если метод является экземпляром универсального метода, универсальный метод без экземпляра помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-352">If the method is an instantiated generic method, the uninstantiated generic method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="d9d17-353">Тип каждого атрибута, примененного к методу, помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-353">The type of each attribute applied to the method is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="d9d17-354">Если метод является универсальным, каждое ограничение типа помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-354">If the method is generic, each constraint type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="d9d17-355">Если метод универсален, типы, по которым создается экземпляр метода, помечаются политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-355">If the method is generic, the types over which the method is instantiated are marked with the `Browse` policy.</span></span>

- <span data-ttu-id="d9d17-356">Этот метод может вызываться `MethodInfo.Invoke`, а создание делегата становится возможным с помощью <xref:System.Reflection.MethodInfo.CreateDelegate%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d9d17-356">The method can be invoked by `MethodInfo.Invoke`, and delegate creation becomes possible by <xref:System.Reflection.MethodInfo.CreateDelegate%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="d9d17-357">Применение политики `Dynamic` для поля включает в себя следующие изменения политики:</span><span class="sxs-lookup"><span data-stu-id="d9d17-357">Applying the `Dynamic` policy to a field involves the following policy changes:</span></span>

- <span data-ttu-id="d9d17-358">Тип каждого атрибута, примененного к полю, помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-358">The type of each attribute applied to the field is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="d9d17-359">Тип поля помечается политикой `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-359">The type of the field is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="d9d17-360">Тип, к которому принадлежит поле помечается политикой `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-360">The type to which the field belongs is marked with the `Dynamic` policy.</span></span>

#### <a name="the-effect-of-activation-policy"></a><span data-ttu-id="d9d17-361">Эффект от политики Activation (активация)</span><span class="sxs-lookup"><span data-stu-id="d9d17-361">The effect of Activation policy</span></span>

<span data-ttu-id="d9d17-362">Применение политики Activation для типа включает в себя следующие изменения политики:</span><span class="sxs-lookup"><span data-stu-id="d9d17-362">Applying the Activation policy to a type involves the following policy changes:</span></span>

- <span data-ttu-id="d9d17-363">Если экземпляр универсального типа, версия типа без создания экземпляра помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-363">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="d9d17-364">Если тип является делегатом, метод `Invoke` типа помечается политикой `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-364">If the type is a delegate type, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="d9d17-365">Конструкторы типа помечаются политикой `Activation`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-365">Constructors of the type are marked with the `Activation` policy.</span></span>

<span data-ttu-id="d9d17-366">Применение политики `Activation` для метода включает в себя следующие изменения политики:</span><span class="sxs-lookup"><span data-stu-id="d9d17-366">Applying the `Activation` policy to a method involves the following policy change:</span></span>

- <span data-ttu-id="d9d17-367">Конструктор может вызываться методами <xref:System.Reflection.ConstructorInfo.Invoke%2A?displayProperty=nameWithType> и <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d9d17-367">The constructor can be invoked by the <xref:System.Reflection.ConstructorInfo.Invoke%2A?displayProperty=nameWithType> and <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="d9d17-368">Для методов политика `Activation` оказывает действие только на конструкторы.</span><span class="sxs-lookup"><span data-stu-id="d9d17-368">For methods, the `Activation` policy affects constructors only.</span></span>

<span data-ttu-id="d9d17-369">Применение политики `Activation` к полю не оказывает влияния.</span><span class="sxs-lookup"><span data-stu-id="d9d17-369">Applying the `Activation` policy to a field has no effect.</span></span>

#### <a name="the-effect-of-serialize-policy"></a><span data-ttu-id="d9d17-370">Эффект политики Serialize (сериализация)</span><span class="sxs-lookup"><span data-stu-id="d9d17-370">The effect of Serialize policy</span></span>

<span data-ttu-id="d9d17-371">Политика `Serialize` позволяет использовать общие сериализаторы, основанные на отражении.</span><span class="sxs-lookup"><span data-stu-id="d9d17-371">The `Serialize` policy enables the use of common reflection-based serializers.</span></span> <span data-ttu-id="d9d17-372">Тем не менее, поскольку точные шаблоны доступа к отражению сериализаторов сторонних разработчиков неизвестны Microsoft, эта политика может оказаться не совсем эффективной.</span><span class="sxs-lookup"><span data-stu-id="d9d17-372">However, because the exact reflection access patterns of non-Microsoft serializers are not known to Microsoft, this policy may not be entirely effective.</span></span>

<span data-ttu-id="d9d17-373">Применение политики `Serialize` для типа включает в себя следующие изменения политики:</span><span class="sxs-lookup"><span data-stu-id="d9d17-373">Applying the `Serialize` policy to a type involves the following policy changes:</span></span>

- <span data-ttu-id="d9d17-374">Базовый тип типа помечается политикой `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-374">The base type of the type is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="d9d17-375">Если экземпляр универсального типа, версия типа без создания экземпляра помечается политикой `Browse`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-375">If the type is an instantiated generic, the uninstantiated version of the type is marked with the `Browse` policy.</span></span>

- <span data-ttu-id="d9d17-376">Если тип является делегатом, метод `Invoke` типа помечается политикой `Dynamic`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-376">If the type is a delegate type, the `Invoke` method on the type is marked with the `Dynamic` policy.</span></span>

- <span data-ttu-id="d9d17-377">Если тип является перечислением, массив типа помечается политикой `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-377">If the type is an enumeration, an array of the type is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="d9d17-378">Если тип реализует <xref:System.Collections.Generic.IEnumerable%601>, `T` помечается политикой `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-378">If the type implements <xref:System.Collections.Generic.IEnumerable%601>, `T` is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="d9d17-379">Если тип является типом <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.Generic.IList%601>, <xref:System.Collections.Generic.ICollection%601>, <xref:System.Collections.Generic.IReadOnlyCollection%601> или <xref:System.Collections.Generic.IReadOnlyList%601>, тогда `T[]` и <xref:System.Collections.Generic.List%601> помечаются политикой `Serialize`, однако ни один из членов типа интерфейса не помечаются политикой `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-379">If the type is <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.Generic.IList%601>, <xref:System.Collections.Generic.ICollection%601>, <xref:System.Collections.Generic.IReadOnlyCollection%601>, or <xref:System.Collections.Generic.IReadOnlyList%601>, then `T[]` and <xref:System.Collections.Generic.List%601> marked with the `Serialize` policy., but no members of the interface type are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="d9d17-380">Если тип является типом <xref:System.Collections.Generic.List%601>, то его члены не помечаются политикой `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-380">If the type is <xref:System.Collections.Generic.List%601>, no members of the type are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="d9d17-381">Если тип является типом <xref:System.Collections.Generic.IDictionary%602>, <xref:System.Collections.Generic.Dictionary%602> помечается политикой `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-381">If the type is <xref:System.Collections.Generic.IDictionary%602>, <xref:System.Collections.Generic.Dictionary%602> is marked with the `Serialize` policy.</span></span> <span data-ttu-id="d9d17-382">Но члены типа не помечаются политикой `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-382">but no members of the type are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="d9d17-383">Если тип является типом <xref:System.Collections.Generic.Dictionary%602>, то его члены не помечаются политикой `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-383">If the type is <xref:System.Collections.Generic.Dictionary%602>, no members of the type are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="d9d17-384">Если тип реализует <xref:System.Collections.Generic.IDictionary%602>, `TKey` и `TValue` помечаются политикой `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-384">If the type implements <xref:System.Collections.Generic.IDictionary%602>, `TKey` and `TValue` are marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="d9d17-385">Каждый конструктор, каждый метод доступа к свойству и каждое поле помечается политикой `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-385">Each constructor, each property accessor, and each field is marked with the `Serialize` policy.</span></span>

<span data-ttu-id="d9d17-386">Применение политики `Serialize` для метода включает в себя следующие изменения политики:</span><span class="sxs-lookup"><span data-stu-id="d9d17-386">Applying the `Serialize` policy to a method involves the following policy changes:</span></span>

- <span data-ttu-id="d9d17-387">Содержащий тип помечается политикой `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-387">The containing type is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="d9d17-388">Возвращаемый тип метода помечается политикой `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-388">The return type of the method is marked with the `Serialize` policy.</span></span>

<span data-ttu-id="d9d17-389">Применение политики `Serialize` для поля включает в себя следующие изменения политики:</span><span class="sxs-lookup"><span data-stu-id="d9d17-389">Applying the `Serialize` policy to a field involves the following policy changes:</span></span>

- <span data-ttu-id="d9d17-390">Содержащий тип помечается политикой `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-390">The containing type is marked with the `Serialize` policy.</span></span>

- <span data-ttu-id="d9d17-391">Тип поля помечается политикой `Serialize`.</span><span class="sxs-lookup"><span data-stu-id="d9d17-391">The type of the field is marked with the `Serialize` policy.</span></span>

#### <a name="the-effect-of-xmlserializer-datacontractserializer-and-datacontractjsonserializer-policies"></a><span data-ttu-id="d9d17-392">Воздействие политик XmlSerializer, DataContractSerializer и DataContractJsonSerializer</span><span class="sxs-lookup"><span data-stu-id="d9d17-392">The effect of XmlSerializer, DataContractSerializer, and DataContractJsonSerializer policies</span></span>

<span data-ttu-id="d9d17-393">В отличие от `Serialize` политики, которая предназначена для сериализаторов на основе отражения, <xref:System.Xml.Serialization.XmlSerializer> <xref:System.Runtime.Serialization.DataContractSerializer> политики, и <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> используются для включения набора сериализаторов, известных цепочке инструментов .NET Native.</span><span class="sxs-lookup"><span data-stu-id="d9d17-393">Unlike the `Serialize` policy, which is intended for reflection-based serializers, the <xref:System.Xml.Serialization.XmlSerializer>, <xref:System.Runtime.Serialization.DataContractSerializer>, and <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> policies are used to enable a set of serializers that are known to the .NET Native tool chain.</span></span> <span data-ttu-id="d9d17-394">Эти сериализаторы не реализуются с помощью отражения, но наборы типов, которые могут быть сериализованы во время выполнения определяются так же, как типы, которые могут отражаться.</span><span class="sxs-lookup"><span data-stu-id="d9d17-394">These serializers are not implemented by using reflection, but the set of types that can be serialized at run time is determined in a similar manner as types that are reflectable.</span></span>

<span data-ttu-id="d9d17-395">Применение одной из этих политик для типа позволяет сериализовать тип с помощью соответствующего сериализатора.</span><span class="sxs-lookup"><span data-stu-id="d9d17-395">Applying one of these policies to a type enables the type to be serialized with the matching serializer.</span></span> <span data-ttu-id="d9d17-396">Все типы, которые обработчик сериализации может статически определить, как нуждающиеся в сериализации, будут также сериализуемыми.</span><span class="sxs-lookup"><span data-stu-id="d9d17-396">Also, any types that the serialization engine can statically determine as needing serialization will also be serializable.</span></span>

<span data-ttu-id="d9d17-397">Эти политики не оказывают влияния на методы или поля.</span><span class="sxs-lookup"><span data-stu-id="d9d17-397">These policies have no effect on methods or fields.</span></span>

<span data-ttu-id="d9d17-398">Подробнее см. в подразделе "Различия в сериализаторах" раздела [Миграция приложения для Магазина Windows в .NET Native](migrating-your-windows-store-app-to-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="d9d17-398">For more information, see the "Differences in Serializers" section in [Migrating Your Windows Store App to .NET Native](migrating-your-windows-store-app-to-net-native.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d9d17-399">См. также</span><span class="sxs-lookup"><span data-stu-id="d9d17-399">See also</span></span>

- [<span data-ttu-id="d9d17-400">Элементы директив среды выполнения</span><span class="sxs-lookup"><span data-stu-id="d9d17-400">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="d9d17-401">Отражение и машинный код .NET</span><span class="sxs-lookup"><span data-stu-id="d9d17-401">Reflection and .NET Native</span></span>](reflection-and-net-native.md)
