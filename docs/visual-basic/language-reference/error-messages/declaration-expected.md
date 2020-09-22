---
title: Ожидается объявление
ms.date: 07/20/2015
f1_keywords:
- vbc30188
- bc30188
helpviewer_keywords:
- BC30188
ms.assetid: da6b1df3-fe6b-4415-88e6-0977e5189e0b
ms.openlocfilehash: ee8f1f9ec26dc6c938f0b412dfe30832e3cfe165
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874530"
---
# <a name="declaration-expected"></a>Ожидается объявление

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
