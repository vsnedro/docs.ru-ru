---
ms.openlocfilehash: 2d0798917b639bc90bf3f78f6fb9f19d0eaf2c71
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614818"
---
### <a name="incorrect-implementation-of-memberdescriptorequals"></a><span data-ttu-id="838d5-101">Неправильная реализация MemberDescriptor.Equals</span><span class="sxs-lookup"><span data-stu-id="838d5-101">Incorrect implementation of MemberDescriptor.Equals</span></span>

#### <a name="details"></a><span data-ttu-id="838d5-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="838d5-102">Details</span></span>

<span data-ttu-id="838d5-103">Исходная реализация метода <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> сравнивает два разных свойства строки из объектов для сравнения: имя категории и строка описания.</span><span class="sxs-lookup"><span data-stu-id="838d5-103">The original implementation of the <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> method compares two different string properties from the objects being compared: the category name and the description string.</span></span> <span data-ttu-id="838d5-104">Исправление заключается в сравнении <xref:System.ComponentModel.MemberDescriptor.Category> первого объекта с <xref:System.ComponentModel.MemberDescriptor.Category> второго объекта, и <xref:System.ComponentModel.MemberDescriptor.Description> первого объекта с <xref:System.ComponentModel.MemberDescriptor.Description> второго.</span><span class="sxs-lookup"><span data-stu-id="838d5-104">The fix is to compare the <xref:System.ComponentModel.MemberDescriptor.Category> of the first object to the <xref:System.ComponentModel.MemberDescriptor.Category> of the second one, and the <xref:System.ComponentModel.MemberDescriptor.Description> of the first to the <xref:System.ComponentModel.MemberDescriptor.Description> of the second.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="838d5-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="838d5-105">Suggestion</span></span>

<span data-ttu-id="838d5-106">Если приложение зависит от того, что <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> иногда возвращает значение `false`, когда дескрипторы эквивалентны, и вы используете .NET Framework 4.6.2 или более поздней версии, у вас есть несколько вариантов:</span><span class="sxs-lookup"><span data-stu-id="838d5-106">If your application depends on <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> sometimes returning `false` when descriptors are equivalent, and you are targeting the .NET Framework 4.6.2 or later, you have several options:</span></span>

- <span data-ttu-id="838d5-107">Изменения в коде для сравнения полей <xref:System.ComponentModel.MemberDescriptor.Category> и <xref:System.ComponentModel.MemberDescriptor.Description> вручную в дополнение к вызову метода <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="838d5-107">Make code changes to compare the <xref:System.ComponentModel.MemberDescriptor.Category> and <xref:System.ComponentModel.MemberDescriptor.Description> fields manually in addition to calling the <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> method.</span></span>
- <span data-ttu-id="838d5-108">Откажитесь от этого изменения, добавив следующее значение в файл app.config:</span><span class="sxs-lookup"><span data-stu-id="838d5-108">Opt out of this change by adding the following value to the app.config file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=true" />
</runtime>
```

<span data-ttu-id="838d5-109">Если ваше приложение предназначено для .NET Framework 4.6.1 или более ранней версии и выполняется на .NET Framework 4.6.2 или более поздней версии и вы хотите включить это изменение, вы можете указать для переключателя совместимости значение `false`, добавив следующее значение в файл app.config:</span><span class="sxs-lookup"><span data-stu-id="838d5-109">If your application targets .NET Framework 4.6.1 or earlier and is running on the .NET Framework 4.6.2 or later and you want this change enabled, you can set the compatibility switch to `false` by adding the following value to the app.config file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=false" />
</runtime>
```

| <span data-ttu-id="838d5-110">name</span><span class="sxs-lookup"><span data-stu-id="838d5-110">Name</span></span>    | <span data-ttu-id="838d5-111">Значение</span><span class="sxs-lookup"><span data-stu-id="838d5-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="838d5-112">Область</span><span class="sxs-lookup"><span data-stu-id="838d5-112">Scope</span></span>   | <span data-ttu-id="838d5-113">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="838d5-113">Edge</span></span>        |
| <span data-ttu-id="838d5-114">Version</span><span class="sxs-lookup"><span data-stu-id="838d5-114">Version</span></span> | <span data-ttu-id="838d5-115">4.6.2</span><span class="sxs-lookup"><span data-stu-id="838d5-115">4.6.2</span></span>       |
| <span data-ttu-id="838d5-116">Type</span><span class="sxs-lookup"><span data-stu-id="838d5-116">Type</span></span>    | <span data-ttu-id="838d5-117">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="838d5-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="838d5-118">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="838d5-118">Affected APIs</span></span>

- <xref:System.ComponentModel.MemberDescriptor.Equals(System.Object)?displayProperty=nameWithType>
