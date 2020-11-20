---
ms.openlocfilehash: 56127309c5f5993ffc2e2faedd1f481e8131e094
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2020
ms.locfileid: "93400639"
---
### <a name="textformatflagsmodifystring-is-obsolete"></a><span data-ttu-id="7b2ee-101">Флаг TextFormatFlags.ModifyString является устаревшим</span><span class="sxs-lookup"><span data-stu-id="7b2ee-101">TextFormatFlags.ModifyString is obsolete</span></span>

<span data-ttu-id="7b2ee-102">Поле <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> устарело в качестве предупреждения и может быть удалено в будущей версии .NET.</span><span class="sxs-lookup"><span data-stu-id="7b2ee-102">The <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> field is obsolete, as a warning, and may be removed in a future .NET version.</span></span>

#### <a name="change-description"></a><span data-ttu-id="7b2ee-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="7b2ee-103">Change description</span></span>

<span data-ttu-id="7b2ee-104">В предыдущих версиях .NET поле перечисления <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> не помечено как устаревшее.</span><span class="sxs-lookup"><span data-stu-id="7b2ee-104">In previous .NET versions, the <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> enumeration field is not marked obsolete.</span></span> <span data-ttu-id="7b2ee-105">В .NET 5.0 и более поздних версиях оно помечено как устаревшее в качестве предупреждения.</span><span class="sxs-lookup"><span data-stu-id="7b2ee-105">In .NET 5.0 and later versions, it is marked obsolete as a warning.</span></span> <span data-ttu-id="7b2ee-106">Это поле может быть удалено в будущей версии .NET.</span><span class="sxs-lookup"><span data-stu-id="7b2ee-106">This field may be removed in a future .NET version.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="7b2ee-107">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="7b2ee-107">Reason for change</span></span>

<span data-ttu-id="7b2ee-108">В некоторых ситуациях передача строки в <xref:System.Windows.Forms.TextRenderer.MeasureText%2A?displayProperty=nameWithType> с <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> изменяет строку.</span><span class="sxs-lookup"><span data-stu-id="7b2ee-108">Passing a string to <xref:System.Windows.Forms.TextRenderer.MeasureText%2A?displayProperty=nameWithType> with <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> alters the string in some situations.</span></span> <span data-ttu-id="7b2ee-109">Это влечет за собой нарушение неизменности строки и может привести к неустранимому повреждению состояния среды выполнения .NET.</span><span class="sxs-lookup"><span data-stu-id="7b2ee-109">This behavior breaks the string immutability promise and may lead to a fatal .NET runtime state corruption.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="7b2ee-110">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="7b2ee-110">Version introduced</span></span>

<span data-ttu-id="7b2ee-111">.NET 5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="7b2ee-111">.NET 5.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="7b2ee-112">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="7b2ee-112">Recommended action</span></span>

<span data-ttu-id="7b2ee-113">Обновите весь код, который зависит от <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7b2ee-113">Update any code that relies on <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType>.</span></span>

#### <a name="category"></a><span data-ttu-id="7b2ee-114">Категория</span><span class="sxs-lookup"><span data-stu-id="7b2ee-114">Category</span></span>

<span data-ttu-id="7b2ee-115">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7b2ee-115">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="7b2ee-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="7b2ee-116">Affected APIs</span></span>

- <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=fullName>

<!--

#### Affected APIs

- `F:System.Windows.Forms.TextFormatFlags.ModifyString`

-->
