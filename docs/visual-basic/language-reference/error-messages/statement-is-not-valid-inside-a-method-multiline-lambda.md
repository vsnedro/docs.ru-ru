---
title: Оператор недопустим в теле метода/многострочного лямбда-оператора
ms.date: 07/20/2015
f1_keywords:
- vbc30024
- bc30024
helpviewer_keywords:
- BC30024
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
ms.openlocfilehash: d5d756f1772b9519613e163119b88a3057d36cf3
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870623"
---
# <a name="statement-is-not-valid-inside-a-methodmultiline-lambda"></a>Оператор недопустим в теле метода/многострочного лямбда-оператора

Оператор недопустим в `Sub` `Function` процедуре свойства,, свойства `Get` или `Set` . Некоторые инструкции можно разместить на уровне модуля или класса. Другие, такие как `Option Strict` , должны находиться на уровне пространства имен и предшествовать всем остальным объявлениям.  
  
 **Идентификатор ошибки:** BC30024  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Удалите инструкцию из процедуры.  
  
## <a name="see-also"></a>См. также

- [Оператор Sub](../statements/sub-statement.md)
- [Оператор Function](../statements/function-statement.md)
- [Оператор Get](../statements/get-statement.md)
- [Инструкция SET](../statements/set-statement.md)
