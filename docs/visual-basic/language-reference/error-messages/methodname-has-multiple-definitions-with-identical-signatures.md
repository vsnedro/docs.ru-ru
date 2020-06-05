---
title: Метод <methodname> несколько раз определен с одинаковыми подписями
ms.date: 07/20/2015
f1_keywords:
- vbc30269
- bc30269
helpviewer_keywords:
- BC30269
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
ms.openlocfilehash: 3b397711cc2fb1fd0c1dfd76899b162ab5fc1542
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397237"
---
# <a name="methodname-has-multiple-definitions-with-identical-signatures"></a>Метод \<methodname> несколько раз определен с одинаковыми подписями
В `Function` `Sub` объявлении процедуры или используется то же имя процедуры и список аргументов, что и в предыдущем объявлении. Одной из возможных причин является попытка перегрузки исходной процедуры. Перегруженные процедуры должны иметь разные списки аргументов.  
  
 **Идентификатор ошибки:** BC30269  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Измените имя процедуры или список аргументов или удалите повторяющееся объявление.  
  
## <a name="see-also"></a>См. также раздел

- [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Вопросы, связанные с перегрузкой процедур](../../programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)
