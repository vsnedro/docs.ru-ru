---
title: Характеристики объявленных элементов
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic], lifetime
- access levels, declared elements
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- elements [Visual Basic], programming
- scope [Visual Basic], declared elements
- lifetime [Visual Basic], declared elements
- declared elements [Visual Basic], access level
- data types [Visual Basic], declared elements
- declared elements [Visual Basic], visibility
ms.assetid: 1bc40fb8-b67c-4428-90a4-76b630ae2583
ms.openlocfilehash: 36c55475b4930dc6c3202d52ef742072d5cee3e1
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075282"
---
# <a name="declared-element-characteristics-visual-basic"></a>Характеристики объявленных элементов (Visual Basic)

*Характеристика* объявленного элемента — это аспект этого элемента, который влияет на способ взаимодействия кода с ним. С каждым объявленным элементом связано одно или несколько из следующих характеристик:  
  
- *Тип данных* — значения, которые может содержать элемент, и способ хранения этих значений. Дополнительные сведения см. в разделе [Типы данных](../../../language-reference/data-types/index.md).  
  
- Время *существования* — период времени выполнения, в течение которого элемент доступен для использования. Дополнительные сведения см. [в разделе время существования в Visual Basic](lifetime.md).  
  
- *Scope* — набор всего кода, который может ссылаться на элемент, без уточнения его имени. Дополнительные сведения см. в разделе [руководство. Управление областью действия переменной](how-to-control-the-scope-of-a-variable.md).  
  
- *Уровень доступа* — разрешение для кода, которое использует элемент. Дополнительные сведения см. в разделе [руководство. Управление доступностью переменной](how-to-control-the-availability-of-a-variable.md).  
  
## <a name="characteristics-of-the-elements"></a>Характеристики элементов  

 В следующей таблице показаны объявленные элементы и характеристики, которые применяются к каждому из них.  
  
|Элемент|Тип данных|Время существования|Область <sup>1</sup>|Уровень доступа|  
|-------------|---------------|--------------|------------------------|------------------|  
|Переменная|Да|Да|Да|Да|  
|Константа|Да|Нет|Да|Да|  
|Перечисление|Да|Нет|Да|Да|  
|structure|Нет|Нет|Да|Да|  
|Свойство|Да|Да|Да|Да|  
|Метод|Нет|Да|Да|Да|  
|Процедура ( `Sub` или `Function` )|Нет|Да|Да|Да|  
|Параметр процедуры|Да|Да|Да|Нет|  
|Возврат функции|Да|Да|Да|Нет|  
|Оператор|Да|Нет|Да|Да|  
|Интерфейс|нет|Нет|Да|Да|  
|Класс|Нет|Нет|Да|Да|  
|Событие|Нет|Нет|Да|Да|  
|Делегат|нет|Нет|Да|Да|  
  
 <sup>1</sup> область иногда называется *видимостью*.  
  
## <a name="see-also"></a>См. также

- [Объявленные элементы](index.md)
- [Declared Element Names](declared-element-names.md)
- [References to Declared Elements](references-to-declared-elements.md)
- [Время существования в Visual Basic](lifetime.md)
- [Область видимости в Visual Basic](scope.md)
- [Уровни доступа в Visual Basic](access-levels.md)
- [Типы данных](../data-types/index.md)
- [Объявление переменной](../variables/variable-declaration.md)
