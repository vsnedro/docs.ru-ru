---
description: Предложение where. Справочник по C#
title: Предложение where. Справочник по C#
ms.date: 07/20/2015
f1_keywords:
- whereclause_CSharpKeyword
helpviewer_keywords:
- where keyword [C#]
- where clause [C#]
ms.assetid: 7f9bf952-7744-4f91-b676-cddb55d107c3
ms.openlocfilehash: 58a8dc226bb2720b6a8251f028712a80f74e893c
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89141690"
---
# <a name="where-clause-c-reference"></a>Предложение where (Справочник по C#)

Предложение `where` используется в выражении запроса для того, чтобы указать, какие элементы из источника данных будут возвращаться в выражении запроса. Оно применяет логическое условие (*предикат*) к каждому исходному элементу (на который ссылается переменная диапазона) и возвращает те из них, для которых указанное условие имеет значение true. Одно выражение запроса может содержать сразу несколько предложений `where`, а одно предложение — несколько частей выражения предиката.

## <a name="example"></a>Пример

В следующем примере предложение `where` отфильтровывает все номера, кроме тех, которые меньше пяти. Если удалить предложение `where`, возвращаются все номера из источника данных. Выражение `num < 5` является предикатом, который применяется к каждому элементу.

[!code-csharp[cscsrefQueryKeywords#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Where.cs#5)]

## <a name="example"></a>Пример

В одном предложении `where` можно указать необходимое число предикатов, используя операторы [&&](../operators/boolean-logical-operators.md#conditional-logical-and-operator-) и [&#124;&#124;](../operators/boolean-logical-operators.md#conditional-logical-or-operator-). В следующем примере запрос определяет два предиката, позволяющие отобрать только четные номера меньше пяти.

[!code-csharp[cscsrefQueryKeywords#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Where.cs#6)]  

## <a name="example"></a>Пример

Предложение `where` может содержать один или несколько методов, возвращающих логические значения. В следующем примере предложение `where` использует метод для того, чтобы определить, является ли текущее значение диапазона четным или нечетным.

[!code-csharp[cscsrefQueryKeywords#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Where.cs#7)]

## <a name="remarks"></a>Remarks

Предложение `where` представляет собой механизм фильтрации. Он может располагаться практически в любом месте выражения запроса, но не может быть первым или последним предложением. Предложение `where` может отображаться до или после предложения [group](group-clause.md) в зависимости от того, необходимо ли отфильтровать исходные элементы до или после их объединения в группы.

Если указанный предикат недопустим для элементов в источнике данных, это вызовет ошибку компиляции. Это одно из преимуществ надежной проверки типов, предоставляемой LINQ.

Во время компиляции ключевое слово `where` преобразуется в вызов метода стандартного оператора запроса <xref:System.Linq.Enumerable.Where%2A>.

## <a name="see-also"></a>См. также раздел

- [Ключевые слова запроса (LINQ)](query-keywords.md)
- [предложение from](from-clause.md)
- [предложение select](select-clause.md)
- [Фильтрация данных](../../programming-guide/concepts/linq/filtering-data.md)
- [LINQ в C#](../../linq/index.md)
- [LINQ](../../programming-guide/concepts/linq/index.md)
