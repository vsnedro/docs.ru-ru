---
ms.openlocfilehash: f1fc70075ef09a4f036c69788342c07ee51d72ce
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702487"
---
### <a name="winforms-methods-now-throw-argumentexception"></a><span data-ttu-id="950b1-101">Теперь методы WinForms вызывают исключение ArgumentException</span><span class="sxs-lookup"><span data-stu-id="950b1-101">WinForms methods now throw ArgumentException</span></span>

<span data-ttu-id="950b1-102">Некоторые методы Windows Forms теперь вызывают <xref:System.ArgumentException> для недопустимых аргументов в ситуациях, где ранее не делали этого.</span><span class="sxs-lookup"><span data-stu-id="950b1-102">Some Windows Forms methods now throw an <xref:System.ArgumentException> for invalid arguments, where previously they did not.</span></span>

#### <a name="change-description"></a><span data-ttu-id="950b1-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="950b1-103">Change description</span></span>

<span data-ttu-id="950b1-104">Ранее передача аргументов непредвиденного или неверного типа в определенные методы Windows Forms приводила к неопределенному состоянию.</span><span class="sxs-lookup"><span data-stu-id="950b1-104">Previously, passing arguments of an unexpected or incorrect type to certain Windows Forms methods would result in an indeterminate state.</span></span> <span data-ttu-id="950b1-105">Начиная с .NET 5.0 эти методы теперь вызывают <xref:System.ArgumentException> при передаче недопустимых аргументов.</span><span class="sxs-lookup"><span data-stu-id="950b1-105">Starting in .NET 5.0, these methods now throw an <xref:System.ArgumentException> when passed invalid arguments.</span></span>

<span data-ttu-id="950b1-106">Вызов <xref:System.ArgumentException> соответствует поведению среды выполнения .NET.</span><span class="sxs-lookup"><span data-stu-id="950b1-106">Throwing an <xref:System.ArgumentException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="950b1-107">Это также улучшает процесс отладки, четко указывая, какой аргумент недопустим.</span><span class="sxs-lookup"><span data-stu-id="950b1-107">It also improves the debugging experience by clearly communicating which argument is invalid.</span></span>

<span data-ttu-id="950b1-108">В следующей таблице перечислены затронутые методы и параметры:</span><span class="sxs-lookup"><span data-stu-id="950b1-108">The following table lists the affected methods and parameters:</span></span>

| <span data-ttu-id="950b1-109">Метод</span><span class="sxs-lookup"><span data-stu-id="950b1-109">Method</span></span> | <span data-ttu-id="950b1-110">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="950b1-110">Parameter name</span></span> | <span data-ttu-id="950b1-111">Условие</span><span class="sxs-lookup"><span data-stu-id="950b1-111">Condition</span></span> | <span data-ttu-id="950b1-112">Добавлено в версии</span><span class="sxs-lookup"><span data-stu-id="950b1-112">Version added</span></span> |
|-|-|-|
| <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName> | `item` | <span data-ttu-id="950b1-113">Аргумент не является аргументом типа <xref:System.Windows.Forms.TabPage>.</span><span class="sxs-lookup"><span data-stu-id="950b1-113">Argument is not of type <xref:System.Windows.Forms.TabPage>.</span></span> | <span data-ttu-id="950b1-114">5.0 Предварительная версия 1</span><span class="sxs-lookup"><span data-stu-id="950b1-114">5.0 Preview 1</span></span> |

#### <a name="version-introduced"></a><span data-ttu-id="950b1-115">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="950b1-115">Version introduced</span></span>

<span data-ttu-id="950b1-116">Предварительная версия 1 .NET 5.0</span><span class="sxs-lookup"><span data-stu-id="950b1-116">.NET 5.0 Preview 1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="950b1-117">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="950b1-117">Recommended action</span></span>

- <span data-ttu-id="950b1-118">Измените код, чтобы предотвратить передачу недопустимых аргументов.</span><span class="sxs-lookup"><span data-stu-id="950b1-118">Update the code to prevent passing invalid arguments.</span></span>
- <span data-ttu-id="950b1-119">При необходимости обработайте <xref:System.ArgumentException> при вызове метода.</span><span class="sxs-lookup"><span data-stu-id="950b1-119">If necessary, handle an <xref:System.ArgumentException> when calling the method.</span></span>

#### <a name="category"></a><span data-ttu-id="950b1-120">Категория</span><span class="sxs-lookup"><span data-stu-id="950b1-120">Category</span></span>

<span data-ttu-id="950b1-121">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="950b1-121">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="950b1-122">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="950b1-122">Affected APIs</span></span>

- <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName>

<!-- 

#### Affected APIs

- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`

-->
