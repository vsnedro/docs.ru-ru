---
title: Inherits Statement
ms.date: 07/20/2015
f1_keywords:
- vb.Inherits
- Inherits
helpviewer_keywords:
- Inherits statement [Visual Basic]
- Inherits statement [Visual Basic], syntax
ms.assetid: 9e6fe042-9af3-4341-8093-fc3537770cf2
ms.openlocfilehash: 5d88a01f90bc91a88229d19aa2368f8c71075b2f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404503"
---
# <a name="inherits-statement"></a>Inherits Statement
Заставляет текущий класс или интерфейс наследовать атрибуты, переменные, свойства, процедуры и события из другого класса или набора интерфейсов.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Inherits basetypenames  
```  
  
## <a name="parts"></a>Компоненты  
  
|Термин|Определение|  
|---|---|  
|`basetypenames`|Обязательный. Имя класса, от которого наследует этот класс.<br /><br /> -или-<br /><br /> Имена интерфейсов, из которых наследуется этот интерфейс. Используйте запятые для разделения нескольких имен.|  
  
## <a name="remarks"></a>Комментарии  
 При использовании `Inherits` инструкция должна быть первой непустой строкой, не являющейся комментарием, в определении класса или интерфейса. Он должен следовать сразу за `Class` `Interface` оператором или.  
  
 Можно использовать `Inherits` только в классе или интерфейсе. Это означает, что контекст объявления для наследования не может быть исходным файлом, пространством имен, структурой, модулем, процедурой или блоком.  
  
## <a name="rules"></a>Правила  
  
- **Наследование класса.** Если класс использует `Inherits` инструкцию, можно указать только один базовый класс.  
  
     Класс не может наследовать от класса, вложенного в него.  
  
- **Наследование интерфейса.** Если интерфейс использует `Inherits` инструкцию, можно указать один или несколько базовых интерфейсов. Можно наследовать от двух интерфейсов, даже если каждый из них определяет член с тем же именем. В этом случае реализующий код должен использовать уточнение имени, чтобы указать, какой член он реализует.  
  
     Интерфейс не может наследовать от другого интерфейса с более узким уровнем доступа. Например, `Public` интерфейс не может наследовать от `Friend` интерфейса.  
  
     Интерфейс не может наследовать от вложенного в него интерфейса.  
  
 Примером наследования класса в .NET Framework является <xref:System.ArgumentException> класс, который наследует от <xref:System.SystemException> класса. Это обеспечивает <xref:System.ArgumentException> все предопределенные свойства и процедуры, необходимые системным исключениям, таким как <xref:System.Exception.Message%2A> свойство и <xref:System.Exception.ToString%2A> метод.  
  
 Примером наследования интерфейса в .NET Framework является <xref:System.Collections.ICollection> интерфейс, который наследует от <xref:System.Collections.IEnumerable> интерфейса. Это приводит <xref:System.Collections.ICollection> к наследованию определения перечислителя, необходимого для прохода по коллекции.  
  
## <a name="example"></a>Пример  
 В следующем примере оператор используется `Inherits` для демонстрации того, как класс с именем `thisClass` может наследовать все члены базового класса с именем `anotherClass` .  
  
 [!code-vb[VbVbalrStatements#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#37)]  
  
## <a name="example"></a>Пример  
 В следующем примере показано наследование нескольких интерфейсов.  
  
 [!code-vb[VbVbalrStatements#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#38)]  
  
 Интерфейс с именем `thisInterface` теперь включает все определения в <xref:System.IComparable> <xref:System.IDisposable> интерфейсах, и, <xref:System.IFormattable> унаследованные члены предоставляют соответствующие типы для сравнения двух объектов, высвобождения выделенных ресурсов и выражения значения объекта как `String` . Класс, реализующий, `thisInterface` должен реализовывать каждый член каждого базового интерфейса.  
  
## <a name="see-also"></a>См. также раздел

- [MustInherit](../modifiers/mustinherit.md)
- [NotInheritable](../modifiers/notinheritable.md)
- [Объекты и классы](../../programming-guide/language-features/objects-and-classes/index.md)
- [Основы наследования](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [Интерфейсы](../../programming-guide/language-features/interfaces/index.md)
