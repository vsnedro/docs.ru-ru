---
description: 'Дополнительные сведения: двойная кавычка не является допустимой лексемой комментария для полей с разделителями, где EscapeQuote имеет значение true'
title: Двойные кавычки не являются допустимой лексемой комментария для полей с разделителями, где EscapeQuote имеет значение True
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_InvalidComment
ms.assetid: 636d4b81-00ba-4cfd-98f7-4d57036f494d
ms.openlocfilehash: d0668c6ffb479e649d4d3900070dc125db6dec05
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797215"
---
# <a name="a-double-quote-is-not-a-valid-comment-token-for-delimited-fields-where-escapequote-is-set-to-true"></a>Двойные кавычки не являются допустимой лексемой комментария для полей с разделителями, где EscapeQuote имеет значение True

Введен знак кавычек в качестве разделителя для `TextFieldParser`, но `EscapeQuotes` имеет значение `True`.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Задайте для параметра `EscapeQuotes` значение `False`.  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>
- [Практическое руководство. Чтение из текстовых файлов с разделителями-запятыми](../../developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)
