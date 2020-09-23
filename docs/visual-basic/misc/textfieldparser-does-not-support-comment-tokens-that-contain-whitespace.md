---
title: TextFieldParser не поддерживает маркеры комментариев, содержащие пробелы
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_WhitespaceInToken
ms.assetid: 55107656-270e-4bbb-841a-478904df8e07
ms.openlocfilehash: 825f999f8eab3563dd77039ef19ae5e329bb4240
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91078506"
---
# <a name="textfieldparser-does-not-support-comment-tokens-that-contain-white-space"></a>TextFieldParser не поддерживает маркеры комментариев, содержащие пробелы

Представлен токен комментария, содержащий пробел. `TextFieldParser` не поддерживает токены комментариев, содержащие пробелы, если это не пробел в начале токена. Пробелы в начале токена игнорируются.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Укажите правильный токен комментария.  
  
## <a name="see-also"></a>См. также

- [Свойство TextFieldParser.CommentTokens](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.CommentTokens%2A)
- [Анализ текстовых файлов с помощью объекта TextFieldParser](../developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)
- [TextFieldParser Object](../language-reference/objects/textfieldparser-object.md)
