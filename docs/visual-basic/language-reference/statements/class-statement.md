---
title: Оператор Class
ms.date: 05/12/2018
f1_keywords:
- vb.Class
helpviewer_keywords:
- class modules
- Class statement [Visual Basic]
- classes [Visual Basic], fields
- fields [Visual Basic], of classes
- class types [Visual Basic], class statements
- classes [Visual Basic], creating
- classes [Visual Basic], data members
- data members [Visual Basic], of classes
ms.assetid: f2664f38-eb5a-4d4b-a374-1d041521fb6c
ms.openlocfilehash: bdb73772dfe0e6d49d89a4ef006b1bceac14c8ee
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397159"
---
# <a name="class-statement-visual-basic"></a>Оператор Class (Visual Basic)
Объявляет имя класса и вводит определение переменных, свойств, событий и процедур, содержащихся в классе.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ MustInherit | NotInheritable ] [ Partial ] _  
Class name [ ( Of typelist ) ]  
    [ Inherits classname ]  
    [ Implements interfacenames ]  
    [ statements ]  
End Class  
```  
  
## <a name="parts"></a>Компоненты  
  
|Термин|Определение|  
|---|---|  
|`attributelist`|Необязательный элемент. См. [список атрибутов](attribute-list.md).|  
|`accessmodifier`|Необязательный элемент. Может принимать следующие значения:<br /><br /> -   [Закрытый](../modifiers/public.md)<br />-   [От](../modifiers/protected.md)<br />-   [Объявление](../modifiers/friend.md)<br />-   [Личному](../modifiers/private.md)<br />-   [Защищенный дружественный](../modifiers/protected-friend.md)<br />- [Частный защищенный](../modifiers/private-protected.md)<br/><br/> См. раздел [уровни доступа в Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Необязательный элемент. См. раздел [Shadows](../modifiers/shadows.md).|  
|`MustInherit`|Необязательный элемент. См. раздел [MustInherit](../modifiers/mustinherit.md).|  
|`NotInheritable`|Необязательный элемент. См. [NotInheritable](../modifiers/notinheritable.md).|  
|`Partial`|Необязательный элемент. Указывает на частичное определение класса. См. раздел [partial](../modifiers/partial.md).|  
|`name`|Обязательный. Имя этого класса. См. раздел [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Необязательный элемент. Указывает, что это универсальный класс.|  
|`typelist`|Требуется, если используется ключевое слово [of](of-clause.md) . Список параметров типа для этого класса. См. [список типов](type-list.md).|  
|`Inherits`|Необязательный элемент. Указывает, что этот класс наследует члены другого класса. См. раздел [оператор Inherits](inherits-statement.md).|  
|`classname`|Требуется, если используется `Inherits` оператор. Имя класса, от которого наследует этот класс.|  
|`Implements`|Необязательный элемент. Указывает, что этот класс реализует члены одного или нескольких интерфейсов. См. [инструкцию Implements](implements-statement.md).|  
|`interfacenames`|Требуется, если используется `Implements` оператор. Имена интерфейсов, реализуемых этим классом.|  
|`statements`|Необязательный элемент. Инструкции, которые определяют элементы этого класса.|  
|`End Class`|Обязательный. Завершает `Class` Определение.|  
  
## <a name="remarks"></a>Комментарии  
 `Class`Оператор определяет новый тип данных. *Класс* является фундаментальным стандартным блоком объектно-ориентированного программирования (ООП). Дополнительные сведения см. в разделе [объекты и классы](../../programming-guide/language-features/objects-and-classes/index.md).  
  
 Можно использовать `Class` только на уровне пространства имен или модуля. Это означает, что *контекст объявления* для класса должен быть исходным файлом, пространством имен, классом, структурой, модулем или интерфейсом и не может быть процедурой или блоком. Дополнительные сведения см. в разделе [Контексты объявления и уровни доступа по умолчанию](declaration-contexts-and-default-access-levels.md).  
  
 Каждый экземпляр класса имеет время существования, не зависящее от всех остальных экземпляров. Это время жизни начинается, когда оно создается новым предложением [оператора](../operators/new-operator.md) или с помощью функции, такой как <xref:Microsoft.VisualBasic.Interaction.CreateObject%2A> . Он завершается, когда всем переменным, указывающим на экземпляр, присвоено значение [Nothing](../nothing.md) или экземпляры других классов.  
  
 Классы по умолчанию имеют доступ [Friend](../modifiers/friend.md) . Уровни доступа можно изменить с помощью модификаторов доступа. Дополнительные сведения см. [в разделе уровни доступа в Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Правила  
  
- **Вложенности.** Можно определить один класс в другом. Внешний класс называется *содержащим классом*, а внутренний класс называется *вложенным классом*.  
  
- **Цепочк.** Если класс использует [инструкцию Inherits](inherits-statement.md), можно указать только один базовый класс или интерфейс. Класс не может наследовать более чем от одного элемента.  
  
     Класс не может наследовать от другого класса с более узким уровнем доступа. Например, `Public` класс не может наследовать от `Friend` класса.  
  
     Класс не может наследовать от класса, вложенного в него.  
  
- **Реализации.** Если класс использует [оператор Implements](implements-statement.md), необходимо реализовать каждый элемент, определенный каждым интерфейсом, указанным в `interfacenames` . Исключением из этого является перереализация члена базового класса. Дополнительные сведения см. в разделе "перереализация" раздела [Implements](implements-clause.md).  
  
- **Свойство по умолчанию.** Класс может указывать не более одного свойства в качестве *свойства по умолчанию*. Дополнительные сведения см. в разделе [Default](../modifiers/default.md).  
  
## <a name="behavior"></a>Поведение  
  
- **Уровень доступа.** Внутри класса можно объявить каждый элемент с собственным уровнем доступа. Члены класса по умолчанию имеют [открытый](../modifiers/public.md) доступ, за исключением переменных и констант, которые по умолчанию имеют [частный](../modifiers/private.md) доступ. Если класс имеет более ограниченный доступ, чем один из его членов, приоритет имеет уровень доступа к классу.  
  
- **Которых.** Класс находится в области по всему его содержащимся пространству имен, классу, структуре или модулю.  
  
     Областью действия каждого члена класса является весь класс.  
  
     **Контролиру.** Visual Basic не поддерживает статические классы. Функциональный эквивалент статического класса предоставляется модулем. Дополнительные сведения см. в разделе [оператор Module](module-statement.md).  
  
     У членов класса есть время существования в зависимости от того, как и где они объявляются. Дополнительные сведения см. [в разделе время существования в Visual Basic](../../programming-guide/language-features/declared-elements/lifetime.md).  
  
- **Квалификацию.** Код за пределами класса должен уточнять имя члена именем этого класса.  
  
     Если код внутри вложенного класса делает неквалифицированную ссылку на программный элемент, Visual Basic ищет элемент сначала во вложенном классе, затем в его содержащем классе и так далее в самом внешнем содержащем элементе.  
  
## <a name="classes-and-modules"></a>Классы и модули  
 У этих элементов много сходства, но есть и некоторые важные отличия.  
  
- **Терминология.** В предыдущих версиях Visual Basic распознаются два типа модулей: *модули классов* (CLS-файлы) и *стандартные модули* (файлы. BAS). Текущая версия вызывает эти *классы* и *модули*соответственно.  
  
- **Общие члены.** Можно контролировать, является ли член класса общим или членом экземпляра.  
  
- **Объектная ориентация.** Классы являются объектно-ориентированными, но модули — нет. Можно создать один или несколько экземпляров класса. Дополнительные сведения см. в разделе [объекты и классы](../../programming-guide/language-features/objects-and-classes/index.md).  
  
## <a name="example"></a>Пример  
 В следующем примере оператор используется `Class` для определения класса и нескольких элементов.  
  
 [!code-vb[VbVbalrStatements#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#62)]  
  
## <a name="see-also"></a>См. также раздел

- [Объекты и классы](../../programming-guide/language-features/objects-and-classes/index.md)
- [Структуры и классы](../../programming-guide/language-features/data-types/structures-and-classes.md)
- [Оператор Interface](interface-statement.md)
- [Оператор Module](module-statement.md)
- [Property Statement](property-statement.md)
- [Время существования: создание и уничтожение объектов](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
- [Generic Types in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md)
- [Практическое руководство. Использование универсального класса](../../programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
