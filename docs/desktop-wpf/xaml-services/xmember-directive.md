---
title: Директива x:Member
ms.date: 03/30/2017
ms.assetid: 4d8394ef-644c-4331-b6c5-be855d392980
ms.openlocfilehash: 1c5b26b405e574290af54b29b22fb5e19e4b6b95
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548251"
---
# <a name="xmember-directive"></a><span data-ttu-id="a7f88-102">Директива x:Member</span><span class="sxs-lookup"><span data-stu-id="a7f88-102">x:Member Directive</span></span>
<span data-ttu-id="a7f88-103">Объявляет член XAML в разметке.</span><span class="sxs-lookup"><span data-stu-id="a7f88-103">Declares a XAML member in markup.</span></span>

## <a name="xaml-object-element-usage"></a><span data-ttu-id="a7f88-104">Использование элемента объекта XAML</span><span class="sxs-lookup"><span data-stu-id="a7f88-104">XAML Object Element Usage</span></span>

```xaml
<object x:Class="className">
  <x:Members>
    <x:Member Name="propertyName"/>
    additionalMembers
  </x:Members>
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="a7f88-105">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="a7f88-105">XAML Values</span></span>

|||
|-|-|
|`className`|<span data-ttu-id="a7f88-106">Имя класса резервирования или разделяемого класса для рабочей среды XAML.</span><span class="sxs-lookup"><span data-stu-id="a7f88-106">Name of the backing class or partial class for the XAML production.</span></span>|
|`memberName`|<span data-ttu-id="a7f88-107">Имя члена определяемого свойства.</span><span class="sxs-lookup"><span data-stu-id="a7f88-107">Member name of the property being defined.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a7f88-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="a7f88-108">Remarks</span></span>

<span data-ttu-id="a7f88-109">В реализации служб XAML .NET.</span><span class="sxs-lookup"><span data-stu-id="a7f88-109">In .NET XAML Services implementation, .</span></span> <span data-ttu-id="a7f88-110">`x:Member` не имеет прямое резервирование типа, но поддерживается классом <xref:System.Windows.Markup.MemberDefinition>.</span><span class="sxs-lookup"><span data-stu-id="a7f88-110">`x:Member` does not have a direct type backing, but is supported by the <xref:System.Windows.Markup.MemberDefinition> class.</span></span> <span data-ttu-id="a7f88-111">В потоке узлов XAML элемент `x:Member` представляется как член с именем `Member` из пространства имен XAML языка XAML.</span><span class="sxs-lookup"><span data-stu-id="a7f88-111">In a XAML node stream, an `x:Member` element is represented as a member named `Member`, from the XAML language XAML namespace.</span></span> <span data-ttu-id="a7f88-112">Член `Member` хранит атрибуты, объявленные в разметке.</span><span class="sxs-lookup"><span data-stu-id="a7f88-112">The member `Member` holds attributes as declared by markup.</span></span>

<span data-ttu-id="a7f88-113">Значение `Name` и `Type` не назначаются на уровне служб XAML .NET.</span><span class="sxs-lookup"><span data-stu-id="a7f88-113">The meaning of `Name` and `Type` are not assigned at .NET XAML Services level.</span></span> <span data-ttu-id="a7f88-114">Они хранятся в исходном потоке узлов XAML как строковые значения для последующей интерпретации в соответствии с правилами, которые могут быть наложены конкретными платформами.</span><span class="sxs-lookup"><span data-stu-id="a7f88-114">They are stored in the initial XAML node stream as string values, to be interpreted later under the rules that might be imposed by specific frameworks.</span></span> <span data-ttu-id="a7f88-115">Эти значения могут выравниваться по значениям имени XAML и типа XAML или могут быть допустимы только в системе с резервированием типов, в зависимости от реализации.</span><span class="sxs-lookup"><span data-stu-id="a7f88-115">The meaning might align to a XAML name and XAML type meaning, or might only be valid in a backing type system, depending on the implementation.</span></span>

<span data-ttu-id="a7f88-116">Для поддержки практического использования `x:Members` как средства указания определений членов в разметке эти члены должны быть связаны с классом, который может быть изменен.</span><span class="sxs-lookup"><span data-stu-id="a7f88-116">To support a practical usage of `x:Members` as a means to specify member definitions in markup, the members must be associated with a class that can be modified.</span></span> <span data-ttu-id="a7f88-117">Предполагаемая модель состоит в том, что `x:Members` существует в качестве члена типа, указывающего `x:Class`.</span><span class="sxs-lookup"><span data-stu-id="a7f88-117">The intended model is that `x:Members` exists as a member of a type that specifies an `x:Class`.</span></span> <span data-ttu-id="a7f88-118">Однако механизм связывания типов и членов или для создания определений динамических элементов не поддерживается на уровне служб XAML .NET.</span><span class="sxs-lookup"><span data-stu-id="a7f88-118">However, the mechanism for associating types and members or for producing dynamic member definitions is not supported at .NET XAML Services level.</span></span> <span data-ttu-id="a7f88-119">Это отводится отдельным платформам, имеющим модели приложений, поддерживающие определения членов из XAML.</span><span class="sxs-lookup"><span data-stu-id="a7f88-119">This is left to individual frameworks that have application models that support member definitions from XAML.</span></span> <span data-ttu-id="a7f88-120">Как правило, для поддержки этой функции требуются действия MSBUILD при построении, которые компилируют разметку XAML и либо интегрируют его с выделенным кодом, либо создают чистые сборки из XAML.</span><span class="sxs-lookup"><span data-stu-id="a7f88-120">Typically, MSBUILD build actions that markup-compile the XAML and either integrate it with code-behind or produce pure from-XAML assemblies are needed to support that feature.</span></span>

## <a name="xproperty-for-windows-workflow-foundation"></a><span data-ttu-id="a7f88-121">x:Property для Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="a7f88-121">x:Property for Windows Workflow Foundation</span></span>

<span data-ttu-id="a7f88-122">Для Windows Workflow Foundation `x:Property` определяет члены пользовательского действия, составленного полностью в XAML, или заданные XAML динамические члены для конструктора действий с выделенным кодом.</span><span class="sxs-lookup"><span data-stu-id="a7f88-122">For Windows Workflow Foundation, `x:Property` defines the members of a custom activity composed entirely in XAML, or XAML –defined dynamic members for an activity designer with code-behind.</span></span> <span data-ttu-id="a7f88-123">`x:Class` также должен быть указан в корневом элементе рабочей среды XAML.</span><span class="sxs-lookup"><span data-stu-id="a7f88-123">`x:Class` must also be specified on the root element of the XAML production.</span></span> <span data-ttu-id="a7f88-124">Это не является обязательным требованием на уровне служб XAML .NET, но становится обязательным при загрузке рабочего пространства XAML с помощью действий сборки MSBUILD, которые поддерживают пользовательские действия и Windows Workflow Foundation XAML в целом.</span><span class="sxs-lookup"><span data-stu-id="a7f88-124">This is not a requirement at .NET XAML Services level, but becomes a requirement when the XAML production is loaded by the MSBUILD build actions that support custom activities and Windows Workflow Foundation XAML in general.</span></span> <span data-ttu-id="a7f88-125">Windows Workflow Foundation не использует чистое имя типа XAML в качестве предполагаемого значения `x:Property` `Type` атрибута, а вместо этого использует соглашение, не описанное здесь.</span><span class="sxs-lookup"><span data-stu-id="a7f88-125">Windows Workflow Foundation does not use the pure XAML type name as its intended value for the `x:Property` `Type` attribute, and instead uses a convention that is not documented here.</span></span> <span data-ttu-id="a7f88-126">Дополнительные сведения см. в разделе [Создание DynamicActivity](/previous-versions/dotnet/netframework-4.0/dd807392(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="a7f88-126">For more information, see [DynamicActivity Creation](/previous-versions/dotnet/netframework-4.0/dd807392(v=vs.100)).</span></span>
