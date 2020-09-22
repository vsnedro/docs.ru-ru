---
title: Авто
ms.date: 07/20/2015
f1_keywords:
- vb.Auto
helpviewer_keywords:
- Auto keyword [Visual Basic], external references
- Declare statement [Visual Basic], marshaling strings
- Auto keyword [Visual Basic]
- Auto keyword [Visual Basic], marshaling strings
ms.assetid: bf79ba95-a62c-48a5-916f-0ac7a52c13ec
ms.openlocfilehash: 799a7320b701384dc5f4b4b46fef8544f6b15b02
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875511"
---
# <a name="auto-visual-basic"></a>Auto (Visual Basic)

Указывает, что Visual Basic должны маршалировать строки согласно правилам .NET Framework, исходя из внешнего имени объявляемой внешней процедуры.  
  
 При вызове процедуры, определенной вне проекта, Visual Basic компилятор не имеет доступа к информации, которая необходима для правильного вызова процедуры. Эти сведения включают в себя расположение процедуры, способ ее определения, последовательность вызова и тип возвращаемого значения, а также используемую строковую кодировку. [Инструкция DECLARE](../statements/declare-statement.md) создает ссылку на внешнюю процедуру и предоставляет эти необходимые сведения.  
  
 `charsetmodifier`Часть в `Declare` инструкции предоставляет сведения о кодировке для упаковки строк во время вызова внешней процедуры. Он также влияет на то, как Visual Basic ищет имя внешней процедуры во внешнем файле. `Auto`Модификатор указывает, что Visual Basic должен маршалировать строки в соответствии с правилами .NET Framework и должен определить базовый набор символов платформы времени выполнения и, возможно, изменить имя внешней процедуры в случае сбоя первоначального поиска. Дополнительные сведения см. в разделе «Наборы символов» в [операторе Declare](../statements/declare-statement.md).  
  
 Если модификатор кодировки не указан, используется значение `Ansi` по умолчанию.  
  
## <a name="remarks"></a>Remarks  

 `Auto`Модификатор можно использовать в этом контексте:  
  
 [Declare Statement](../statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>Примечания для разработчиков смарт-устройств  

 Это ключевое слово не поддерживается.  
  
## <a name="see-also"></a>См. также

- [Набора](ansi.md)
- [Юникод](unicode.md)
- [Ключевые слова](../keywords/index.md)
