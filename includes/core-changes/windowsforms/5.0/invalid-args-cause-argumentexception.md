---
ms.openlocfilehash: 9f6703c77e17ac9376aee944b891f4635dc7632e
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309165"
---
### <a name="winforms-methods-now-throw-argumentexception"></a><span data-ttu-id="81d4d-101">Теперь методы WinForms вызывают исключение ArgumentException</span><span class="sxs-lookup"><span data-stu-id="81d4d-101">WinForms methods now throw ArgumentException</span></span>

<span data-ttu-id="81d4d-102">Некоторые методы Windows Forms теперь вызывают <xref:System.ArgumentException> для недопустимых аргументов в ситуациях, где ранее не делали этого.</span><span class="sxs-lookup"><span data-stu-id="81d4d-102">Some Windows Forms methods now throw an <xref:System.ArgumentException> for invalid arguments, where previously they did not.</span></span>

#### <a name="change-description"></a><span data-ttu-id="81d4d-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="81d4d-103">Change description</span></span>

<span data-ttu-id="81d4d-104">Ранее передача аргументов непредвиденного или неверного типа в определенные методы Windows Forms приводила к неопределенному состоянию.</span><span class="sxs-lookup"><span data-stu-id="81d4d-104">Previously, passing arguments of an unexpected or incorrect type to certain Windows Forms methods would result in an indeterminate state.</span></span> <span data-ttu-id="81d4d-105">Начиная с .NET 5.0 эти методы теперь вызывают <xref:System.ArgumentException> при передаче недопустимых аргументов.</span><span class="sxs-lookup"><span data-stu-id="81d4d-105">Starting in .NET 5.0, these methods now throw an <xref:System.ArgumentException> when passed invalid arguments.</span></span>

<span data-ttu-id="81d4d-106">Вызов <xref:System.ArgumentException> соответствует поведению среды выполнения .NET.</span><span class="sxs-lookup"><span data-stu-id="81d4d-106">Throwing an <xref:System.ArgumentException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="81d4d-107">Это также улучшает процесс отладки, четко указывая, какой аргумент недопустим.</span><span class="sxs-lookup"><span data-stu-id="81d4d-107">It also improves the debugging experience by clearly communicating which argument is invalid.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="81d4d-108">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="81d4d-108">Version introduced</span></span>

<span data-ttu-id="81d4d-109">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="81d4d-109">.NET 5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="81d4d-110">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="81d4d-110">Recommended action</span></span>

- <span data-ttu-id="81d4d-111">Измените код, чтобы предотвратить передачу недопустимых аргументов.</span><span class="sxs-lookup"><span data-stu-id="81d4d-111">Update the code to prevent passing invalid arguments.</span></span>
- <span data-ttu-id="81d4d-112">При необходимости обработайте <xref:System.ArgumentException> при вызове метода.</span><span class="sxs-lookup"><span data-stu-id="81d4d-112">If necessary, handle an <xref:System.ArgumentException> when calling the method.</span></span>

#### <a name="category"></a><span data-ttu-id="81d4d-113">Категория</span><span class="sxs-lookup"><span data-stu-id="81d4d-113">Category</span></span>

<span data-ttu-id="81d4d-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="81d4d-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="81d4d-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="81d4d-115">Affected APIs</span></span>

<span data-ttu-id="81d4d-116">В следующей таблице перечислены затронутые методы и параметры:</span><span class="sxs-lookup"><span data-stu-id="81d4d-116">The following table lists the affected methods and parameters:</span></span>

| <span data-ttu-id="81d4d-117">Метод</span><span class="sxs-lookup"><span data-stu-id="81d4d-117">Method</span></span> | <span data-ttu-id="81d4d-118">Имя параметра</span><span class="sxs-lookup"><span data-stu-id="81d4d-118">Parameter name</span></span> | <span data-ttu-id="81d4d-119">Условие</span><span class="sxs-lookup"><span data-stu-id="81d4d-119">Condition</span></span> | <span data-ttu-id="81d4d-120">Добавлено в версии</span><span class="sxs-lookup"><span data-stu-id="81d4d-120">Version added</span></span> |
|-|-|-|-|
| <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName> | `item` | <span data-ttu-id="81d4d-121">Аргумент не является аргументом типа <xref:System.Windows.Forms.TabPage>.</span><span class="sxs-lookup"><span data-stu-id="81d4d-121">Argument is not of type <xref:System.Windows.Forms.TabPage>.</span></span> | <span data-ttu-id="81d4d-122">Предварительная версия 1</span><span class="sxs-lookup"><span data-stu-id="81d4d-122">Preview 1</span></span> |
| <xref:System.Windows.Forms.DataFormats.GetFormat(System.String)?displayProperty=fullName> | `format` | <span data-ttu-id="81d4d-123">Аргумент содержит `null`, <xref:System.String.Empty?displayProperty=nameWithType> или пробел.</span><span class="sxs-lookup"><span data-stu-id="81d4d-123">Argument is `null`, <xref:System.String.Empty?displayProperty=nameWithType>, or white space.</span></span> | <span data-ttu-id="81d4d-124">Предварительная версия 5</span><span class="sxs-lookup"><span data-stu-id="81d4d-124">Preview 5</span></span> |
| <xref:System.Windows.Forms.InputLanguageChangedEventArgs.%23ctor(System.Globalization.CultureInfo,System.Byte)> | `culture` | <span data-ttu-id="81d4d-125">Не удается извлечь `InputLanguage` для заданных языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="81d4d-125">Unable to retrieve an `InputLanguage` for the specified culture.</span></span> | <span data-ttu-id="81d4d-126">Предварительная версия 7</span><span class="sxs-lookup"><span data-stu-id="81d4d-126">Preview 7</span></span> |

<!-- 

#### Affected APIs

- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`
- `M:System.Windows.Forms.DataFormats.GetFormat(System.String)`
- `M:System.Windows.Forms.InputLanguageChangedEventArgs.%23ctor(System.Globalization.CultureInfo,System.Byte)`

-->
