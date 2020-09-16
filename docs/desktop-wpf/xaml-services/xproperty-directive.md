---
title: Директива x:Property
ms.date: 03/30/2017
ms.assetid: 618555a8-c893-455c-810f-ac54cd24ef10
ms.openlocfilehash: d4294b39ff262198f8082863d23eb6f4edbc7054
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90549305"
---
# <a name="xproperty-directive"></a><span data-ttu-id="b546e-102">Директива x:Property</span><span class="sxs-lookup"><span data-stu-id="b546e-102">x:Property Directive</span></span>

<span data-ttu-id="b546e-103">Объявляет свойство XAML в разметке.</span><span class="sxs-lookup"><span data-stu-id="b546e-103">Declares a XAML property in markup.</span></span>

## <a name="xaml-object-element-usage"></a><span data-ttu-id="b546e-104">Использование элемента объекта XAML</span><span class="sxs-lookup"><span data-stu-id="b546e-104">XAML Object Element Usage</span></span>

```xaml
<object x:Class="className">
  <x:Members>
    <x:Property Name="propertyName" Type="propertyType"/>
    additionalProperties
  </x:Members>
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="b546e-105">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="b546e-105">XAML Values</span></span>

|||
|-|-|
|`className`|<span data-ttu-id="b546e-106">Имя класса резервирования или разделяемого класса для рабочей среды XAML.</span><span class="sxs-lookup"><span data-stu-id="b546e-106">Name of the backing class or partial class for the XAML production.</span></span>|
|`propertyName`|<span data-ttu-id="b546e-107">Имя члена определяемого свойства.</span><span class="sxs-lookup"><span data-stu-id="b546e-107">Member name of the property being defined.</span></span>|
|`propertyType`|<span data-ttu-id="b546e-108">Имя типа (или другая строковая форма, специфичная для платформы), указывающее тип этого свойства.</span><span class="sxs-lookup"><span data-stu-id="b546e-108">Type name (or other string form, framework-specific) that specifies the type of this property.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b546e-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="b546e-109">Remarks</span></span>

<span data-ttu-id="b546e-110">В реализации служб XAML .NET.</span><span class="sxs-lookup"><span data-stu-id="b546e-110">In .NET XAML Services implementation, .</span></span> <span data-ttu-id="b546e-111">`x:Property` не имеет прямое резервирование типа, но поддерживается классом <xref:System.Windows.Markup.PropertyDefinition>.</span><span class="sxs-lookup"><span data-stu-id="b546e-111">`x:Property` does not have a direct type backing, but is supported by the <xref:System.Windows.Markup.PropertyDefinition> class.</span></span> <span data-ttu-id="b546e-112">В потоке узлов XAML элемент `x:Property` представляется как член с именем `Property` из пространства имен XAML языка XAML.</span><span class="sxs-lookup"><span data-stu-id="b546e-112">In a XAML node stream, an `x:Property` element is represented as a member named `Property`, from the XAML language XAML namespace.</span></span> <span data-ttu-id="b546e-113">Член `Property` хранит атрибуты, объявленные в разметке.</span><span class="sxs-lookup"><span data-stu-id="b546e-113">The member `Property` hold attributes as declared by markup.</span></span>

<span data-ttu-id="b546e-114">Значение `Name` и `Type` не назначаются на уровне служб XAML .NET.</span><span class="sxs-lookup"><span data-stu-id="b546e-114">The meaning of `Name` and `Type` are not assigned at .NET XAML Services level.</span></span> <span data-ttu-id="b546e-115">Они хранятся в исходном потоке узлов XAML как строковые значения для последующей интерпретации в соответствии с правилами, которые могут быть наложены конкретными платформами.</span><span class="sxs-lookup"><span data-stu-id="b546e-115">They are stored in the initial XAML node stream as string values, to be interpreted later under the rules that might be imposed by specific frameworks.</span></span> <span data-ttu-id="b546e-116">Эти значения могут выравниваться по значениям имени XAML и типа XAML или могут быть допустимы только в системе с резервированием типов, в зависимости от реализации.</span><span class="sxs-lookup"><span data-stu-id="b546e-116">The meaning might align to a XAML name and XAML type meaning, or might only be valid in a backing type system, depending on the implementation.</span></span>

<span data-ttu-id="b546e-117">Для поддержки практического использования `x:Members` как средства указания определений членов в разметке эти члены должны быть связаны с классом, который может быть изменен.</span><span class="sxs-lookup"><span data-stu-id="b546e-117">To support a practical usage of `x:Members` as a means to specify member definitions in markup, the members must be associated with a class that can be modified.</span></span> <span data-ttu-id="b546e-118">Предполагаемая модель состоит в том, что `x:Members` существует в качестве члена типа, указывающего `x:Class`.</span><span class="sxs-lookup"><span data-stu-id="b546e-118">The intended model is that `x:Members` exists as a member of a type that specifies an `x:Class`.</span></span> <span data-ttu-id="b546e-119">Однако механизм связывания типов и членов или для создания определений динамических элементов не поддерживается на уровне служб XAML .NET.</span><span class="sxs-lookup"><span data-stu-id="b546e-119">However, the mechanism for associating types and members or for producing dynamic member definitions is not supported at .NET XAML Services level.</span></span> <span data-ttu-id="b546e-120">Это отводится отдельным платформам, имеющим модели приложений, поддерживающие определения членов из XAML.</span><span class="sxs-lookup"><span data-stu-id="b546e-120">This is left to individual frameworks that have application models that support member definitions from XAML.</span></span> <span data-ttu-id="b546e-121">Как правило, для поддержки этой функции требуются действия MSBUILD при построении, которые компилируют разметку XAML и либо интегрируют его с выделенным кодом, либо создают чистые сборки из XAML.</span><span class="sxs-lookup"><span data-stu-id="b546e-121">Typically, MSBUILD build actions that markup-compile the XAML and either integrate it with code-behind or produce pure from-XAML assemblies are needed to support that feature.</span></span>

## <a name="xproperty-for-windows-workflow-foundation"></a><span data-ttu-id="b546e-122">x:Property для Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="b546e-122">x:Property for Windows Workflow Foundation</span></span>

<span data-ttu-id="b546e-123">Для Windows Workflow Foundation `x:Property` определяет члены пользовательского действия, составленного полностью в XAML, или заданные XAML динамические члены для конструктора действий с выделенным кодом.</span><span class="sxs-lookup"><span data-stu-id="b546e-123">For Windows Workflow Foundation, `x:Property` defines the members of a custom activity composed entirely in XAML, or XAML –defined dynamic members for an activity designer with code-behind.</span></span> <span data-ttu-id="b546e-124">`x:Class` также должен быть указан в корневом элементе рабочей среды XAML.</span><span class="sxs-lookup"><span data-stu-id="b546e-124">`x:Class` must also be specified on the root element of the XAML production.</span></span> <span data-ttu-id="b546e-125">Это не является обязательным требованием на уровне служб XAML .NET, но становится обязательным при загрузке рабочего пространства XAML с помощью действий сборки MSBUILD, которые поддерживают пользовательские действия и Windows Workflow Foundation XAML в целом.</span><span class="sxs-lookup"><span data-stu-id="b546e-125">This is not a requirement at .NET XAML Services level, but becomes a requirement when the XAML production is loaded by the MSBUILD build actions that support custom activities and Windows Workflow Foundation XAML in general.</span></span> <span data-ttu-id="b546e-126">Windows Workflow Foundation не использует чистое имя типа XAML в качестве предполагаемого значения `x:Property` `Type` атрибута, а вместо этого использует соглашение, не описанное здесь.</span><span class="sxs-lookup"><span data-stu-id="b546e-126">Windows Workflow Foundation does not use the pure XAML type name as its intended value for the `x:Property` `Type` attribute, and instead uses a convention that is not documented here.</span></span> <span data-ttu-id="b546e-127">Дополнительные сведения см. в разделе [Создание DynamicActivity](/previous-versions/dotnet/netframework-4.0/dd807392(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="b546e-127">For more information, see [DynamicActivity Creation](/previous-versions/dotnet/netframework-4.0/dd807392(v=vs.100)).</span></span>
