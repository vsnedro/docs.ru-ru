---
title: В делегируемом классе <classname> отсутствует метод Invoke, поэтому выражение этого типа не может быть вызвано посредством метода
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: 27be97ba2930791bcb9012c824bc418a0089b037
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409716"
---
# <a name="delegate-class-classname-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a>В делегируемом классе \<classname> отсутствует метод Invoke, поэтому выражение этого типа не может быть вызвано посредством метода
Вызов `Invoke` через делегат завершился неудачей, поскольку `Invoke` не реализован в классе делегата.  
  
 **Идентификатор ошибки:** BC30220  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Убедитесь, что экземпляр класса делегата был создан с помощью `Dim` оператора и что процедура была назначена экземпляру делегата с помощью `AddressOf` оператора.  
  
2. Выберите код, реализующий класс делегата, и убедитесь, что он реализует `Invoke` процедуру.  
  
## <a name="see-also"></a>См. также раздел

- [Делегаты](../../programming-guide/language-features/delegates/index.md)
- [Оператор Delegate](../statements/delegate-statement.md)
- [Оператор AddressOf](../operators/addressof-operator.md)
- [Оператор Dim](../statements/dim-statement.md)
