---
description: 'Дополнительные сведения: ни один из доступных перегруженных " <methodname> " не может вызываться с этими аргументами без сужения преобразования: <list>'
title: 'Ни один из доступных перегруженных "<methodname>" не может вызываться с этими аргументами без преобразования с сужением:  <list>'
ms.date: 07/20/2015
f1_keywords:
- vbrAmbiguousCall2
ms.assetid: 13b20ffa-9f02-4971-a3cb-e08b402fd971
ms.openlocfilehash: a802b420a01c1894feca2c61c0bfdbb7be5104f5
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100475712"
---
# <a name="no-accessible-overloaded-methodname-can-be-called-with-these-arguments-without-a-narrowing-conversion-list"></a>Ни один из доступных перегруженных "\<methodname>" не может вызываться с этими аргументами без преобразования с сужением: \<list>

Вызван перегруженный метод, однако он не может быть сопоставлен со списком указанных аргументов без сужающего преобразования.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Задайте имя `Option Strict Off`.
  
2. Измените аргументы таким образом, чтобы они соответствовали сигнатуре перегруженного метода.  
  
## <a name="see-also"></a>См. также раздел

- [Передача аргументов по значению и по ссылке](../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
- [Widening and Narrowing Conversions](../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
