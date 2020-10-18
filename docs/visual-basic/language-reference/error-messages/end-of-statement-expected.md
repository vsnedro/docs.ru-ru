---
title: Ожидается окончание оператора
ms.date: 07/20/2015
f1_keywords:
- bc30205
- vbc30205
helpviewer_keywords:
- BC30205
ms.assetid: 53c7f825-a737-4b76-a1fa-f67745b8bd40
ms.openlocfilehash: 36883989fe5aa0b5c70aa9ab1f7c991fab99e778
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163133"
---
# <a name="bc30205-end-of-statement-expected"></a>BC30205: Ожидается конец оператора

Инструкция является синтаксически завершенной, но дополнительный программный элемент следует за элементом, который завершает инструкцию. В конце каждой инструкции требуется признак конца строки.

 Признак конца строки делит символы Visual Basic исходного файла на строки. Примерами признаков конца строки являются символ возврата каретки в Юникоде (&HD), символ перевода строки в Юникоде (&HA) и символ возврата каретки в Юникоде, за которым следует символ перевода строки в Юникоде. Дополнительные сведения о знаках конца строки см. в разделе [Спецификация языка Visual Basic](~/_vblang/spec/lexical-grammar.md#line-terminators).

 **Идентификатор ошибки:** BC30205

## <a name="to-correct-this-error"></a>Исправление ошибки

1. Убедитесь, что две разные инструкции случайно были помещены в одну и ту же строку.

2. Вставьте признак конца строки после элемента, который завершает инструкцию.

## <a name="see-also"></a>См. также

- [Практическое руководство. Разбиение и объединение инструкций в коде](../../programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
- [Операторы](../../programming-guide/language-features/statements.md)
