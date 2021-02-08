---
description: 'Дополнительные сведения о: BC30269: " <methodname> " имеет несколько определений с одинаковыми сигнатурами'
title: Метод <methodname> несколько раз определен с одинаковыми подписями
ms.date: 07/20/2015
f1_keywords:
- vbc30269
- bc30269
helpviewer_keywords:
- BC30269
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
ms.openlocfilehash: 7364ee7a308fab96afce268ff0c92cd45717f1bd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795811"
---
# <a name="bc30269-methodname-has-multiple-definitions-with-identical-signatures"></a>BC30269: " \<methodname> " имеет несколько определений с одинаковыми сигнатурами

В `Function` `Sub` объявлении процедуры или используется то же имя процедуры и список аргументов, что и в предыдущем объявлении. Одной из возможных причин является попытка перегрузки исходной процедуры. Перегруженные процедуры должны иметь разные списки аргументов.

 **Идентификатор ошибки:** BC30269

## <a name="to-correct-this-error"></a>Исправление ошибки

- Измените имя процедуры или список аргументов или удалите повторяющееся объявление.

## <a name="see-also"></a>См. также

- [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Вопросы, связанные с перегрузкой процедур](../../programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)
