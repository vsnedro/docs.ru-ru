---
title: Оператор Yield
ms.date: 07/20/2015
f1_keywords:
- vb.Yield
helpviewer_keywords:
- iterators, Yield statement [Visual Basic]
- iterators [Visual Basic]
- Yield statement [Visual Basic]
ms.assetid: f33126c5-d7c4-43e2-8e36-4ae3f0703d97
ms.openlocfilehash: 783785f2a078b6ad8f975846c44ee4e716a12773
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866500"
---
# <a name="yield-statement-visual-basic"></a>Оператор Yield (Visual Basic)

Отправляет следующий элемент коллекции в `For Each...Next` оператор.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Yield expression  
```  
  
## <a name="parameters"></a>Параметры  
  
|Термин|Определение|  
|---|---|  
|`expression`|Обязательный. Выражение, которое неявно преобразуется в тип функции итератора или `Get` метода доступа, содержащего `Yield` инструкцию.|  
  
## <a name="remarks"></a>Remarks  

 `Yield`Инструкция возвращает по одному элементу коллекции за раз. `Yield`Инструкция включена в функцию итератора или `Get` метод доступа, который выполняет пользовательские итерации по коллекции.  
  
 Для использования функции итератора используется оператор [For Each... Следующий оператор](for-each-next-statement.md) или запрос LINQ. Каждая итерация `For Each` цикла вызывает функцию итератора. При `Yield` достижении оператора в функции итератора `expression` возвращается, а текущее расположение в коде сохраняется. При следующем вызове функции итератора выполнение возобновляется с этого места.  
  
 Неявное преобразование должно существовать из типа `expression` в инструкции в `Yield` возвращаемый тип итератора.  
  
 `Exit Function` `Return` Для завершения итерации можно использовать оператор или.  
  
 "Yield" не является зарезервированным словом и имеет специальное значение только при использовании в `Iterator` функции или `Get` методе доступа.  
  
 Дополнительные сведения о функциях и `Get` доступе итераторов см. в разделе [итераторы](../../programming-guide/concepts/iterators.md).  
  
## <a name="iterator-functions-and-get-accessors"></a>Функции итераторов и методы доступа Get  

 Объявление функции итератора или `Get` метода доступа должно удовлетворять следующим требованиям.  
  
- Он должен включать модификатор [итератора](../modifiers/iterator.md) .  
  
- Возвращаемый тип должен быть <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> или <xref:System.Collections.Generic.IEnumerator%601>.  
  
- У него не может быть `ByRef` параметров.  
  
 Функция итератора не может присутствовать в событии, конструкторе экземпляра, статическом конструкторе или статическом деструкторе.  
  
 Функция итератора может быть анонимной функцией. Дополнительные сведения см. в разделе [Итераторы](../../programming-guide/concepts/iterators.md).  
  
## <a name="exception-handling"></a>Обработка исключений  

 `Yield`Оператор может находиться внутри `Try` блока [конструкции try... Перехватить... Оператор finally](try-catch-finally-statement.md). `Try`Блок, содержащий `Yield` оператор, может иметь `Catch` блоки и может иметь `Finally` блок.  
  
 `Yield`Оператор не может находиться внутри `Catch` блока или блока `Finally` .  
  
 Если `For Each` тело (за пределами функции итератора) создает исключение, `Catch` блок в функции итератора не выполняется, но `Finally` выполняется блок в функции iterator. `Catch`Блок внутри функции итератора перехватывает только исключения, происходящие внутри функции итератора.  
  
## <a name="technical-implementation"></a>Техническая реализация  

 Следующий код возвращает `IEnumerable (Of String)` из функции-итератора, а затем выполняет итерацию по элементам объекта `IEnumerable (Of String)` .  
  
```vb  
Dim elements As IEnumerable(Of String) = MyIteratorFunction()  
    …  
For Each element As String In elements  
Next  
```  
  
 Вызов метода `MyIteratorFunction` не выполняет тело функции. Вместо этого вызов возвращает `IEnumerable(Of String)` в переменную `elements`.  
  
 В итерации цикла `For Each` метод <xref:System.Collections.IEnumerator.MoveNext%2A> вызывается для `elements`. Этот вызов выполняет тело `MyIteratorFunction` до достижения следующего оператора `Yield`. `Yield`Оператор возвращает выражение, которое определяет не только значение `element` переменной для использования в теле цикла, но также <xref:System.Collections.Generic.IEnumerator%601.Current%2A> свойство элементов, которое является `IEnumerable (Of String)` .  
  
 В каждой последующей итерации цикла `For Each` выполнение тела итератора продолжается с места остановки и при достижении оператора `Yield` оно снова останавливается. `For Each`Цикл завершается при достижении конца функции итератора или `Return` `Exit Function` оператора или.  
  
## <a name="example"></a>Пример  

 В следующем примере содержится `Yield` оператор, который находится внутри блока [for... Следующий](for-next-statement.md) цикл. Каждая итерация тела оператора [for each](for-each-next-statement.md) в `Main` создает вызов `Power` функции итератора. При каждом вызове функции итератора происходит переход к следующему выполнению оператора `Yield`, которое осуществляется во время следующей итерации цикла `For…Next`.  
  
 Тип возвращаемого значения метода итератора — это <xref:System.Collections.Generic.IEnumerable%601> тип интерфейса итератора. При вызове метода итератора возвращается перечисляемый объект, содержащий степени числа.  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a>Пример  

 В следующем примере демонстрируется метод доступа `Get`, представляющий собой итератор. Объявление свойства содержит `Iterator` модификатор.  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 Дополнительные примеры см. в разделе [итераторы](../../programming-guide/concepts/iterators.md).  
  
## <a name="see-also"></a>См. также

- [Операторы](index.md)
