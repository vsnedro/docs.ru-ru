---
description: 'Дополнительные сведения о: BC30024: оператор недопустим в методе или многострочной лямбда-выражении'
title: Оператор недопустим в теле метода/многострочного лямбда-оператора
ms.date: 07/20/2015
f1_keywords:
- vbc30024
- bc30024
helpviewer_keywords:
- BC30024
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
ms.openlocfilehash: c70e5563ab8c161966cd9790ae1f192fa5d50b17
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99731179"
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
