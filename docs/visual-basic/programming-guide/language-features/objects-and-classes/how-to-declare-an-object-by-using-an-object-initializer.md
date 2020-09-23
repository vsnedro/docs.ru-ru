---
title: Практическое руководство. Объявление объекта с помощью инициализатора объектов
ms.date: 07/20/2015
helpviewer_keywords:
- declaring objects using object initializer
- object initializers [Visual Basic]
- initializers [Visual Basic]
- Video How tos, Visual Basic
ms.assetid: 0f53a553-efd6-466d-80bf-6b679e5cd174
ms.openlocfilehash: 61f520a528c3d40b9d34807d517a9bf27ad40da8
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075230"
---
# <a name="how-to-declare-an-object-by-using-an-object-initializer-visual-basic"></a>Практическое руководство. Объявление объекта с помощью инициализатора объектов (Visual Basic)

Инициализаторы объектов позволяют объявлять и создавать экземпляры класса в одной инструкции. Кроме того, можно одновременно инициализировать один или несколько членов экземпляра без вызова параметризованного конструктора.  
  
 При использовании инициализатора объекта для создания экземпляра именованного типа вызывается конструктор без параметров для класса, за которым следует инициализация назначенных членов в указанном порядке.  
  
 В следующей процедуре показано, как создать экземпляр `Student` класса тремя разными способами. У класса есть имя, фамилия и свойства года, кроме других. Каждое из трех объявлений создает новый экземпляр `Student` , свойство `First` которого имеет значение "Michael", свойство которого установлено в значение `Last` "туккер", а всем остальным элементам присвоены значения по умолчанию. Результат каждого объявления в процедуре эквивалентен следующему примеру, в котором не используется инициализатор объекта.  
  
 [!code-vb[VbVbalrObjectInit#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#20)]  
  
 Сведения `Student` о реализации класса см. в разделе [как создать список элементов](../../concepts/linq/how-to-create-a-list-of-items.md). Можно скопировать код из этого раздела, чтобы настроить класс и создать список `Student` объектов для работы.  
  
### <a name="to-create-an-object-of-a-named-class-by-using-an-object-initializer"></a>Создание объекта именованного класса с помощью инициализатора объекта  
  
1. Начните объявление, как если бы вы планировали использовать конструктор.  
  
     `Dim student1 As New Student`  
  
2. Введите ключевое слово `With` , за которым следует список инициализации в фигурных скобках.  
  
     `Dim student1 As New Student With { <initialization list> }`  
  
3. В списке инициализация Включите каждое свойство, которое необходимо инициализировать, и присвойте ему начальное значение. Имя свойства предшествует точке.  
  
     [!code-vb[VbVbalrObjectInit#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#21)]  
  
     Можно инициализировать один или несколько членов класса.  
  
4. Кроме того, можно объявить новый экземпляр класса и присвоить ему значение. Сначала объявите экземпляр `Student` :  
  
     `Dim student2 As Student`  
  
5. Начните создание экземпляра `Student` обычным способом.  
  
     `Dim student2 As Student = New Student`  
  
6. Введите `With` и затем инициализатор объекта для инициализации одного или нескольких членов нового экземпляра.  
  
     [!code-vb[VbVbalrObjectInit#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#22)]  
  
7. Можно упростить определение в предыдущем шаге, опустив `As Student` . В этом случае компилятор определит, что `student3` является экземпляром `Student` , используя вывод локального типа.  
  
     [!code-vb[VbVbalrObjectInit#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#23)]  
  
     Дополнительные сведения см. в разделе [определение локального типа](../variables/local-type-inference.md).  
  
## <a name="see-also"></a>См. также

- [Вывод локального типа](../variables/local-type-inference.md)
- [Практическое руководство. Создание списка элементов](../../concepts/linq/how-to-create-a-list-of-items.md)
- [Инициализаторы объектов: именованные и анонимные типы](object-initializers-named-and-anonymous-types.md)
- [Анонимные типы](anonymous-types.md)
