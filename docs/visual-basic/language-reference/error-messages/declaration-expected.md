---
description: 'Дополнительные сведения о: BC30188: ожидается объявление'
title: Ожидается объявление
ms.date: 07/20/2015
f1_keywords:
- vbc30188
- bc30188
helpviewer_keywords:
- BC30188
ms.assetid: da6b1df3-fe6b-4415-88e6-0977e5189e0b
ms.openlocfilehash: b86c182fb9dc8ab7d624833136f0e87b072aed92
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796669"
---
# <a name="bc30188-declaration-expected"></a>BC30188: ожидается объявление

Недекларативный оператор, такой как оператор присваивания или цикла, происходит вне любой процедуры. За пределами процедур разрешены только объявления.

 Кроме того, программный элемент объявляется без ключевого слова объявления, такого как `Dim` или `Const` .

 **Идентификатор ошибки:** BC30188

## <a name="to-correct-this-error"></a>Исправление ошибки

- Переместите недекларативный оператор в тело процедуры.

- Начните объявление с помощью соответствующего ключевого слова объявления.

- Убедитесь, что ключевое слово объявления написано неправильно.

## <a name="see-also"></a>См. также

- [Процедуры](../../programming-guide/language-features/procedures/index.md)
- [Оператор Dim](../statements/dim-statement.md)
