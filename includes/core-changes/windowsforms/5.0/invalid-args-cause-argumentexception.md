---
ms.openlocfilehash: 5212c5d9513a8ef5f51693857d0ddb60db4e49b9
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158410"
---
### <a name="winforms-methods-now-throw-argumentexception"></a><span data-ttu-id="b2680-101">Теперь методы WinForms вызывают исключение ArgumentException</span><span class="sxs-lookup"><span data-stu-id="b2680-101">WinForms methods now throw ArgumentException</span></span>

<span data-ttu-id="b2680-102">Некоторые методы Windows Forms теперь вызывают <xref:System.ArgumentException> для недопустимых аргументов в ситуациях, где ранее не делали этого.</span><span class="sxs-lookup"><span data-stu-id="b2680-102">Some Windows Forms methods now throw an <xref:System.ArgumentException> for invalid arguments, where previously they did not.</span></span>

#### <a name="change-description"></a><span data-ttu-id="b2680-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="b2680-103">Change description</span></span>

<span data-ttu-id="b2680-104">Ранее передача аргументов непредвиденного или неверного типа в определенные методы Windows Forms приводила к неопределенному состоянию.</span><span class="sxs-lookup"><span data-stu-id="b2680-104">Previously, passing arguments of an unexpected or incorrect type to certain Windows Forms methods would result in an indeterminate state.</span></span> <span data-ttu-id="b2680-105">Начиная с .NET 5.0 эти методы теперь вызывают <xref:System.ArgumentException> при передаче недопустимых аргументов.</span><span class="sxs-lookup"><span data-stu-id="b2680-105">Starting in .NET 5.0, these methods now throw an <xref:System.ArgumentException> when passed invalid arguments.</span></span>

<span data-ttu-id="b2680-106">Вызов <xref:System.ArgumentException> соответствует поведению среды выполнения .NET.</span><span class="sxs-lookup"><span data-stu-id="b2680-106">Throwing an <xref:System.ArgumentException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="b2680-107">Это также улучшает процесс отладки, четко указывая, какой аргумент недопустим.</span><span class="sxs-lookup"><span data-stu-id="b2680-107">It also improves the debugging experience by clearly communicating which argument is invalid.</span></span>

<span data-ttu-id="b2680-108">В следующей таблице перечислены затронутые методы и параметры:</span><span class="sxs-lookup"><span data-stu-id="b2680-108">The following table lists the affected methods and parameters:</span></span>

| <span data-ttu-id="b2680-109">Метод</span><span class="sxs-lookup"><span data-stu-id="b2680-109">Method</span></span> | <span data-ttu-id="b2680-110">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="b2680-110">Parameter name</span></span> | <span data-ttu-id="b2680-111">Условие</span><span class="sxs-lookup"><span data-stu-id="b2680-111">Condition</span></span> | <span data-ttu-id="b2680-112">Добавлено в версии</span><span class="sxs-lookup"><span data-stu-id="b2680-112">Version added</span></span> |
|-|-|-|
| <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName> | `item` | <span data-ttu-id="b2680-113">Аргумент не является аргументом типа <xref:System.Windows.Forms.TabPage>.</span><span class="sxs-lookup"><span data-stu-id="b2680-113">Argument is not of type <xref:System.Windows.Forms.TabPage>.</span></span> | <span data-ttu-id="b2680-114">5.0 Предварительная версия 1</span><span class="sxs-lookup"><span data-stu-id="b2680-114">5.0 Preview 1</span></span> |

#### <a name="version-introduced"></a><span data-ttu-id="b2680-115">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="b2680-115">Version introduced</span></span>

<span data-ttu-id="b2680-116">Предварительная версия 1 .NET 5.0</span><span class="sxs-lookup"><span data-stu-id="b2680-116">.NET 5.0 Preview 1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b2680-117">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="b2680-117">Recommended action</span></span>

- <span data-ttu-id="b2680-118">Измените код, чтобы предотвратить передачу недопустимых аргументов.</span><span class="sxs-lookup"><span data-stu-id="b2680-118">Update the code to prevent passing invalid arguments.</span></span>
- <span data-ttu-id="b2680-119">При необходимости обработайте <xref:System.ArgumentException> при вызове метода.</span><span class="sxs-lookup"><span data-stu-id="b2680-119">If necessary, handle an <xref:System.ArgumentException> when calling the method.</span></span>

#### <a name="category"></a><span data-ttu-id="b2680-120">Категория</span><span class="sxs-lookup"><span data-stu-id="b2680-120">Category</span></span>

<span data-ttu-id="b2680-121">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b2680-121">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b2680-122">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="b2680-122">Affected APIs</span></span>

- <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName>

<!-- 

### Affected APIs

- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`

-->
