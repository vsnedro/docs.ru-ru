---
title: Символ "." или "!", стоящий в начале оператора, может использоваться только внутри оператора "With"
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: 4ff273d5930fe58a5bccf0f4f4c10e971d777d01
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162509"
---
# <a name="bc30157-leading--or--can-only-appear-inside-a-with-statement"></a>BC30157: ведущие "." или "!" могут использоваться только в операторе "with"

Точка (.) или восклицательный знак (!), не находящиеся внутри `With` блока, происходит без выражения слева. Для доступа к членам ( `.` ) и доступа к членам словаря ( `!` ) требуется выражение, указывающее элемент, содержащий элемент. Он должен располагаться непосредственно слева от метода доступа или являться целевым объектом блока, `With` содержащего доступ к члену.

 **Идентификатор ошибки:** BC30157

## <a name="to-correct-this-error"></a>Исправление ошибки

1. Убедитесь, что `With` блок имеет правильный формат.

2. Если `With` блок отсутствует, добавьте выражение слева от метода доступа, результатом которого является определенный элемент, содержащий элемент.

## <a name="see-also"></a>См. также

- [Специальные символы в коде](../../programming-guide/program-structure/special-characters-in-code.md)
- [Оператор With…End With](../statements/with-end-with-statement.md)
