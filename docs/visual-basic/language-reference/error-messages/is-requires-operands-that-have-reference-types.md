---
description: 'Дополнительные сведения о: BC30020: "is" требует операндов, имеющих ссылочные типы, но этот операнд имеет тип значения " <typename> "'
title: При использовании оператора сравнения Is требуются операнды со ссылочным типом, однако данный операнд имеет тип значения <typename>
ms.date: 07/20/2015
f1_keywords:
- bc30020
- vbc30020
helpviewer_keywords:
- BC30020
ms.assetid: 228afebd-1203-4bd3-8d7a-c5c56f3cedc4
ms.openlocfilehash: f05040c6174f4b1edd006d1302f0d94b871d1cd9
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100427548"
---
# <a name="bc30020-is-requires-operands-that-have-reference-types-but-this-operand-has-the-value-type-typename"></a>BC30020: для "is" требуются операнды, имеющие ссылочные типы, но этот операнд имеет тип значения " \<typename> "

`Is`Оператор сравнения определяет, ссылаются ли две объектные переменные на один и тот же экземпляр. Это сравнение не определено для типов значений.

 **Идентификатор ошибки:** BC30020

## <a name="to-correct-this-error"></a>Исправление ошибки

- Используйте соответствующий оператор арифметического сравнения или `Like` оператор для сравнения двух типов значений.

## <a name="see-also"></a>См. также раздел

- [Оператор Is](../operators/is-operator.md)
- [Оператор Like](../operators/like-operator.md)
- [Операторы сравнения](../operators/comparison-operators.md)
