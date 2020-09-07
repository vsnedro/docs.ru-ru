---
ms.openlocfilehash: 086dac69d085d070511fcfd5820bd2644ee4598e
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497021"
---
### <a name="marshalsizeof-and-marshalptrtostructure-overloads-break-dynamic-code"></a><span data-ttu-id="4b43b-101">Перегрузки Marshal.SizeOf и Marshal.PtrToStructure нарушают работу динамического кода</span><span class="sxs-lookup"><span data-stu-id="4b43b-101">Marshal.SizeOf and Marshal.PtrToStructure overloads break dynamic code</span></span>

#### <a name="details"></a><span data-ttu-id="4b43b-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="4b43b-102">Details</span></span>

<span data-ttu-id="4b43b-103">Начиная с .NET Framework 4.5.1 динамическая привязка к методам <xref:System.Runtime.InteropServices.Marshal.SizeOf%60%601>, <xref:System.Runtime.InteropServices.Marshal.SizeOf%60%601(%60%600)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure(System.IntPtr,System.Object)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure(System.IntPtr,System.Type)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%60%601(System.IntPtr)> или <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%60%601(System.IntPtr,%60%600)> (с помощью Windows PowerShell, IronPython или ключевого слова dynamic в C#) может привести к исключению <code>MethodInvocationExceptions</code>, так как были добавлены новые перегрузки этих методов, которые могут быть неоднозначными для обработчиков скриптов.</span><span class="sxs-lookup"><span data-stu-id="4b43b-103">Beginning in the .NET Framework 4.5.1, dynamically binding to the methods <xref:System.Runtime.InteropServices.Marshal.SizeOf%60%601>, <xref:System.Runtime.InteropServices.Marshal.SizeOf%60%601(%60%600)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure(System.IntPtr,System.Object)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure(System.IntPtr,System.Type)>, <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%60%601(System.IntPtr)>, or <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%60%601(System.IntPtr,%60%600)>, (via Windows PowerShell, IronPython, or the C# dynamic keyword, for example) can result in <code>MethodInvocationExceptions</code> because new overloads of these methods have been added that may be ambiguous to the scripting engines.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="4b43b-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="4b43b-104">Suggestion</span></span>

<span data-ttu-id="4b43b-105">Обновите скрипты для четкого указания используемой перегрузки.</span><span class="sxs-lookup"><span data-stu-id="4b43b-105">Update scripts to clearly indicate which overload should be used.</span></span> <span data-ttu-id="4b43b-106">Обычно нужно явным образом привести параметры типа метода как <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="4b43b-106">This can typically done by explicitly casting the methods' type parameters as <xref:System.Type>.</span></span> <span data-ttu-id="4b43b-107">Дополнительные сведения и возможные решения этой проблемы см. по [этой ссылке](https://support.microsoft.com/kb/2909958/).</span><span class="sxs-lookup"><span data-stu-id="4b43b-107">See [this link](https://support.microsoft.com/kb/2909958/) for more detail and examples of how to workaround the issue.</span></span>

| <span data-ttu-id="4b43b-108">name</span><span class="sxs-lookup"><span data-stu-id="4b43b-108">Name</span></span>    | <span data-ttu-id="4b43b-109">Значение</span><span class="sxs-lookup"><span data-stu-id="4b43b-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="4b43b-110">Область</span><span class="sxs-lookup"><span data-stu-id="4b43b-110">Scope</span></span>   |<span data-ttu-id="4b43b-111">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="4b43b-111">Minor</span></span>|
|<span data-ttu-id="4b43b-112">Version</span><span class="sxs-lookup"><span data-stu-id="4b43b-112">Version</span></span>|<span data-ttu-id="4b43b-113">4.5.1</span><span class="sxs-lookup"><span data-stu-id="4b43b-113">4.5.1</span></span>|
|<span data-ttu-id="4b43b-114">Type</span><span class="sxs-lookup"><span data-stu-id="4b43b-114">Type</span></span>|<span data-ttu-id="4b43b-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="4b43b-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="4b43b-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="4b43b-116">Affected APIs</span></span>

<span data-ttu-id="4b43b-117">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="4b43b-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
