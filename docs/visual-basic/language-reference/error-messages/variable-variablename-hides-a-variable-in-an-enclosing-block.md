---
description: "Дополнительные сведения о: BC30616: переменная ' <variablename> ' скрывает переменную во внешнем блоке"
title: Переменная <variablename> скрывает содержащуюся в блоке переменную
ms.date: 07/20/2015
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords:
- BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
ms.openlocfilehash: a0b2a4d024ff0409b5617354b5e671ca6dc0305b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99666125"
---
# <a name="bc30616-variable-variablename-hides-a-variable-in-an-enclosing-block"></a>BC30616: переменная " \<variablename> " скрывает переменную во внешнем блоке

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

- [Оператор Try...Catch...Finally](../statements/try-catch-finally-statement.md)
- [Объявление переменной](../../programming-guide/language-features/variables/variable-declaration.md)
