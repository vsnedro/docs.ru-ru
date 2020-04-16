---
title: Грамматика XamlName
ms.date: 03/30/2017
helpviewer_keywords:
- DottedXamlName grammar [XAML Services]
- grammar [XAML Services], DottedXamlName
- grammar [XAML Services], XamlName
- names in XAML [XAML Services]
- XamlName grammar [XAML Services]
ms.assetid: 11e4cada-41d2-494d-9531-0d3df4dfcbe3
ms.openlocfilehash: 2fc74990b15caaa9b58e6eea5b0212ea22505674
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "81433052"
---
# <a name="xamlname-grammar"></a><span data-ttu-id="9ff05-102">Грамматика XamlName</span><span class="sxs-lookup"><span data-stu-id="9ff05-102">XamlName Grammar</span></span>

<span data-ttu-id="9ff05-103">XamlName Grammar — это специфическая грамматика, которая определяется в спецификации языка XAML «MS-XAML», которая воспроизводится здесь для удобства.</span><span class="sxs-lookup"><span data-stu-id="9ff05-103">XamlName Grammar is a specific grammar that is defined in the XAML language specification [MS-XAML], which is reproduced here for convenience.</span></span>

## <a name="from-the-xaml-specification"></a><span data-ttu-id="9ff05-104">Из спецификации XAML</span><span class="sxs-lookup"><span data-stu-id="9ff05-104">From the XAML Specification</span></span>

<span data-ttu-id="9ff05-105">Спецификация «MS-XAML» определяет грамматику XamlName для определения набора юридических символических идентификаторов, используемых для типов и свойств.</span><span class="sxs-lookup"><span data-stu-id="9ff05-105">The [MS-XAML] specification defines the grammar XamlName to identify the set of legal symbolic identifiers used for types and properties.</span></span>

<span data-ttu-id="9ff05-106">Значения строки типа XamlName должны соответствовать следующей грамматике:</span><span class="sxs-lookup"><span data-stu-id="9ff05-106">String values that are of type XamlName must conform to the following grammar:</span></span>

```xaml
XamlName ::= NameStartChar ( NameChar )*
NameStartChar ::= LetterCharacter | '_'
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl
DecimalDigit ::= UnicodeNd
CombiningCharacter ::= UnicodeMn | UnicodeMc
```

<span data-ttu-id="9ff05-107">Что предполагает следующие значения общей категории, определенные в базе данных символов Unicode</span><span class="sxs-lookup"><span data-stu-id="9ff05-107">Which assumes the following general category values as defined in the Unicode Character Database</span></span>

| <span data-ttu-id="9ff05-108">Категория Unicode</span><span class="sxs-lookup"><span data-stu-id="9ff05-108">Unicode category</span></span>   | <span data-ttu-id="9ff05-109">Описание</span><span class="sxs-lookup"><span data-stu-id="9ff05-109">Description</span></span>                   |
|--------------------|-------------------------------|
| <span data-ttu-id="9ff05-110">Лы</span><span class="sxs-lookup"><span data-stu-id="9ff05-110">Lu</span></span>                 | <span data-ttu-id="9ff05-111">Буква: прописные буквы</span><span class="sxs-lookup"><span data-stu-id="9ff05-111">Letter, Uppercase</span></span>             |
| <span data-ttu-id="9ff05-112">Ll</span><span class="sxs-lookup"><span data-stu-id="9ff05-112">Ll</span></span>                 | <span data-ttu-id="9ff05-113">Буква: строчные буквы</span><span class="sxs-lookup"><span data-stu-id="9ff05-113">Letter, Lowercase</span></span>             |
| <span data-ttu-id="9ff05-114">Lt</span><span class="sxs-lookup"><span data-stu-id="9ff05-114">Lt</span></span>                 | <span data-ttu-id="9ff05-115">Буква: заглавный регистр</span><span class="sxs-lookup"><span data-stu-id="9ff05-115">Letter, Titlecase</span></span>             |
| <span data-ttu-id="9ff05-116">Lm</span><span class="sxs-lookup"><span data-stu-id="9ff05-116">Lm</span></span>                 | <span data-ttu-id="9ff05-117">Буква: модификатор</span><span class="sxs-lookup"><span data-stu-id="9ff05-117">Letter, Modifier</span></span>              |
| <span data-ttu-id="9ff05-118">Lo</span><span class="sxs-lookup"><span data-stu-id="9ff05-118">Lo</span></span>                 | <span data-ttu-id="9ff05-119">Буква: другие</span><span class="sxs-lookup"><span data-stu-id="9ff05-119">Letter, Other</span></span>                 |
| <span data-ttu-id="9ff05-120">Mn</span><span class="sxs-lookup"><span data-stu-id="9ff05-120">Mn</span></span>                 | <span data-ttu-id="9ff05-121">Марк, не-интервалы</span><span class="sxs-lookup"><span data-stu-id="9ff05-121">Mark, Non-Spacing</span></span>             |
| <span data-ttu-id="9ff05-122">Mc</span><span class="sxs-lookup"><span data-stu-id="9ff05-122">Mc</span></span>                 | <span data-ttu-id="9ff05-123">Метка: комбинированная</span><span class="sxs-lookup"><span data-stu-id="9ff05-123">Mark, Spacing Combining</span></span>       |
| <span data-ttu-id="9ff05-124">Nd</span><span class="sxs-lookup"><span data-stu-id="9ff05-124">Nd</span></span>                 | <span data-ttu-id="9ff05-125">Номер, десятичная</span><span class="sxs-lookup"><span data-stu-id="9ff05-125">Number, Decimal</span></span>               |
| <span data-ttu-id="9ff05-126">Nl</span><span class="sxs-lookup"><span data-stu-id="9ff05-126">Nl</span></span>                 | <span data-ttu-id="9ff05-127">Число: буква</span><span class="sxs-lookup"><span data-stu-id="9ff05-127">Number, Letter</span></span>                |

<span data-ttu-id="9ff05-128">XAML определяет вторую грамматику, DottedXamlName, которая используется для свойств и событий квалифицированных ссылок, а также для прикрепленных членов.</span><span class="sxs-lookup"><span data-stu-id="9ff05-128">XAML defines a second grammar, DottedXamlName, that is used for property and event qualified references, and also for attached members.</span></span> <span data-ttu-id="9ff05-129">Для получения дополнительной <xref:System.Windows.DependencyProperty> информации см. [XAML Overview (WPF)](../fundamentals/xaml.md)</span><span class="sxs-lookup"><span data-stu-id="9ff05-129">For more information, see <xref:System.Windows.DependencyProperty> and [XAML Overview (WPF)](../fundamentals/xaml.md).</span></span>

<span data-ttu-id="9ff05-130">Значения строки, которые имеют тип DottedXamlName, должны соответствовать следующей грамматике:</span><span class="sxs-lookup"><span data-stu-id="9ff05-130">String values that are of type DottedXamlName must conform to the following grammar:</span></span>

```xaml
DottedXamlName ::= XamlName '.' XamlName
```

## <a name="remarks"></a><span data-ttu-id="9ff05-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="9ff05-131">Remarks</span></span>

<span data-ttu-id="9ff05-132">Для полной спецификации [ \[см.\]](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))</span><span class="sxs-lookup"><span data-stu-id="9ff05-132">For the complete specification, see [\[MS-XAML\]](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>
