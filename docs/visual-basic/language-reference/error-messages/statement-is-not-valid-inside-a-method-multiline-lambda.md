---
title: Оператор недопустим в теле метода/многострочного лямбда-оператора
ms.date: 07/20/2015
f1_keywords:
- vbc30024
- bc30024
helpviewer_keywords:
- BC30024
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
ms.openlocfilehash: cef992c3eaa2b82bbf5e8993f9fccd64ae388c95
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159681"
---
# <a name="bc30024-statement-is-not-valid-inside-a-methodmultiline-lambda"></a>BC30024: недопустимая инструкция в методе или многострочной лямбда-выражении

Оператор недопустим в `Sub` `Function` процедуре свойства,, свойства `Get` или `Set` . Некоторые инструкции можно разместить на уровне модуля или класса. Другие, такие как `Option Strict` , должны находиться на уровне пространства имен и предшествовать всем остальным объявлениям.

 **Идентификатор ошибки:** BC30024

## <a name="to-correct-this-error"></a>Исправление ошибки

- Удалите инструкцию из процедуры.

## <a name="see-also"></a>См. также

- [Оператор Sub](../statements/sub-statement.md)
- [Оператор Function](../statements/function-statement.md)
- [Оператор Get](../statements/get-statement.md)
- [Инструкция SET](../statements/set-statement.md)
