---
description: 'Подробнее: кодировка не может принимать значение Nothing'
title: Параметру Encoding нельзя присвоить значение Nothing
ms.date: 07/20/2015
ms.assetid: 59f7c731-8291-4a85-bf51-c225e48cdc84
ms.openlocfilehash: 4fa9cbd9488501b5295da8d8ace41ef06a706c12
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100462999"
---
# <a name="encoding-cannot-be-set-to-nothing"></a>Параметру Encoding нельзя присвоить значение Nothing

Не удалось выполнить чтение или запись в файл, так как параметр `encoding` установлен в значение `Nothing` , но требует допустимое значение.  
  
 <xref:System.Text.Encoding> используется для определения, какая кодировка должна использоваться при записи в файл. Кодировка по умолчанию — UTF-8.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Предоставьте допустимое значение для параметра `encoding` .  
  
## <a name="see-also"></a>См. также раздел

- [Кодировки файлов](../developing-apps/programming/drives-directories-files/file-encodings.md)
- [Чтение из файлов](../developing-apps/programming/drives-directories-files/reading-from-files.md)
- [Запись в файлы](../developing-apps/programming/drives-directories-files/writing-to-files.md)
- [My. Computer. FileSystem. ReadAllText](xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A)
- [My. Computer. FileSystem. WriteAllText](xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A)
