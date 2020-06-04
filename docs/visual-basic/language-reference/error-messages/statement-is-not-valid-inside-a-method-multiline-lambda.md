---
title: Оператор недопустим в теле метода/многострочного лямбда-оператора
ms.date: 07/20/2015
f1_keywords:
- vbc30024
- bc30024
helpviewer_keywords:
- BC30024
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
ms.openlocfilehash: f3c43d640259d5e1af545e2610088aab5d70453d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396250"
---
# <a name="statement-is-not-valid-inside-a-methodmultiline-lambda"></a>Оператор недопустим в теле метода/многострочного лямбда-оператора
Оператор недопустим в `Sub` `Function` процедуре свойства,, свойства `Get` или `Set` . Некоторые инструкции можно разместить на уровне модуля или класса. Другие, такие как `Option Strict` , должны находиться на уровне пространства имен и предшествовать всем остальным объявлениям.  
  
 **Идентификатор ошибки:** BC30024  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Удалите инструкцию из процедуры.  
  
## <a name="see-also"></a>См. также раздел

- [Оператор Sub](../statements/sub-statement.md)
- [Оператор Function](../statements/function-statement.md)
- [Оператор Get](../statements/get-statement.md)
- [Инструкция SET](../statements/set-statement.md)
