---
description: 'Дополнительные сведения: ни один из доступных перегруженных " <methodname> " не может вызываться с этими аргументами без сужения преобразования'
title: Ни один из доступных перегруженных " <methodname> " не может вызываться с этими аргументами без сужения преобразования
ms.date: 07/20/2015
f1_keywords:
- vbrAmbiguousMatch_NarrowingConversion1
ms.assetid: 2fdbadb9-8ef1-404a-a2ed-ce5f5e55cfcb
ms.openlocfilehash: ff70d43e5e5171055f631a6965b81b934bfb0b39
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100479183"
---
# <a name="no-accessible-overloaded-methodname-can-be-called-with-these-arguments-without-a-narrowing-conversion"></a>Ни один из доступных перегруженных " \<methodname> " не может вызываться с этими аргументами без сужения преобразования

Вызван перегруженный метод, однако ни один метод не может быть сопоставлен со списком предоставленных аргументов без сужающего преобразования.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Задайте имя `Option Strict Off`.  
  
2. Измените аргументы таким образом, чтобы они соответствовали одной из сигнатур перегруженного метода.  
  
## <a name="see-also"></a>См. также раздел

- [Передача аргументов по значению и по ссылке](../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
- [Widening and Narrowing Conversions](../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
