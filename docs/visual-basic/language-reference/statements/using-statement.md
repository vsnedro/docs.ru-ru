---
description: 'Дополнительные сведения об инструкции: using (Visual Basic)'
title: Оператор Using
ms.date: 07/20/2015
f1_keywords:
- vb.using
helpviewer_keywords:
- resource disposal
- Try...Catch...Finally statements, equivalent to Using statement
- resources [Visual Basic], disposing
- Using statement [Visual Basic]
ms.assetid: 665d1580-dd54-4e96-a9a9-6be2a68948f1
ms.openlocfilehash: fea77a441182b7c3ecac58d4fe7f1297a87f086c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740890"
---
# <a name="using-statement-visual-basic"></a>Оператор Using (Visual Basic)

Объявляет начало `Using` блока и при необходимости получает системные ресурсы, которые блокируют элементы управления.

## <a name="syntax"></a>Синтаксис

```vb
Using { resourcelist | resourceexpression }
    [ statements ]
End Using
```

## <a name="parts"></a>Компоненты

|Термин|Определение|  
|---|---|  
|`resourcelist`|Требуется, если не указан `resourceexpression` . Список из одного или нескольких системных ресурсов, которые `Using` управляются этим блоком, разделенные запятыми.|  
|`resourceexpression`|Требуется, если не указан `resourcelist` . Ссылка на переменную или выражение, ссылающееся на системный ресурс, который должен управляться этим `Using` блоком.|  
|`statements`|Необязательный элемент. Блок операторов, `Using` выполняемых блоком.|  
|`End Using`|Обязательный элемент. Завершает определение `Using` блока и уничтожает все ресурсы, которыми он управляет.|  

 Каждый ресурс в `resourcelist` части имеет следующий синтаксис и части:

 `resourcename As New resourcetype [ ( [ arglist ] ) ]`

 -или-

 `resourcename As resourcetype = resourceexpression`

## <a name="resourcelist-parts"></a>ресаурцелист части

|Термин|Определение|  
|---|---|  
|`resourcename`|Обязательный. Ссылочная переменная, которая ссылается на системный ресурс, который `Using` контролируется блоком.|  
|`New`|Требуется, если `Using` инструкция получает ресурс. Если вы уже приобрели ресурс, используйте второй альтернативный синтаксис.|  
|`resourcetype`|Обязательный элемент. Класс ресурса. Класс должен реализовывать <xref:System.IDisposable> интерфейс.|  
|`arglist`|Необязательный элемент. Список аргументов, передаваемый конструктору для создания экземпляра `resourcetype` . См. [список параметров](parameter-list.md).|  
|`resourceexpression`|Обязательный элемент. Переменная или выражение, ссылающееся на системный ресурс, удовлетворяющий требованиям `resourcetype` . Если используется второй альтернативный синтаксис, необходимо получить ресурс перед передачей управления `Using` оператору.|  
  
## <a name="remarks"></a>Remarks

 Иногда коду требуется неуправляемый ресурс, например файловый обработчик, оболочка COM или соединение SQL. `Using`Блок гарантирует удаление одного или нескольких таких ресурсов при завершении кода с ними. Это делает их доступными для использования другим кодом.

 Управляемые ресурсы удаляются сборщиком мусора платформа .NET Framework (GC) без дополнительного написания кода для вашей части. `Using`Для управляемых ресурсов блок не требуется. Однако можно по-прежнему использовать `Using` блок для принудительного удаления управляемого ресурса вместо ожидания сборщика мусора.

 `Using`Блок состоит из трех частей: приобретение, использование и утилизация.

- *Получение* означает создание переменной и ее инициализацию для ссылки на системный ресурс. `Using`Инструкция может получить один или несколько ресурсов, либо можно получить ровно один ресурс, прежде чем входить в блок и передать его в `Using` инструкцию. При указании необходимо `resourceexpression` получить ресурс перед передачей управления `Using` оператору.

- *Использование* означает доступ к ресурсам и выполнение действий с ними. Операторы между `Using` и `End Using` представляют использование ресурсов.

- *Реализация* означает вызов <xref:System.IDisposable.Dispose%2A> метода для объекта в `resourcename` . Это позволяет объекту очищать свои ресурсы. `End Using`Оператор уничтожает ресурсы под `Using` управлением блока.

## <a name="behavior"></a>Поведение

 `Using`Блок ведет себя подобно `Try` конструкции..., `Finally` в которой `Try` блок использует ресурсы и `Finally` блок удаляет их. По этой причине `Using` блок гарантирует освобождение ресурсов, независимо от того, как вы выйдете из блока. Это справедливо даже в случае необработанного исключения, за исключением <xref:System.StackOverflowException> .

 Область каждой переменной ресурса, полученной `Using` инструкцией, ограничена `Using` блоком.

 Если в инструкции указано более одного системного ресурса `Using` , то такой результат будет таким же, как если бы вложенные `Using` блоки совпадали друг с другом.

 Если `resourcename` имеет значение `Nothing` , вызов не выполняется <xref:System.IDisposable.Dispose%2A> и исключение не создается.

## <a name="structured-exception-handling-within-a-using-block"></a>Структурированная обработка исключений в блоке using

 Если необходимо выполнить обработку исключения, которое может возникнуть в `Using` блоке, можно добавить `Try` `Finally` к нему полную конструкцию... Если необходимо решить, когда `Using` инструкция не сможет получить ресурс, можно проверить, `resourcename` имеет ли это значение `Nothing` .

## <a name="structured-exception-handling-instead-of-a-using-block"></a>Структурированная обработка исключений вместо блока using

 Если требуется более точный контроль за приобретением ресурсов или требуется дополнительный код в `Finally` блоке, можно переписать `Using` блок как `Try` конструкцию... `Finally` . В следующем примере показаны скелеты `Try` и `Using` конструкции, эквивалентные в приобретении и утилизации `resource` .

```vb
Using resource As New resourceType
    ' Insert code to work with resource.
End Using

' For the acquisition and disposal of resource, the following  
' Try construction is equivalent to the Using block.
Dim resource As New resourceType
Try
    ' Insert code to work with resource.
Finally
    If resource IsNot Nothing Then
        resource.Dispose()
    End If
End Try
```

> [!NOTE]
> Код внутри `Using` блока не должен назначать объект в `resourcename` другую переменную. При выходе из `Using` блока ресурс удаляется, а другая переменная не может получить доступ к ресурсу, на который он указывает.

## <a name="example"></a>Пример

 В следующем примере создается файл с именем log.txt и в файл записывается две строки текста. В примере также считывается тот же файл и отображаются строки текста:

 Поскольку <xref:System.IO.TextWriter> классы и <xref:System.IO.TextReader> реализуют <xref:System.IDisposable> интерфейс, код может использовать инструкции, `Using` чтобы убедиться, что файл правильно закрыт после операций записи и чтения.

 [!code-vb[VbVbalrStatements#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#50)]

## <a name="see-also"></a>См. также раздел

- <xref:System.IDisposable>
- [Оператор Try...Catch...Finally](try-catch-finally-statement.md)
- [Практическое руководство. Удаление системного ресурса](../../programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)
