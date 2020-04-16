---
title: '{}Последовательность побега - Расширение разметки'
ms.date: 03/30/2017
f1_keywords:
- '{}'
helpviewer_keywords:
- XAML [XAML Services], quotation mark (")
- '{} escape sequence [XAML Services]'
- XAML [XAML Services], {} escape sequence
- XAML [XAML Services], escape sequence
- quotation mark (") [XAML Services]
- escape sequence [XAML Services]
ms.assetid: 3ce3e2ad-a868-43f9-9c98-b29561cb146e
ms.openlocfilehash: f84243994557d76fa52d72b060a1ba35460e98b0
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432968"
---
# <a name="-escape-sequence--markup-extension"></a><span data-ttu-id="2b730-102">{}Побег последовательность / разметка расширение</span><span class="sxs-lookup"><span data-stu-id="2b730-102">{} Escape sequence / markup extension</span></span>

<span data-ttu-id="2b730-103">Обеспечивает последовательность побега XAML для значений атрибутов.</span><span class="sxs-lookup"><span data-stu-id="2b730-103">Provides the XAML escape sequence for attribute values.</span></span> <span data-ttu-id="2b730-104">Последовательность побега позволяет интерпретировать последующие значения в атрибуте как буквальные.</span><span class="sxs-lookup"><span data-stu-id="2b730-104">The escape sequence allows the subsequent values in the attribute to be interpreted as a literal.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="2b730-105">Использование атрибута XAML</span><span class="sxs-lookup"><span data-stu-id="2b730-105">XAML Attribute Usage</span></span>

```xaml
<object property="{} literalValue" .../>
```

## <a name="xaml-property-element-usage"></a><span data-ttu-id="2b730-106">Использование элемента свойства XAML</span><span class="sxs-lookup"><span data-stu-id="2b730-106">XAML Property Element Usage</span></span>

```xaml
<object>
  <object.property>
    {} literalValue
  </object.property>
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="2b730-107">Значения XAML</span><span class="sxs-lookup"><span data-stu-id="2b730-107">XAML Values</span></span>

|||
|-|-|
|<span data-ttu-id="2b730-108">*буквальнаястоимость*</span><span class="sxs-lookup"><span data-stu-id="2b730-108">*literalValue*</span></span>|<span data-ttu-id="2b730-109">Буквальная строка, которая следует за последовательностью побега.</span><span class="sxs-lookup"><span data-stu-id="2b730-109">The literal string that follows the escape sequence.</span></span> <span data-ttu-id="2b730-110">Обычно эта строка содержит открытую или закрытую скобку (я. или я).</span><span class="sxs-lookup"><span data-stu-id="2b730-110">Typically this string contains an open or close brace ({ or }).</span></span>|

## <a name="remarks"></a><span data-ttu-id="2b730-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="2b730-111">Remarks</span></span>

<span data-ttu-id="2b730-112">Последовательность побега ({}) используется так, что открытая скобка (я) может быть использована в качестве буквального символа в XAML.</span><span class="sxs-lookup"><span data-stu-id="2b730-112">The escape sequence ({}) is used so that an open brace ({) can be used as a literal character in XAML.</span></span>

<span data-ttu-id="2b730-113">Читатели XAML обычно используют открытую скобку (к) для обозначения точки входа в расширение разметки; однако, они сначала проверяют следующий символ, чтобы определить, является ли это закрытие скобки (я).</span><span class="sxs-lookup"><span data-stu-id="2b730-113">XAML readers typically use the open brace ({) to denote the entry point of a markup extension; however, they first check the next character to determine whether it is a closing brace (}).</span></span> <span data-ttu-id="2b730-114">Только тогда, когда{}две скобки ( ) являются смежными, они считаются побега последовательности.</span><span class="sxs-lookup"><span data-stu-id="2b730-114">Only when the two braces ({}) are adjacent, are they considered an escape sequence.</span></span>

<span data-ttu-id="2b730-115">При возникновении последовательности побега считыватель XAML должен обработать оставшуюся часть строки в виде строки.</span><span class="sxs-lookup"><span data-stu-id="2b730-115">If the escape sequence is encountered, the XAML reader should process the remainder of the string as a string.</span></span> <span data-ttu-id="2b730-116">Однако, если последовательность побега применяется к члену, который имеет преобразователь типа, строка может подвергнуться преобразованию типа, когда она интерпретируется автором XAML.</span><span class="sxs-lookup"><span data-stu-id="2b730-116">However, if the escape sequence is applied to a member that has a type converter, the string might undergo type conversion when it is interpreted by a XAML writer.</span></span>

<span data-ttu-id="2b730-117">Последовательность побега не является расширением разметки и не поддерживается классом.</span><span class="sxs-lookup"><span data-stu-id="2b730-117">The escape sequence is not a markup extension and is not backed by a class.</span></span> <span data-ttu-id="2b730-118">Тем не менее, это конвенция, что XAML читателей (в том числе пользовательских xAML читателей) должны уважать.</span><span class="sxs-lookup"><span data-stu-id="2b730-118">However, it is a convention that XAML readers (including custom XAML readers) should respect.</span></span>

<span data-ttu-id="2b730-119">Таким образом, знак котировки () не может использоваться в качестве последовательности побега.</span><span class="sxs-lookup"><span data-stu-id="2b730-119">A quotation mark (") cannot be used as an escape sequence in this manner.</span></span> <span data-ttu-id="2b730-120">Если вам нужно установить отметку котировки в качестве значения свойства для свойства, используйте синтаксис элемента свойства и поместите отметку котировки в качестве строки внутри элемента свойства, или используйте сущность символа XML.</span><span class="sxs-lookup"><span data-stu-id="2b730-120">If you need to set a quotation mark as a property value for a noncontent property, use property element syntax and place the quotation mark as a string inside the property element, or use an XML character entity.</span></span> <span data-ttu-id="2b730-121">Для свойства содержимого знак котировки может быть всем содержанием.</span><span class="sxs-lookup"><span data-stu-id="2b730-121">For a content property, the quotation mark can be the entire content.</span></span>

<span data-ttu-id="2b730-122">Последовательность побега (){}часто требуется при указании типа XML, который должен включать квалификатор пространства имен в месте, где может появиться расширение разметки XAML.</span><span class="sxs-lookup"><span data-stu-id="2b730-122">The escape sequence ({}) is frequently required when specifying an XML type that must include a namespace qualifier in a location where a XAML markup extension might appear.</span></span> <span data-ttu-id="2b730-123">Это место включает в себя начало значения атрибута XAML и расширение разметки сразу после равного знака.</span><span class="sxs-lookup"><span data-stu-id="2b730-123">This location includes the start of a XAML attribute value, and in a markup extension immediately after an equal sign (=).</span></span> <span data-ttu-id="2b730-124">В следующем примере показаны последовательности побега для пространства имен XML, которое появляется в начале значения атрибута XAML.</span><span class="sxs-lookup"><span data-stu-id="2b730-124">The following example shows escape sequences for an XML namespace that appears at the start of a XAML attribute value.</span></span>

[!code-xaml[XLINQExample#StackPanelResources](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]

## <a name="see-also"></a><span data-ttu-id="2b730-125">См. также</span><span class="sxs-lookup"><span data-stu-id="2b730-125">See also</span></span>

- [<span data-ttu-id="2b730-126">Преобразователи типов или расширения разметки для XAML</span><span class="sxs-lookup"><span data-stu-id="2b730-126">Type Converters and Markup Extensions for XAML</span></span>](type-converters-and-markup-extensions.md)
- [<span data-ttu-id="2b730-127">Сущности знаков XML и XAML</span><span class="sxs-lookup"><span data-stu-id="2b730-127">XML Character Entities and XAML</span></span>](xml-character-entities.md)
