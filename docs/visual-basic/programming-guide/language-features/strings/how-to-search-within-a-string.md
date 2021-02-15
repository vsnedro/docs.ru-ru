---
description: Дополнительные сведения см. в статье как искать в строке (Visual Basic)
title: Практические руководства. Поиск в строке
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], finding
- strings [Visual Basic], searching
- examples [Visual Basic], strings
ms.assetid: ae4c79e0-08ea-489f-bdb2-5eb6d355f284
ms.openlocfilehash: dab9faf91eef2e6d845805693227e1a6735ec796
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100429732"
---
# <a name="how-to-search-within-a-string-visual-basic"></a>Как выполнить поиск в строке (Visual Basic)

В этой статье приведен пример поиска в строке в Visual Basic.

## <a name="example"></a>Пример

В этом примере вызывается <xref:System.String.IndexOf%2A> метод для <xref:System.String> объекта, чтобы сообщить индекс первого вхождения подстроки:

 [!code-vb[VbVbalrStrings#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#71)]

## <a name="robust-programming"></a>Отказоустойчивость

<xref:System.String.IndexOf%2A>Метод возвращает расположение первого символа в первом вхождении подстроки. Индекс основан на 0, что означает, что первый символ строки имеет индекс 0.

Если не <xref:System.String.IndexOf%2A> находит подстроку, возвращается значение-1.

<xref:System.String.IndexOf%2A>Метод учитывает регистр и использует текущий язык и региональные параметры.

Для оптимального управления ошибками может потребоваться заключить Поиск строки в `Try` блок [конструкции try... Перехватить... Построение оператора finally](../../../language-reference/statements/try-catch-finally-statement.md) .

## <a name="see-also"></a>См. также раздел

- <xref:System.String.IndexOf%2A>
- [Оператор Try...Catch...Finally](../../../language-reference/statements/try-catch-finally-statement.md)
- [Знакомство со строками в Visual Basic](introduction-to-strings.md)
- [Строки](index.md)
