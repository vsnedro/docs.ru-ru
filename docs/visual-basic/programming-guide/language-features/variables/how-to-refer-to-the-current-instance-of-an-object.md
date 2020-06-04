---
title: Практическое руководство. Ссылка на текущий экземпляр объекта
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
ms.openlocfilehash: 43bfd54592fb1d26cbf7f268b7e098e01e3745d8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410429"
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a>Практическое руководство. Ссылка на текущий экземпляр объекта (Visual Basic)
*Текущим экземпляром* объекта является экземпляр, в котором в данный момент выполняется код.  
  
 Используйте `Me` ключевое слово для ссылки на текущий экземпляр.  
  
### <a name="to-refer-to-the-current-instance"></a>Ссылка на текущий экземпляр  
  
- Используйте `Me` ключевое слово, в котором обычно используется имя объектной переменной.  
  
    ```vb  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     Несмотря `Me` на то, что ведет себя как объектная переменная, вы не можете объявить ее или присвоить ей что-либо. `Me`всегда ссылается на текущий экземпляр.  
  
## <a name="see-also"></a>См. также раздел

- [Объектные переменные](object-variables.md)
- [Присваивание объектных переменных](object-variable-assignment.md)
- [Me, My, MyBase и MyClass](../../program-structure/me-my-mybase-and-myclass.md)
