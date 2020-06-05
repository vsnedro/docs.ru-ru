---
title: Неверный номер записи
ms.date: 07/20/2015
f1_keywords:
- vbrID63
ms.assetid: 1fcc33f8-822a-4de9-a6e3-228ddb5824a6
ms.openlocfilehash: 44a11d95d33041de9d637684f41cb003dcc36b97
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84367546"
---
# <a name="bad-record-number"></a>Неверный номер записи
Номер записи в операторе `a FileGet`, `FilePut`, `FileGetObject`или `FilePutObject` меньше или равен нулю.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Проверьте вычисления, используемые при формировании номера записи. Проверьте правильность написания переменных, содержащих номер записи или используемых при вычислении номеров записей. Неправильно написанное имя переменной неявно объявляется и приравнивается к нулю, если вы не использовали `Option Explicit On` в модуле.  
  
## <a name="see-also"></a>См. также раздел

- [Оператор Option Explicit](../language-reference/statements/option-explicit-statement.md)
