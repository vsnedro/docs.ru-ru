---
title: Юникод
ms.date: 07/20/2015
f1_keywords:
- vb.Unicode
helpviewer_keywords:
- Unicode, external references
- Declare statement [Visual Basic], marshaling strings
- Unicode keyword [Visual Basic]
- Unicode, marshaling strings
ms.assetid: 0021d5ff-3209-444e-8497-420f3e6ee075
ms.openlocfilehash: 9b1bc40bb52244deefc0486d3a40c4b961ad1ee5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402685"
---
# <a name="unicode-visual-basic"></a>Юникод (Visual Basic)
Указывает, что Visual Basic должны маршалировать все строки в значения Юникода независимо от имени объявляемой внешней процедуры.  
  
 При вызове процедуры, определенной вне проекта, Visual Basic компилятор не имеет доступа к информации, которая необходима для правильного вызова процедуры. Эти сведения включают в себя расположение процедуры, способ ее определения, последовательность вызова и тип возвращаемого значения, а также используемую строковую кодировку. [Инструкция DECLARE](../statements/declare-statement.md) создает ссылку на внешнюю процедуру и предоставляет эти необходимые сведения.  
  
 `charsetmodifier`Часть в `Declare` инструкции предоставляет сведения о кодировке для маршалирования строк во время вызова внешней процедуры. Он также влияет на то, как Visual Basic ищет имя внешней процедуры во внешнем файле. `Unicode`Модификатор указывает, что Visual Basic должен маршалировать все строки в значения Юникода и выполнять поиск процедуры, не изменяя ее имя во время поиска.  
  
 Если модификатор кодировки не указан, используется значение `Ansi` по умолчанию.  
  
## <a name="remarks"></a>Комментарии  
 `Unicode`Модификатор можно использовать в этом контексте:  
  
 [Declare Statement](../statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>Примечания для разработчиков смарт-устройств  
 Это ключевое слово не поддерживается.  
  
## <a name="see-also"></a>См. также раздел

- [Ansi](ansi.md)
- [Автоматически](auto.md)
- [Ключевые слова](../keywords/index.md)
