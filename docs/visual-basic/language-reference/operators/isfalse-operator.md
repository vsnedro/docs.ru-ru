---
title: Оператор IsFalse
ms.date: 07/20/2015
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
ms.openlocfilehash: 7c5ad5fa0b72370eeb19fbaced88807570467552
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84370678"
---
# <a name="isfalse-operator-visual-basic"></a>Оператор IsFalse (Visual Basic)
Определяет, является ли выражение `False` .  
  
 `IsFalse`В коде нельзя вызывать явным образом, но компилятор Visual Basic может использовать его для создания кода из `AndAlso` предложений. Если вы определяете класс или структуру, а затем используете переменную этого типа в `AndAlso` предложении, необходимо определить `IsFalse` для этого класса или структуры.  
  
 Компилятор рассматривает `IsFalse` операторы и `IsTrue` как *парную пару*. Это означает, что при определении одного из них необходимо также определить другой.  
  
> [!NOTE]
> `IsFalse`Оператор можно *перегрузить*, что означает, что класс или структура может переопределить свое поведение, если его операнд имеет тип этого класса или структуры. Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Пример  
 В следующем примере кода определяется структура структуры, включающей определения для `IsFalse` `IsTrue` операторов и.  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>См. также раздел

- [Оператор IsTrue](istrue-operator.md)
- [Практическое руководство. Определение оператора](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Оператор AndAlso](andalso-operator.md)
