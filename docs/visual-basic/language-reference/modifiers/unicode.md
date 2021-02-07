---
description: 'Дополнительные сведения: Юникод (Visual Basic)'
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
ms.openlocfilehash: b0c71d8fdefe3f0d240201e0d57265e5c6081d50
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700719"
---
# <a name="unicode-visual-basic"></a>Юникод (Visual Basic)

Указывает, что Visual Basic должны маршалировать все строки в значения Юникода независимо от имени объявляемой внешней процедуры.  
  
 При вызове процедуры, определенной вне проекта, Visual Basic компилятор не имеет доступа к информации, которая необходима для правильного вызова процедуры. Эти сведения включают в себя расположение процедуры, способ ее определения, последовательность вызова и тип возвращаемого значения, а также используемую строковую кодировку. [Инструкция DECLARE](../statements/declare-statement.md) создает ссылку на внешнюю процедуру и предоставляет эти необходимые сведения.  
  
 `charsetmodifier`Часть в `Declare` инструкции предоставляет сведения о кодировке для маршалирования строк во время вызова внешней процедуры. Он также влияет на то, как Visual Basic ищет имя внешней процедуры во внешнем файле. `Unicode`Модификатор указывает, что Visual Basic должен маршалировать все строки в значения Юникода и выполнять поиск процедуры, не изменяя ее имя во время поиска.  
  
 Если модификатор кодировки не указан, используется значение `Ansi` по умолчанию.  
  
## <a name="remarks"></a>Remarks  

 `Unicode`Модификатор можно использовать в этом контексте:  
  
 [Declare Statement](../statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>Примечания для разработчиков смарт-устройств  

 Это ключевое слово не поддерживается.  
  
## <a name="see-also"></a>См. также

- [Ansi](ansi.md)
- [Автоматически](auto.md)
- [Ключевые слова](../keywords/index.md)
