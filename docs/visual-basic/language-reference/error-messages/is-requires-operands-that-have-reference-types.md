---
title: При использовании оператора сравнения Is требуются операнды со ссылочным типом, однако данный операнд имеет тип значения <typename>
ms.date: 07/20/2015
f1_keywords:
- bc30020
- vbc30020
helpviewer_keywords:
- BC30020
ms.assetid: 228afebd-1203-4bd3-8d7a-c5c56f3cedc4
ms.openlocfilehash: daf9724fef81b4d7adb4f571ee950723aec09d8d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873914"
---
# <a name="is-requires-operands-that-have-reference-types-but-this-operand-has-the-value-type-typename"></a>При использовании оператора сравнения Is требуются операнды со ссылочным типом, однако данный операнд имеет тип значения \<typename>

`Is`Оператор сравнения определяет, ссылаются ли две объектные переменные на один и тот же экземпляр. Это сравнение не определено для типов значений.  
  
 **Идентификатор ошибки:** BC30020  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Используйте соответствующий оператор арифметического сравнения или `Like` оператор для сравнения двух типов значений.  
  
## <a name="see-also"></a>См. также

- [Оператор Is](../operators/is-operator.md)
- [Оператор Like](../operators/like-operator.md)
- [Операторы сравнения](../operators/comparison-operators.md)
