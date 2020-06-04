---
title: <type1>Тип <typename> должен реализовать <methodname> для интерфейса <interfacename>
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: 90d2b6d70390bfb732af4a5868c935de61d18f94
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408504"
---
# <a name="type1typename-must-implement-methodname-for-interface-interfacename"></a>\<type1>Тип \<typename> должен реализовать \<methodname> для интерфейса \<interfacename>
Класс или структура требует реализации интерфейса, но не реализует процедуру, определенную интерфейсом. Каждый член интерфейса должен быть реализован.  
  
 **Идентификатор ошибки:** BC30149  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Объявите процедуру с тем же именем и сигнатурой, как определено в интерфейсе. Обязательно включите по крайней мере `End Function` оператор или `End Sub` .  
  
2. Добавьте `Implements` предложение в конец `Function` `Sub` оператора или. Пример:  
  
    ```vb  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a>См. также раздел

- [Оператор Implements](../statements/implements-statement.md)
- [Интерфейсы](../../programming-guide/language-features/interfaces/index.md)
