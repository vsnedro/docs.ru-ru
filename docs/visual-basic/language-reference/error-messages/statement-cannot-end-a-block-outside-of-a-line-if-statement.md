---
description: 'Дополнительные сведения о: BC32005: оператор не может заканчивать блок за пределами строки оператора if'
title: Оператор не может завершить блок за пределами однострочной инструкции If
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: afe856b2c2ea3fa1db029d35c5b876f5d67da411
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99731156"
---
# <a name="bc32005-statement-cannot-end-a-block-outside-of-a-line-if-statement"></a>BC32005: оператор не может заканчивать блок за пределами однострочного оператора if

Однострочный `If` оператор содержит несколько операторов, разделенных двоеточиями (:), одна из которых является `End` оператором для блока управления за пределами однострочного `If` . Однострочные `If` операторы не используют `End If` инструкцию.

 **Идентификатор ошибки:** BC32005

## <a name="to-correct-this-error"></a>Исправление ошибки

- Переместите однострочный `If` оператор за пределы блока управления, содержащего `End If` оператор.

## <a name="see-also"></a>См. также

- [Оператор If…Then…Else](../statements/if-then-else-statement.md)
