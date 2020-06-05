---
title: Переменная <variablename> скрывает содержащуюся в блоке переменную
ms.date: 07/20/2015
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords:
- BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
ms.openlocfilehash: 474a920c9cfdfba7a8157320d9c88b8677958425
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406525"
---
# <a name="variable-variablename-hides-a-variable-in-an-enclosing-block"></a>Переменная \<variablename> скрывает содержащуюся в блоке переменную
Переменная, заключенная в блок, имеет то же имя, что и другая локальная переменная.  
  
 **Идентификатор ошибки:** BC30616  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Переименуйте переменную во вложенном блоке так, чтобы она не совпадала с другими локальными переменными. Пример:  
  
    ```vb  
    Dim a, b, x As Integer  
    If a = b Then  
       Dim y As Integer = 20 ' Uniquely named block variable.  
    End If  
    ```  
  
- Распространенной причиной этой ошибки является использование `Catch e As Exception` внутри обработчика событий. Если это так, назовите `Catch` переменную блока, `ex` а не `e` .  
  
- Другой распространенный источник этой ошибки — попытка доступа к локальной переменной, объявленной в `Try` блоке, в отдельном `Catch` блоке. Чтобы исправить это, объявите переменную вне `Try...Catch...Finally` структуры.  
  
## <a name="see-also"></a>См. также раздел

- [Оператор Try…Catch…Finally](../statements/try-catch-finally-statement.md)
- [Объявление переменной](../../programming-guide/language-features/variables/variable-declaration.md)
