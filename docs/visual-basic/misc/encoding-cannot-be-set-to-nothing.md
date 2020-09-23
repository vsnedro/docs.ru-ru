---
title: Параметру Encoding нельзя присвоить значение Nothing
ms.date: 07/20/2015
ms.assetid: 59f7c731-8291-4a85-bf51-c225e48cdc84
ms.openlocfilehash: 0356098ca3fb41804ea396b0ff792cf2990b3340
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077544"
---
# <a name="encoding-cannot-be-set-to-nothing"></a>Параметру Encoding нельзя присвоить значение Nothing

Не удалось выполнить чтение или запись в файл, так как параметр `encoding` установлен в значение `Nothing` , но требует допустимое значение.  
  
 <xref:System.Text.Encoding> используется для определения, какая кодировка должна использоваться при записи в файл. Кодировка по умолчанию — UTF-8.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Предоставьте допустимое значение для параметра `encoding` .  
  
## <a name="see-also"></a>См. также

- [Кодировки файлов](../developing-apps/programming/drives-directories-files/file-encodings.md)
- [Чтение из файлов](../developing-apps/programming/drives-directories-files/reading-from-files.md)
- [Запись в файлы](../developing-apps/programming/drives-directories-files/writing-to-files.md)
- [My. Computer. FileSystem. ReadAllText](xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A)
- [My. Computer. FileSystem. WriteAllText](xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A)
