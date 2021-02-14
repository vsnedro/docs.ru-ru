---
description: Дополнительные сведения см. в разделе Пошаговое руководство. реализация IEnumerable (Of T) в Visual Basic
title: Реализация IEnumerable
ms.date: 07/31/2018
helpviewer_keywords:
- control flow [Visual Basic]
- enumerable interfaces
- loop structures [Visual Basic], optimizing performance
- control flow [Visual Basic]
ms.assetid: c60d7589-51f2-4463-a2d5-22506bbc1554
ms.openlocfilehash: 87905e4f110d3a9d95b1cad642296ea8105f32f4
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100428146"
---
# <a name="walkthrough-implementing-ienumerableof-t-in-visual-basic"></a>Пошаговое руководство. Реализация IEnumerable(Of T) в Visual Basic

<xref:System.Collections.Generic.IEnumerable%601>Интерфейс реализуется классами, которые могут возвращать последовательность значений по одному элементу за раз. Преимущество возврата данных по одному элементу за раз заключается в том, что для работы с ним не нужно загружать полный набор данных в память. Для загрузки одного элемента из данных необходимо использовать достаточно памяти. Классы, реализующие `IEnumerable(T)` интерфейс, можно использовать с `For Each` циклами или запросами LINQ.  
  
 Например, рассмотрим приложение, которое должно считывать большой текстовый файл и возвращать каждую строку из файла, удовлетворяющего определенным условиям поиска. Приложение использует запрос LINQ для возврата строк из файла, соответствующих указанным критериям. Чтобы запросить содержимое файла с помощью запроса LINQ, приложение может загрузить содержимое файла в массив или коллекцию. Однако загрузка всего файла в массив или коллекцию занимают гораздо больше памяти, чем требуется. Запрос LINQ может вместо этого запросить содержимое файла с помощью перечислимого класса, возвращая только те значения, которые соответствуют критериям поиска. Запросы, возвращающие только несколько соответствующих значений, занимают гораздо меньше памяти.  
  
 Можно создать класс, реализующий <xref:System.Collections.Generic.IEnumerable%601> интерфейс для предоставления исходных данных в виде перечислимых данных. Класс, реализующий `IEnumerable(T)` интерфейс, потребует другого класса, реализующего <xref:System.Collections.Generic.IEnumerator%601> интерфейс для прохода по исходным данным. Эти два класса позволяют последовательно возвращаться элементы данных в виде определенного типа.  
  
 В этом пошаговом руководстве будет создан класс, реализующий `IEnumerable(Of String)` интерфейс, и класс, реализующий `IEnumerator(Of String)` интерфейс для считывания текстового файла по одной строке за раз.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-the-enumerable-class"></a>Создание класса Enumerable  
  
**Создание проекта класса Enumerable**

1. В Visual Basic в меню **файл** наведите указатель мыши на пункт **создать** и выберите пункт **проект**.

1. Убедитесь, что в диалоговом окне **Создание проекта** в области **Типы проектов** выбран пункт **Windows**. Выберите **Библиотеки классов** в области **Шаблоны**. В поле **Имя** введите `StreamReaderEnumerable` и нажмите кнопку **ОК**. Отобразится новый проект.

1. В **Обозреватель решений** щелкните правой кнопкой мыши файл Class1. vb и выберите команду **Переименовать**. Измените имя файла на `StreamReaderEnumerable.vb` и нажмите клавишу ВВОД. При переименовании файла класс также будет переименован в `StreamReaderEnumerable`. Этот класс реализует интерфейс `IEnumerable(Of String)`.

1. Щелкните правой кнопкой мыши проект Стреамреадеренумерабле, наведите указатель на пункт **Добавить** и выберите пункт **новый элемент**. Выберите шаблон **класса** . В поле **имя** введите `StreamReaderEnumerator.vb` и нажмите кнопку **ОК**.

 Первый класс в этом проекте является классом Enumerable и будет реализовывать `IEnumerable(Of String)` интерфейс. Этот универсальный интерфейс реализует <xref:System.Collections.IEnumerable> интерфейс и гарантирует, что потребители этого класса могут обращаться к значениям, введенным как `String` .  
  
**Добавление кода для реализации IEnumerable**

1. Откройте файл Стреамреадеренумерабле. vb.

2. В строке после `Public Class StreamReaderEnumerable` введите следующую команду и нажмите клавишу ВВОД.

     [!code-vb[VbVbalrIteratorWalkthrough#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#1)]

   Visual Basic автоматически заполняет класс членами, необходимыми для `IEnumerable(Of String)` интерфейса.
  
3. Этот перечислимый класс будет считывать строки из текстового файла по одной строке за раз. Добавьте следующий код в класс, чтобы предоставить открытый конструктор, который принимает путь к файлу в качестве входного параметра.

     [!code-vb[VbVbalrIteratorWalkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#2)]

4. Реализация <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> метода `IEnumerable(Of String)` интерфейса будет возвращать новый экземпляр `StreamReaderEnumerator` класса. Реализация `GetEnumerator` метода `IEnumerable` интерфейса может быть выполнена `Private` , поскольку необходимо предоставлять только члены `IEnumerable(Of String)` интерфейса. Замените код, который Visual Basic создан для `GetEnumerator` методов, следующим кодом.

     [!code-vb[VbVbalrIteratorWalkthrough#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#3)]  
  
**Добавьте код для реализации IEnumerator**

1. Откройте файл Стреамреадеренумератор. vb.

2. В строке после `Public Class StreamReaderEnumerator` введите следующую команду и нажмите клавишу ВВОД.

     [!code-vb[VbVbalrIteratorWalkthrough#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#4)]

   Visual Basic автоматически заполняет класс членами, необходимыми для `IEnumerator(Of String)` интерфейса.

3. Класс перечислителя открывает текстовый файл и выполняет файловый ввод-вывод для считывания строк из файла. Добавьте следующий код в класс, чтобы предоставить открытый конструктор, который принимает путь к файлу в качестве входного параметра и открывает текстовый файл для чтения.

     [!code-vb[VbVbalrIteratorWalkthrough#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#5)]

4. `Current`Свойства обоих `IEnumerator(Of String)` `IEnumerator` интерфейсов и возвращают текущий элемент из текстового файла в виде `String` . Реализация `Current` свойства `IEnumerator` интерфейса может быть выполнена `Private` , поскольку необходимо предоставлять только члены `IEnumerator(Of String)` интерфейса. Замените код, который Visual Basic создан для `Current` свойств, следующим кодом.

     [!code-vb[VbVbalrIteratorWalkthrough#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#6)]

5. `MoveNext`Метод `IEnumerator` интерфейса переходит к следующему элементу в текстовом файле и обновляет значение, возвращаемое `Current` свойством. Если больше нет элементов для чтения, `MoveNext` метод возвращает значение `False` ; в противном случае `MoveNext` метод возвращает значение `True` . Добавьте в метод `MoveNext` следующий код.

     [!code-vb[VbVbalrIteratorWalkthrough#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#7)]

6. `Reset`Метод `IEnumerator` интерфейса направляет итератор, указывающий на начало текстового файла, и очищает значение текущего элемента. Добавьте в метод `Reset` следующий код.

     [!code-vb[VbVbalrIteratorWalkthrough#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#8)]

7. `Dispose`Метод `IEnumerator` интерфейса гарантирует, что все неуправляемые ресурсы освобождаются до уничтожения итератора. Используемый `StreamReader` объектом файл является неуправляемым ресурсом и должен быть закрыт перед уничтожением экземпляра итератора. Замените код, который Visual Basic создан для `Dispose` метода, следующим кодом.

     [!code-vb[VbVbalrIteratorWalkthrough#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#9)]
  
## <a name="using-the-sample-iterator"></a>Использование примера итератора

 Класс Enumerable можно использовать в коде вместе с структурами элементов управления, для которых требуется объект, реализующий `IEnumerable` , например, `For Next` цикл или запрос LINQ. В следующем примере показано `StreamReaderEnumerable` в запросе LINQ.  
  
 [!code-vb[VbVbalrIteratorWalkthrough#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/Module1.vb#10)]  
  
## <a name="see-also"></a>См. также раздел

- [Introduction to LINQ in Visual Basic](../linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Поток управления](index.md)
- [Циклические структуры](loop-structures.md)
- [Оператор For Each…Next](../../../language-reference/statements/for-each-next-statement.md)
