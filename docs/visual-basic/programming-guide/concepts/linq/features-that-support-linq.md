---
title: Функции, поддерживающие LINQ
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, LINQ features
- LINQ [Visual Basic], features supporting LINQ
ms.assetid: c821bb50-b6f6-4cf9-8aba-2717e465bd3a
ms.openlocfilehash: bd63cd36c1f85fd89349293a71ecc5b281165380
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91078310"
---
# <a name="visual-basic-features-that-support-linq"></a>Возможности Visual Basic, поддерживающие LINQ

Языковой интегрированный запрос (LINQ) относится к технологии в Visual Basic, которая поддерживает синтаксис запросов и другие языковые конструкции непосредственно на языке. При использовании LINQ нет необходимости изучать новый язык для запроса к внешнему источнику данных. С помощью Visual Basic можно выполнять запросы к данным в реляционных базах данных, хранилищах XML или объектах. Такая интеграция возможностей запросов в язык обеспечивает проверку синтаксических ошибок и безопасности типов во время компиляции. Эта интеграция также гарантирует, что вы уже знакомы с большинством возможностей для написания сложных, разнообразных запросов в Visual Basic.  
  
 В следующих разделах описаны языковые конструкции, которые поддерживают LINQ в достаточно подробном виде, чтобы начать чтение вводной документации, примеры кода и примеры приложений. Вы также можете щелкнуть ссылки, чтобы найти более подробное объяснение того, как функции языка объединены, чтобы включить запросы, интегрированные в язык. Лучше всего начать с [пошагового руководства: написание запросов в Visual Basic](walkthrough-writing-queries.md).  
  
## <a name="query-expressions"></a>Выражения запросов  

 Выражения запросов в Visual Basic могут быть выражены в декларативном синтаксисе, аналогичном SQL или XQuery. Во время компиляции синтаксис запроса преобразуется в вызовы методов в реализацию методов расширения стандартных операторов запросов поставщика LINQ. Приложения контролируют, какие стандартные операторы запросов находятся в области, указывая соответствующее пространство имен с помощью `Imports` оператора. Синтаксис выражения запроса Visual Basic выглядит следующим образом:  
  
 [!code-vb[VbLINQVbFeatures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#1)]  
  
 Дополнительные сведения см. в статье [Знакомство с LINQ в Visual Basic](../../language-features/linq/introduction-to-linq.md).  
  
## <a name="implicitly-typed-variables"></a>Неявно типизированные переменные  

 Вместо явного указания типа при объявлении и инициализации переменной можно разрешить компилятору определять и назначать тип. Это называется *выводом локального типа*.  
  
 Переменные, типы которых выводятся строго, точно так же, как переменные, тип которых указан явным образом. Локальное определение типа работает только при определении локальной переменной внутри тела метода. Дополнительные сведения см. в разделе [оператор Option Infer](../../../language-reference/statements/option-infer-statement.md) и [определение локального типа](../../language-features/variables/local-type-inference.md).  
  
 В следующем примере показан вывод локального типа. Чтобы использовать этот пример, необходимо задать `Option Infer` для значение `On` .  
  
 [!code-vb[VbLINQVbFeatures#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#2)]  
  
 Вывод локального типа также позволяет создавать анонимные типы, описанные далее в этом разделе и необходимые для запросов LINQ.  
  
 В следующем примере LINQ определение типа происходит, если имеет значение `Option Infer` `On` или `Off` . Ошибка времени компиляции возникает, если `Option Infer` имеет значение `Off` , а `Option Strict` имеет значение `On` .  
  
 [!code-vb[VbLINQVbFeatures#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#3)]  
  
## <a name="object-initializers"></a>Инициализаторы объектов  

 Инициализаторы объектов используются в выражениях запросов, если необходимо создать анонимный тип для хранения результатов запроса. Они также могут использоваться для инициализации объектов именованных типов за пределами запросов. С помощью инициализатора объектов можно инициализировать объект в одной строке без явного вызова конструктора. При условии, что у вас есть класс с именем `Customer` Public `Name` и `Phone` свойства, а также другие свойства, инициализатор объекта можно использовать следующим образом:  
  
 [!code-vb[VbLINQVbFeatures#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#4)]  
  
 Дополнительные сведения см. в разделе [инициализаторы объектов: именованные и анонимные типы](../../language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).  
  
## <a name="anonymous-types"></a>Анонимные типы  

 Анонимные типы предоставляют удобный способ временного группирования набора свойств в элемент, который необходимо включить в результат запроса. Это позволяет выбрать любое сочетание доступных полей в запросе в любом порядке, не определяя именованный тип данных для элемента.  
  
 *Анонимный тип* создается компилятором динамически. Имя типа назначается компилятором и может изменяться при каждой новой компиляции. Поэтому имя нельзя использовать напрямую. Анонимные типы инициализируются следующим образом:  
  
 [!code-vb[VbLINQVbFeatures#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#5)]  
  
 Дополнительные сведения см. в статье [Анонимные типы](../../language-features/objects-and-classes/anonymous-types.md).  
  
## <a name="extension-methods"></a>Методы расширения  

 Методы расширения позволяют добавлять методы к типу данных или интерфейсу извне определения. Эта функция позволяет, по сути, добавлять новые методы к существующему типу без фактического изменения типа. Стандартные операторы запросов сами по себе представляют собой набор методов расширения, которые предоставляют функциональность запросов LINQ для любого типа, реализующего интерфейс <xref:System.Collections.Generic.IEnumerable%601> . Другие расширения для <xref:System.Collections.Generic.IEnumerable%601> включения <xref:System.Linq.Enumerable.Count%2A> , <xref:System.Linq.Enumerable.Union%2A> и <xref:System.Linq.Enumerable.Intersect%2A> .  
  
 Следующий метод расширения добавляет метод Print в <xref:System.String> класс.  
  
 [!code-vb[VbLINQVbFeatures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#6)]  
  
 Метод вызывается как обычный метод экземпляра <xref:System.String> :  
  
 [!code-vb[VbLINQVbFeatures#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#7)]  
  
 Дополнительные сведения см. в разделе [Методы расширения](../../language-features/procedures/extension-methods.md).  
  
## <a name="lambda-expressions"></a>Лямбда-выражения  

 Лямбда-выражение — это функция без имени, которая вычисляет и возвращает одно значение. В отличие от именованных функций лямбда-выражение может быть определено и выполнено одновременно. В следующем примере отображается 4.  
  
 [!code-vb[VbLINQVbFeatures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#8)]  
  
 Можно присвоить определение лямбда-выражения имени переменной, а затем использовать имя для вызова функции. В следующем примере также отображается 4.  
  
 [!code-vb[VbLINQVbFeatures#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#12)]  
  
 В LINQ лямбда-выражения лежат во многих стандартных операторах запросов. Компилятор создает лямбда-выражения для записи вычислений, определенных в основных методах запросов, таких как `Where` ,,, `Select` `Order By` `Take While` и других.  
  
 Например, следующий код определяет запрос, который возвращает всех старших учащихся из списка учащихся.  
  
 [!code-vb[VbLINQVbFeatures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#9)]  
  
 Определение запроса компилируется в код, похожий на следующий пример, который использует два лямбда-выражения для указания аргументов для `Where` и `Select` .  
  
 [!code-vb[VbLINQVbFeatures#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#10)]  
  
 Любую из этих версий можно запустить с помощью `For Each` цикла:  
  
 [!code-vb[VbLINQVbFeatures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#11)]  
  
 Дополнительные сведения см. в разделе [Лямбда-выражения](../../language-features/procedures/lambda-expressions.md).  
  
## <a name="see-also"></a>См. также

- [LINQ (Visual Basic)](index.md)
- [Приступая к работе с LINQ в Visual Basic](getting-started-with-linq.md)
- [LINQ и строки (Visual Basic)](linq-and-strings.md)
- [Оператор Option Infer](../../../language-reference/statements/option-infer-statement.md)
- [Оператор Option Strict](../../../language-reference/statements/option-strict-statement.md)
