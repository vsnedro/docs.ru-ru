---
title: Метод <methodname> несколько раз определен с одинаковыми подписями
ms.date: 07/20/2015
f1_keywords:
- vbc30269
- bc30269
helpviewer_keywords:
- BC30269
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
ms.openlocfilehash: 663b22421d1a0e401cfb3c135c99bd097163a78b
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160370"
---
# <a name="bc30269-methodname-has-multiple-definitions-with-identical-signatures"></a>BC30269: " \<methodname> " имеет несколько определений с одинаковыми сигнатурами

В `Function` `Sub` объявлении процедуры или используется то же имя процедуры и список аргументов, что и в предыдущем объявлении. Одной из возможных причин является попытка перегрузки исходной процедуры. Перегруженные процедуры должны иметь разные списки аргументов.

 **Идентификатор ошибки:** BC30269

## <a name="to-correct-this-error"></a>Исправление ошибки

- Измените имя процедуры или список аргументов или удалите повторяющееся объявление.

## <a name="see-also"></a>См. также

- [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Вопросы, связанные с перегрузкой процедур](../../programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)
