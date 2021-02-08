---
description: 'Дополнительные сведения о: неправильная длина записи'
title: Недопустимая длина записи
ms.date: 07/20/2015
f1_keywords:
- vbrID59
ms.assetid: 0926a3a4-177b-4452-9b33-d8a01e24cc21
ms.openlocfilehash: 820597a3c4e157894aadb280ae141098cae7eed4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797059"
---
# <a name="bad-record-length"></a>Недопустимая длина записи

Некоторые из возможных причин этой ошибки:  
  
- Длина переменной записи, указанной в `FileGet` `FileGetObject` `FilePut` операторе, или, `FilePutObject` отличается от длины, указанной в соответствующем `FileOpen` операторе.  
  
- Переменная в `FilePut` `FilePutObject` операторе или включает строку переменной длины.  
  
- Переменная в `FilePut` или `FilePutObject` включает `Variant` тип или.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Убедитесь, что сумма размеров переменных фиксированной длины в определяемом пользователем типе, определяющем тип переменной записи, совпадает со значением, указанным в `FileOpen` `Len` предложении инструкции.  
  
2. Если переменная в `FilePut` `FilePutObject` операторе или содержит строку переменной длины, убедитесь, что длина строки переменной длины не меньше 2 символов, чем длина записи, заданная в `Len` предложении `FileOpen` инструкции.  
  
3. Если переменная в `FilePut` или имеет значение `FilePutObject` или включает, `Variant` Убедитесь, что длина строки переменной длины не меньше 4 байт, чем длина записи, указанная в `Len` предложении `FileOpen` инструкции.  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.FileSystem.FileGet%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FileGetObject%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePut%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePutObject%2A>
