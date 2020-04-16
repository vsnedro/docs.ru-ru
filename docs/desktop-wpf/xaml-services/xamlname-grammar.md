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
# <a name="xamlname-grammar"></a>Грамматика XamlName

XamlName Grammar — это специфическая грамматика, которая определяется в спецификации языка XAML «MS-XAML», которая воспроизводится здесь для удобства.

## <a name="from-the-xaml-specification"></a>Из спецификации XAML

Спецификация «MS-XAML» определяет грамматику XamlName для определения набора юридических символических идентификаторов, используемых для типов и свойств.

Значения строки типа XamlName должны соответствовать следующей грамматике:

```xaml
XamlName ::= NameStartChar ( NameChar )*
NameStartChar ::= LetterCharacter | '_'
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl
DecimalDigit ::= UnicodeNd
CombiningCharacter ::= UnicodeMn | UnicodeMc
```

Что предполагает следующие значения общей категории, определенные в базе данных символов Unicode

| Категория Unicode   | Описание                   |
|--------------------|-------------------------------|
| Лы                 | Буква: прописные буквы             |
| Ll                 | Буква: строчные буквы             |
| Lt                 | Буква: заглавный регистр             |
| Lm                 | Буква: модификатор              |
| Lo                 | Буква: другие                 |
| Mn                 | Марк, не-интервалы             |
| Mc                 | Метка: комбинированная       |
| Nd                 | Номер, десятичная               |
| Nl                 | Число: буква                |

XAML определяет вторую грамматику, DottedXamlName, которая используется для свойств и событий квалифицированных ссылок, а также для прикрепленных членов. Для получения дополнительной <xref:System.Windows.DependencyProperty> информации см. [XAML Overview (WPF)](../fundamentals/xaml.md)

Значения строки, которые имеют тип DottedXamlName, должны соответствовать следующей грамматике:

```xaml
DottedXamlName ::= XamlName '.' XamlName
```

## <a name="remarks"></a>Примечания

Для полной спецификации [ \[см.\]](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))
