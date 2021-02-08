---
description: 'Дополнительные сведения о: BC36633: переменная диапазона <variable> скрывает переменную во внешнем блоке, ранее определенную переменную диапазона или неявно объявленную переменную в выражении запроса'
title: Переменная диапазона <variable> скрывает переменную во включающем блоке, ранее определенную переменную диапазона или неявно объявленную переменную в выражении запроса
ms.date: 07/20/2015
f1_keywords:
- bc36633
- vbc36633
helpviewer_keywords:
- BC36633
ms.assetid: 5d5470e4-3de5-49c2-8831-1087625f4a77
ms.openlocfilehash: f8e5c109274af9c00963e8a9f18384a299d17a4a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792080"
---
# <a name="bc36633-range-variable-variable-hides-a-variable-in-an-enclosing-block-a-previously-defined-range-variable-or-an-implicitly-declared-variable-in-a-query-expression"></a>BC36633: переменная диапазона \<variable> скрывает переменную во внешнем блоке, ранее определенную переменную диапазона или неявно объявленную переменную в выражении запроса

Имя переменной диапазона, указанное в `Select` `From` `Aggregate` предложении,, или, `Let` дублирует имя переменной диапазона, уже указанное ранее в запросе, или имя переменной, неявно объявленной в запросе, например имя поля или имя агрегатной функции.

 **Идентификатор ошибки:** BC36633

## <a name="to-correct-this-error"></a>Исправление ошибки

- Убедитесь, что все переменные диапазона в определенной области запроса имеют уникальные имена. Запрос можно заключить в круглые скобки, чтобы убедиться, что вложенные запросы имеют уникальную область.

## <a name="see-also"></a>См. также

- [Introduction to LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Предложение From](../queries/from-clause.md)
- [Предложение Let](../queries/let-clause.md)
- [Aggregate Clause](../queries/aggregate-clause.md)
- [Предложение SELECT](../queries/select-clause.md)
