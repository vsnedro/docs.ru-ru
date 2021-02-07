---
description: Дополнительные сведения о предложении JOIN (Visual Basic)
title: Предложение Join
ms.date: 07/20/2015
f1_keywords:
- vb.QueryJoinIn
- vb.QueryJoin
- vb.QueryJoinOn
helpviewer_keywords:
- queries [Visual Basic], Join
- Join statement [Visual Basic]
- Join clause [Visual Basic]
ms.assetid: 6dd37936-b27c-4e00-98ad-154b23f4de64
ms.openlocfilehash: 69d808e68a32b3f8799dabbbc8abc53acae42b57
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700446"
---
# <a name="join-clause-visual-basic"></a>Предложение Join (Visual Basic)

Объединяет две коллекции в одну. Операция Join основана на совпадающих ключах и использует `Equals` оператор.

## <a name="syntax"></a>Синтаксис

```vb
Join element In collection _
  [ joinClause _ ]
  [ groupJoinClause ... _ ]
On key1 Equals key2 [ And key3 Equals key4 [... ]
```

## <a name="parts"></a>Компоненты

`element` Обязательный. Управляющая переменная для объединяемой коллекции.

`collection`  
Обязательный элемент. Коллекция для объединения с коллекцией, указанной в левой части `Join` оператора. `Join`Предложение может быть вложенным в другое `Join` предложение или в `Group Join` предложении.

`joinClause`  
Необязательный элемент. Одно или несколько дополнительных `Join` предложений для дальнейшего уточнения запроса.

`groupJoinClause`  
Необязательный элемент. Одно или несколько дополнительных `Group Join` предложений для дальнейшего уточнения запроса.

`key1` `Equals` `key2`  
Обязательный элемент. Определяет ключи для соединяемых коллекций. `Equals`Для сравнения ключей из объединяемых коллекций необходимо использовать оператор. Условия объединения можно комбинировать с помощью `And` оператора для обнаружения нескольких ключей. `key1` должен быть из коллекции в левой части `Join` оператора. `key2` должен находиться в коллекции с правой стороны `Join` оператора.

Ключи, используемые в условии объединения, могут быть выражениями, включающими более одного элемента из коллекции. Однако каждое ключевое выражение может содержать только элементы из соответствующей коллекции.

## <a name="remarks"></a>Remarks

`Join`Предложение объединяет две коллекции на основе совпадающих значений ключей из объединяемых коллекций. Результирующая коллекция может содержать любое сочетание значений из коллекции, указанной в левой части `Join` оператора, и коллекции, указанной в `Join` предложении. Запрос возвратит только результаты, для которых выполняется условие, заданное `Equals` оператором. Это эквивалентно `INNER JOIN` в SQL.

`Join`Для объединения двух или более коллекций в одну коллекцию можно использовать несколько предложений в запросе.

Можно выполнить неявное соединение для объединения коллекций без `Join` предложения. Для этого включите `In` в предложение несколько предложений `From` и укажите `Where` предложение, определяющее ключи, которые необходимо использовать для объединения.

Предложение можно использовать `Group Join` для объединения коллекций в одну иерархическую коллекцию. Это похоже на `LEFT OUTER JOIN` в SQL.

## <a name="example"></a>Пример

В следующем примере кода выполняется неявное соединение для объединения списка клиентов с их заказами.

[!code-vb[VbSimpleQuerySamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#13)]

## <a name="example"></a>Пример

В следующем примере кода две коллекции объединяются с помощью `Join` предложения.

[!code-vb[VbSimpleQuerySamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples2.vb#12)]

В этом примере выводятся выходные данные, аналогичные приведенным ниже.

`winlogon (968), Windows Logon`

`explorer (2424), File Explorer`

`cmd (5136), Command Window`

## <a name="example"></a>Пример

В следующем примере кода две коллекции соединяются с помощью `Join` предложения с двумя ключевыми столбцами.

[!code-vb[VbSimpleQuerySamples#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples3.vb#17)]

В примере будет выведен результат, аналогичный приведенному ниже:

`winlogon (968), Windows Logon, Priority = 13`

`cmd (700), Command Window, Priority = 8`

`explorer (2424), File Explorer, Priority = 8`

## <a name="see-also"></a>См. также

- [Introduction to LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Запросы](index.md)
- [Предложение SELECT](select-clause.md)
- [Предложение From](from-clause.md)
- [Предложение Group Join](group-join-clause.md)
- [Предложение WHERE](where-clause.md)
