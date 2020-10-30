---
description: Справочник по C#. Модификатор override
title: Справочник по C#. Модификатор override
ms.date: 10/22/2020
f1_keywords:
- override
- override_CSharpKeyword
helpviewer_keywords:
- override keyword [C#]
ms.assetid: dd1907a8-acf8-46d3-80b9-c2ca4febada8
ms.openlocfilehash: 618200183348e68a4600adb9592a635f61f6a875
ms.sourcegitcommit: 98d20cb038669dca4a195eb39af37d22ea9d008e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2020
ms.locfileid: "92434878"
---
# <a name="override-c-reference"></a>override (справочник по C#)

Модификатор `override` требуется для расширения или изменения абстрактной или виртуальной реализации унаследованного метода, свойства, индексатора или события.

В следующем примере класс `Square` должен предоставить переопределенную реализацию `GetArea`, так как `GetArea` является унаследованным от абстрактного класса `Shape`:

[!code-csharp[csrefKeywordsModifiers#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#1)]

Метод `override` предоставляет новую реализацию метода, унаследованного от базового класса. Метод, переопределенный объявлением `override`, называется переопределенным базовым методом. Метод `override` должен иметь ту же сигнатуру, что и переопределенный базовый метод. Начиная с версии C# 9.0, методы `override` поддерживают ковариантные типы возвращаемых значений. В частности, тип возвращаемого значения метода `override` может быть производным от типа возвращаемого значения соответствующего базового метода. В C# 8.0 и более ранних версий типы возвращаемых значений метода `override` и переопределенного базового метода должны быть одинаковыми.

Невиртуальный или статический метод нельзя переопределить. Переопределенный базовый метод должен иметь тип `virtual`, `abstract` или `override`.

Объявление `override` не может изменить доступность метода `virtual`. Методы `override` и `virtual` должны иметь одинаковый [модификатор уровня доступа](access-modifiers.md).

Модификаторы `new`, `static` и `virtual` нельзя использовать для изменения метода `override`.

Переопределяющее объявление свойства должно задавать такие же модификатор уровня доступа, тип и имя, которые имеются у унаследованного свойства. Начиная с версии C# 9.0, переопределяющие свойства только для чтения поддерживают ковариантные типы возвращаемых значений. Переопределенное свойство должно быть `virtual`, `abstract` или `override`.

Дополнительные сведения об использовании ключевого слова `override` см. в разделах [Управление версиями с помощью ключевых слов Override и New](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) и [Использование ключевых слов Override и New](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md). Дополнительные сведения о наследовании см. в разделе [Наследование](../../programming-guide/classes-and-structs/inheritance.md).

## <a name="example"></a>Пример

В этом примере определяется базовый класс с именем `Employee` и производный класс с именем `SalesEmployee`. Класс `SalesEmployee` включает дополнительное поле `salesbonus`, для использования которого переопределяется метод `CalculatePay`.

[!code-csharp[csrefKeywordsModifiers#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#9)]

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе [Методы переопределения](~/_csharplang/spec/classes.md#override-methods) статьи [Спецификация языка C#](~/_csharplang/spec/introduction.md).

Дополнительные сведения о ковариантных типах возвращаемых значений см. в [примечании к функциям](~/_csharplang/proposals/csharp-9.0/covariant-returns.md).

## <a name="see-also"></a>См. также

- [справочник по C#](../index.md)
- [Наследование](../../programming-guide/classes-and-structs/inheritance.md)
- [Ключевые слова C#](index.md)
- [Модификаторы](index.md)
- [abstract](abstract.md)
- [virtual](virtual.md)
- [new (модификатор)](new-modifier.md)
- [Полиморфизм](../../programming-guide/classes-and-structs/polymorphism.md)
