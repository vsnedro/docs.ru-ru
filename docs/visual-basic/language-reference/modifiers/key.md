---
description: 'Дополнительные сведения: Key (Visual Basic)'
title: Клавиши
ms.date: 07/20/2015
f1_keywords:
- vb.AnonymousKey
helpviewer_keywords:
- anonymous types [Visual Basic], key
- Key [Visual Basic]
- Key keyword [Visual Basic]
ms.assetid: 7697a928-7d14-4430-a72a-c9e96e8d6c11
ms.openlocfilehash: 5ec918da661144053824ca2a734cdec11873b0e6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99640801"
---
# <a name="key-visual-basic"></a>Key (Visual Basic)

`Key`Ключевое слово позволяет задать поведение для свойств анонимных типов. Только свойства, указанные в качестве ключевых свойств, участвуют в тестах равенства между экземплярами анонимного типа или вычислении значений хэш-кода. Значения ключевых свойств нельзя изменить.  
  
 Вы назначаете свойство анонимного типа в качестве ключевого свойства, помещая ключевое слово `Key` перед его объявлением в списке инициализации. В следующем примере `Airline` и `FlightNo` являются ключевыми свойствами, но `Gate` не.  
  
 [!code-vb[VbVbalrAnonymousTypes#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#26)]  
  
 При создании нового анонимного типа он наследуется непосредственно от <xref:System.Object> . Компилятор переопределяет три наследуемых члена: <xref:System.Object.Equals%2A> , <xref:System.Object.GetHashCode%2A> и <xref:System.Object.ToString%2A> . Код переопределения, созданный для <xref:System.Object.Equals%2A> и <xref:System.Object.GetHashCode%2A> , основан на ключевых свойствах. Значение, если в типе нет ключевых свойств <xref:System.Object.GetHashCode%2A> и <xref:System.Object.Equals%2A> они не переопределяются.  
  
## <a name="equality"></a>Равенство  

 Два экземпляра анонимных типов равны, если они являются экземплярами одного типа и если значения их ключевых свойств равны. В следующих примерах `flight2` значение равно `flight1` из предыдущего примера, так как они являются экземплярами одного и того же анонимного типа и имеют совпадающие значения для их ключевых свойств. Однако `flight3` не равно, `flight1` поскольку имеет другое значение для ключевого свойства, `FlightNo` . Тип экземпляра отличается `flight4` от типа, `flight1` так как он определяет различные свойства в качестве ключевых свойств.  
  
 [!code-vb[VbVbalrAnonymousTypes#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#27)]  
  
 Если два экземпляра объявляются только с неключевыми свойствами, идентичными в имени, типе, порядке и значении, два экземпляра не равны. Экземпляр без ключевых свойств равен только самому себе.  
  
 Дополнительные сведения об условиях, при которых два экземпляра анонимных типов являются экземплярами одного и того же анонимного типа, см. в разделе [анонимные типы](../../programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
## <a name="hash-code-calculation"></a>Вычисление хэш-кода  

 Например <xref:System.Object.Equals%2A> , хэш-функция, определенная в <xref:System.Object.GetHashCode%2A> для анонимного типа, основана на ключевых свойствах типа. В следующих примерах показано взаимодействие между ключевыми свойствами и значениями хэш-кода.  
  
 Экземпляры анонимного типа, имеющие одинаковые значения для всех ключевых свойств, имеют одинаковое значение хэш-кода, даже если неключевые свойства не имеют совпадающих значений. Следующая инструкция возвращает значение `True`.  
  
 [!code-vb[VbVbalrAnonymousTypes#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#37)]  
  
 Экземпляры анонимного типа, имеющие разные значения для одного или нескольких ключевых свойств, имеют разные значения хэш-кода. Следующая инструкция возвращает значение `False`.  
  
 [!code-vb[VbVbalrAnonymousTypes#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#38)]  
  
 Экземпляры анонимных типов, которые обозначают различные свойства в качестве ключевых свойств, не являются экземплярами одного типа. Они имеют разные значения хэш-кода, даже если имена и значения всех свойств одинаковы. Следующая инструкция возвращает значение `False`.  
  
 [!code-vb[VbVbalrAnonymousTypes#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#39)]  
  
## <a name="read-only-values"></a>Значения Read-Only  

 Значения ключевых свойств нельзя изменить. Например, в `flight1` предыдущих примерах `Airline` `FlightNo` поля и доступны только для чтения, но `Gate` могут быть изменены.  
  
 [!code-vb[VbVbalrAnonymousTypes#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class2.vb#28)]  
  
## <a name="see-also"></a>См. также

- [Определение анонимного типа](../../programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)
- [Практическое руководство. Выведение имен свойств и типов в объявлениях анонимных типов](../../programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)
- [Анонимные типы](../../programming-guide/language-features/objects-and-classes/anonymous-types.md)
