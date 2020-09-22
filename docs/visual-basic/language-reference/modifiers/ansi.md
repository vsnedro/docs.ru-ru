---
title: Ansi
ms.date: 07/20/2015
f1_keywords:
- vb.Ansi
helpviewer_keywords:
- Declare statement [Visual Basic], marshaling strings [Visual Basic]
- ANSI, Visual Basic
- ANSI
ms.assetid: 4f1fa6ff-5557-41ab-b6da-90baf4c15917
ms.openlocfilehash: 8dfd830e4c7ed97c8813da4ad310ee59b26f44f8
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90868798"
---
# <a name="ansi-visual-basic"></a>Ansi (Visual Basic)

Указывает, что Visual Basic должны маршалировать все строки в значения Американский национальный институт стандартов (ANSI) (ANSI) независимо от имени объявляемой внешней процедуры.  
  
 При вызове процедуры, определенной вне проекта, Visual Basic компилятор не имеет доступа к информации, которая необходима для правильного вызова процедуры. Эти сведения включают в себя расположение процедуры, способ ее определения, последовательность вызова и тип возвращаемого значения, а также используемую строковую кодировку. [Инструкция DECLARE](../statements/declare-statement.md) создает ссылку на внешнюю процедуру и предоставляет эти необходимые сведения.  
  
 `charsetmodifier`Часть в `Declare` инструкции предоставляет сведения о кодировке для упаковки строк во время вызова внешней процедуры. Он также влияет на то, как Visual Basic ищет имя внешней процедуры во внешнем файле. `Ansi`Модификатор указывает, что Visual Basic должен маршалировать все строки в значения ANSI и выполнять поиск процедуры, не изменяя ее имя во время поиска.  
  
 Если модификатор кодировки не указан, используется значение `Ansi` по умолчанию.  
  
## <a name="remarks"></a>Remarks  

 `Ansi`Модификатор можно использовать в этом контексте:  
  
 [Declare Statement](../statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>Примечания для разработчиков смарт-устройств  

 Это ключевое слово не поддерживается.  
  
## <a name="see-also"></a>См. также

- [Автоматически](auto.md)
- [Юникод](unicode.md)
- [Ключевые слова](../keywords/index.md)
