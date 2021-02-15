---
description: Дополнительные сведения см. в разделе Пошаговое руководство. Написание запросов в Visual Basic
title: Написание запросов
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ [Visual Basic], walkthroughs
- LINQ [Visual Basic], writing queries
- writing LINQ queries [Visual Basic]
ms.assetid: f0045808-b9fe-4d31-88d1-473d9957211e
ms.openlocfilehash: 55a1b3382d587b7982b79448334c4688895fa6e6
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100466813"
---
# <a name="walkthrough-writing-queries-in-visual-basic"></a>Пошаговое руководство. Написание запросов в Visual Basic

В этом пошаговом руководстве показано, как можно использовать функции языка Visual Basic для написания выражений запросов Language-Integrated запросов (LINQ). В этом пошаговом руководстве показано, как создавать запросы к списку объектов Student, выполнять запросы и изменять их. Запросы включают в себя несколько функций, включая инициализаторы объектов, определение локального типа и анонимные типы.

После завершения этого пошагового руководства вы будете готовы перейти к образцам и документации для конкретного интересующего поставщика LINQ. Поставщики LINQ включают [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] , LINQ to DataSet и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] .

## <a name="create-a-project"></a>Создание проекта

### <a name="to-create-a-console-application-project"></a>Создание проекта консольного приложения

1. Запустите Visual Studio.

2. В меню **Файл** выберите пункт **Создать**, а затем команду **Проект**.

3. В списке **Установленные шаблоны** щелкните **Visual Basic**.

4. В списке типов проектов щелкните **консольное приложение**. В поле **имя** введите имя проекта и нажмите кнопку **ОК**.

    Создается проект. По умолчанию он содержит ссылку на System.Core.dll. Кроме того, в списке **Импортированные пространства имен** на [странице ссылки в конструкторе проектов (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic) содержится <xref:System.Linq?displayProperty=nameWithType> пространство имен.

5. На [странице Компиляция в конструкторе проектов (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)убедитесь, что **параметр Infer** имеет значение **On**.

## <a name="add-an-in-memory-data-source"></a>Добавление источника данных In-Memory

Источником данных для запросов в этом пошаговом руководстве является список `Student` объектов. Каждый `Student` объект содержит имя, фамилию, класс year и академический рейтинг в тексте учащегося.

### <a name="to-add-the-data-source"></a>Добавление источника данных

- Определите `Student` класс и создайте список экземпляров класса.

  > [!IMPORTANT]
  > Код, необходимый для определения `Student` класса и создания списка, используемого в примерах пошагового руководства, приведен в разделе [Практическое руководство. Создание списка элементов](how-to-create-a-list-of-items.md). Вы можете скопировать его из него и вставить в проект. Новый код заменяет код, который отображался при создании проекта.

### <a name="to-add-a-new-student-to-the-students-list"></a>Добавление нового учащегося в список учащихся

- Следуйте шаблону в `getStudents` методе, чтобы добавить в список другой экземпляр `Student` класса. При добавлении учащегося будут представлены инициализаторы объектов. Дополнительные сведения см. в разделе [инициализаторы объектов: именованные и анонимные типы](../../language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).

## <a name="create-a-query"></a>Создание запроса

При выполнении запроса, добавленного в этом разделе, создается список учащихся, чьи учебные заведения помещают в десять первых. Поскольку запрос выбирает полный `Student` объект каждый раз, тип результата запроса — `IEnumerable(Of Student)` . Однако тип запроса обычно не указывается в определениях запросов. Вместо этого компилятор использует определение локального типа для определения типа. Дополнительные сведения см. в разделе [определение локального типа](../../language-features/variables/local-type-inference.md). Переменная диапазона запроса, выступает в `currentStudent` качестве ссылки на каждый `Student` экземпляр в источнике, `students` предоставляя доступ к свойствам каждого объекта в `students` .

### <a name="to-create-a-simple-query"></a>Создание простого запроса

1. Найдите место в `Main` методе проекта, который помечен следующим образом:

    [!code-vb[VbLINQWalkthrough#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#1)]

    Скопируйте приведенный ниже код и вставьте его в.

    [!code-vb[VbLINQWalkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#2)]

2. Наведите указатель мыши на `studentQuery` код, чтобы убедиться, что назначенный компилятором тип имеет значение `IEnumerable(Of Student)` .

## <a name="run-the-query"></a>Выполнение запроса

Переменная `studentQuery` содержит определение запроса, а не результаты выполнения запроса. Типичный механизм выполнения запроса — `For Each` цикл. Доступ к каждому элементу в возвращаемой последовательности осуществляется через переменную итерации цикла. Дополнительные сведения о выполнении запросов см. [в разделе Написание первого запроса LINQ](writing-your-first-linq-query.md).

### <a name="to-run-the-query"></a>Выполнение запроса

1. Добавьте следующий `For Each` цикл под запросом в проекте.

    [!code-vb[VbLINQWalkthrough#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#3)]

2. Наведите указатель мыши на переменную управления циклом, `studentRecord` чтобы увидеть ее тип данных. Тип `studentRecord` выводится `Student` как, так как `studentQuery` возвращает коллекцию `Student` экземпляров.

3. Выполните сборку и запустите приложение, нажав клавиши CTRL + F5. Обратите внимание на результаты в окне консоли.

## <a name="modify-the-query"></a>Изменение запроса

Проще проверять результаты запроса, если они находятся в указанном порядке. Возвращаемую последовательность можно отсортировать на основе любого доступного поля.

### <a name="to-order-the-results"></a>Упорядочение результатов

1. Добавьте следующее `Order By` предложение между `Where` оператором и `Select` инструкцией запроса. `Order By`Предложение упорядочивает результаты в алфавитном порядке от A до Z в соответствии с фамилией каждого учащегося.

    ```vb
    Order By currentStudent.Last Ascending
    ```

2. Чтобы упорядочить по фамилии, а затем по имени, добавьте в запрос оба поля:

    ```vb
    Order By currentStudent.Last Ascending, currentStudent.First Ascending
    ```

    Можно также указать `Descending` Порядок от я до а.

3. Выполните сборку и запустите приложение, нажав клавиши CTRL + F5. Обратите внимание на результаты в окне консоли.

### <a name="to-introduce-a-local-identifier"></a>Введение локального идентификатора

1. Добавьте код в этом разделе, чтобы ввести локальный идентификатор в выражение запроса. Локальный идентификатор будет содержать промежуточный результат. В следующем примере `name` — это идентификатор, содержащий объединение имени и фамилии учащегося. Локальный идентификатор можно использовать для удобства или повысить производительность, сохранив результаты выражения, которые в противном случае будут вычисляться несколько раз.

    [!code-vb[VbLINQWalkthrough#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#4)]

2. Выполните сборку и запустите приложение, нажав клавиши CTRL + F5. Обратите внимание на результаты в окне консоли.

### <a name="to-project-one-field-in-the-select-clause"></a>Проецирование одного поля в предложении SELECT

1. Добавьте запрос и `For Each` цикл из этого раздела, чтобы создать запрос, который создает последовательность, элементы которой отличаются от элементов в источнике. В следующем примере источником является коллекция `Student` объектов, но возвращается только один элемент каждого объекта: имена учащихся, чье фамилия — Гарсиа. Так как `currentStudent.First` является строкой, тип данных последовательности, возвращаемой `studentQuery3` , — это `IEnumerable(Of String)` последовательность строк. Как и в предыдущих примерах, для определения типа данных для `studentQuery3` компилятора необходимо определить, используя вывод локального типа.

    [!code-vb[VbLINQWalkthrough#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#5)]

2. Наведите указатель мыши на `studentQuery3` код, чтобы убедиться, что назначенный тип имеет значение `IEnumerable(Of String)` .

3. Выполните сборку и запустите приложение, нажав клавиши CTRL + F5. Обратите внимание на результаты в окне консоли.

### <a name="to-create-an-anonymous-type-in-the-select-clause"></a>Создание анонимного типа в предложении SELECT

1. Добавьте код из этого раздела, чтобы увидеть, как анонимные типы используются в запросах. Они используются в запросах, если требуется вернуть несколько полей из источника данных, а не полные записи ( `currentStudent` записи в предыдущих примерах) или отдельные поля ( `First` в предыдущем разделе). Вместо определения нового именованного типа, содержащего поля, которые необходимо включить в результат, необходимо указать поля в `Select` предложении, и компилятор создаст анонимный тип с этими полями в качестве свойств. Дополнительные сведения см. в статье [Анонимные типы](../../language-features/objects-and-classes/anonymous-types.md).

    В следующем примере создается запрос, который возвращает имя и звание старших званий, чьи учебные заведения находятся в диапазоне от 1 до 10 в порядке академических званий. В этом примере тип `studentQuery4` должен быть определен, поскольку `Select` предложение возвращает экземпляр анонимного типа, а анонимный тип не имеет имени.

    [!code-vb[VbLINQWalkthrough#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#6)]

2. Выполните сборку и запустите приложение, нажав клавиши CTRL + F5. Обратите внимание на результаты в окне консоли.

## <a name="additional-examples"></a>Дополнительные примеры

Теперь, когда вы понимаете основы, ниже приведен список дополнительных примеров для демонстрации гибкости и возможностей запросов LINQ. Каждому примеру предшествует краткое описание того, что он делает. Наведите указатель мыши на переменную результата запроса для каждого запроса, чтобы увидеть выведенный тип. `For Each`Для получения результатов используйте цикл.

[!code-vb[VbLINQWalkthrough#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#7)]

## <a name="additional-information"></a>Дополнительные сведения

После ознакомления с основными понятиями работы с запросами вы можете ознакомиться с документацией и примерами для конкретного типа поставщика LINQ, который вас интересует:

- [LINQ to Objects](linq-to-objects.md)

- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)

- [LINQ to XML](../../../../standard/linq/linq-xml-overview.md)

- [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)

## <a name="see-also"></a>См. также раздел

- [LINQ (Visual Basic)](index.md)
- [Приступая к работе с LINQ в Visual Basic](getting-started-with-linq.md)
- [Вывод локального типа](../../language-features/variables/local-type-inference.md)
- [Инициализаторы объектов: именованные и анонимные типы](../../language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Анонимные типы](../../language-features/objects-and-classes/anonymous-types.md)
- [Introduction to LINQ in Visual Basic](../../language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [LINQ](../../language-features/linq/index.md)
- [Запросы](../../../language-reference/queries/index.md)
