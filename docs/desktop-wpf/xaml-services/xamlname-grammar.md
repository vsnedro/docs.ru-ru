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
ms.openlocfilehash: ceb027938b6d4313babbe02949e0b6dd5ee85589
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556698"
---
# <a name="xamlname-grammar"></a>Грамматика XamlName

Грамматика Имяxaml — это специальная грамматика, определенная в спецификации языка XAML [MS-XAML], которая создается здесь для удобства.

## <a name="from-the-xaml-specification"></a>Из спецификации XAML

Спецификация [MS-XAML] определяет грамматику Имяxaml для определения набора допустимых символьных идентификаторов, используемых для типов и свойств.

Строковые значения типа Имяxaml должны соответствовать следующей грамматике:

```xaml
XamlName ::= NameStartChar ( NameChar )*
NameStartChar ::= LetterCharacter | '_'
NameChar ::= NameStartChar | DecimalDigit | CombiningCharacter
LetterCharacter ::= UnicodeLu | UnicodeLl | UnicodeLo | UnicodeLt | UnicodeNl
DecimalDigit ::= UnicodeNd
CombiningCharacter ::= UnicodeMn | UnicodeMc
```

Предполагается, что следующие общие значения категории определены в базе данных символов Юникода.

| Категория Юникода   | Описание                   |
|--------------------|-------------------------------|
| Лы                 | Буква: прописные буквы             |
| Ll                 | Буква: строчные буквы             |
| Lt                 | Буква: заглавный регистр             |
| Lm                 | Буква: модификатор              |
| Lo                 | Буква: другие                 |
| Mn                 | Пометить, без промежутков             |
| Mc                 | Метка: комбинированная       |
| Nd                 | Число, десятичное               |
| Nl                 | Число: буква                |

XAML определяет вторую грамматику, Доттедксамлнаме, которая используется для уточненных ссылок на свойства и события, а также для присоединенных членов. Дополнительные сведения см. в <xref:System.Windows.DependencyProperty> разделе [Общие сведения о языке XAML (WPF)](../fundamentals/xaml.md).

Строковые значения типа Доттедксамлнаме должны соответствовать следующей грамматике:

```xaml
DottedXamlName ::= XamlName '.' XamlName
```

## <a name="remarks"></a>Примечания

Полную спецификацию см. в разделе [ \[ MS- \] XAML](/previous-versions/msp-n-p/ff650760(v=pandp.10)).
