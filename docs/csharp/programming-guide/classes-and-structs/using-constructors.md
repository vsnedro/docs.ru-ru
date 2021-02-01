---
title: Руководство по программированию на C#. Использование конструкторов
description: В этом примере показано, как создать экземпляр класса с помощью оператора new в C#. Простой конструктор вызывается после выделения памяти новому объекту.
ms.date: 07/20/2015
helpviewer_keywords:
- constructors [C#], about constructors
ms.assetid: 464253b2-fd5d-469a-836d-df0fdf2a43f7
ms.openlocfilehash: 161c243f16f6705fa8fcf79360f92a74e4d0b27b
ms.sourcegitcommit: 8299abfbd5c49b596d61f1e4d09bc6b8ba055b36
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/27/2021
ms.locfileid: "98899260"
---
# <a name="using-constructors-c-programming-guide"></a>Использование конструкторов (Руководство по программированию на C#)

Каждый раз, когда создается [класс](../../language-reference/keywords/class.md) или [структура](../../language-reference/builtin-types/struct.md), вызывается конструктор. Конструкторы имеют имя, совпадающее с именем класса или структуры, и обычно инициализируют члены данных нового объекта.  
  
 В следующем примере класс с именем `Taxi` определяется с помощью простого конструктора. Затем оператор [new](../../language-reference/operators/new-operator.md) создает экземпляр этого класса. Конструктор `Taxi` вызывается оператором `new` сразу после того, как новому объекту будет выделена память.  
  
 [!code-csharp[TaxiExample#1](snippets/using-constructors/Program.cs#1)]
  
 Конструктор, который не принимает никаких параметров, называется *конструктором без параметров*. Конструкторы без параметров вызываются всякий раз, когда создается экземпляр объекта с помощью оператора `new`, а аргументы в `new` не передаются. Дополнительные сведения см. в разделе [Конструкторы экземпляров](./instance-constructors.md).  
  
 Если класс не является [статическим](../../language-reference/keywords/static.md), компилятор C# выделяет классам без конструкторов открытый конструктор без параметров, позволяющий создавать экземпляры классов. Дополнительные сведения см. в статье [Статические классы и члены статических классов](./static-classes-and-static-class-members.md).  
  
 Создание экземпляров класса можно запретить, сделав конструктор закрытым, следующим образом:  
  
 [!code-csharp[PrivateConstructor#2](snippets/using-constructors/Program.cs#2)]
  
 Дополнительные сведения см. в разделе [Закрытые конструкторы](./private-constructors.md).  
  
 Конструкторы для типов [struct](../../language-reference/builtin-types/struct.md) похожи на конструкторы классов, однако `structs` не может содержать явный конструктор без параметров, так как он предоставляется компилятором автоматически. Этот конструктор инициализирует каждое поле в `struct` со [значением по умолчанию](../../language-reference/builtin-types/default-values.md). При этом конструктор без параметров вызывается только в том случае, если экземпляр `struct` создается с помощью переменной `new`. Например, в этом коде конструктор без параметров используется для <xref:System.Int32> — это обеспечивает инициализацию целого числа:  
  
```csharp  
int i = new int();  
Console.WriteLine(i);  
```  
  
 В то же время следующий код вызывает ошибку компилятора, поскольку не использует `new`, и потому, что использует не инициализированный объект:  
  
```csharp  
int i;  
Console.WriteLine(i);  
```  
  
 Кроме того, объекты на основе `structs` (включая все встроенные числовые типы) можно инициализировать или назначить, а затем использовать, как в следующем примере:  
  
```csharp  
int a = 44;  // Initialize the value type...  
int b;  
b = 33;      // Or assign it before using it.  
Console.WriteLine("{0}, {1}", a, b);  
```  
  
 В связи с этим вызывать конструктор без параметров для типа значения необязательно.  
  
 Оба класса и `structs` могут определять конструкторы, принимающие параметры. Конструкторы, принимающие параметры, необходимо вызывать с помощью оператора `new` или [base](../../language-reference/keywords/base.md). Классы и `structs` могут определять также несколько конструкторов; для определения конструктора без параметров ни один их них не требуется. Пример:  
  
 [!code-csharp[EmployeeExample#3](snippets/using-constructors/Program.cs#3)]
  
 Этот класс можно создать, воспользовавшись одним из следующих операторов:  
  
 [!code-csharp[InstantiatingEmployeeConstructors#4](snippets/using-constructors/Program.cs#4)]
  
 Конструктор может использовать ключевое слово `base` для вызова конструктора базового класса. Пример:  
  
 [!code-csharp[ManagerInheritingEmployee#5](snippets/using-constructors/Program.cs#5)]
  
 В этом примере конструктор базового класса вызывается перед выполнением соответствующего ему блока. Ключевое слово `base` можно использовать как с параметрами, так и без них. Любые параметры для конструктора можно использовать как параметры для `base` или как часть выражения. Дополнительные сведения см. в разделе [base](../../language-reference/keywords/base.md).  
  
 В производном классе, если конструктор базового класса не вызывается явным образом с помощью ключевого слова `base`, конструктор без параметров, если он существует, вызывается неявно. Это означает, что следующие объявления конструкторов действуют одинаково:  
  
 [!code-csharp[ManagerImplicitlyCallingParameterlessBaseConstructor#6](snippets/using-constructors/Program.cs#6)]
  
 [!code-csharp[ManagerExplicitlyCallingParameterlessBaseConstructor#7](snippets/using-constructors/Program.cs#7)]
  
 Если базовый класс не предлагает конструктор без параметров, производный класс должен явно вызвать конструктор базового класса с помощью `base`.  
  
 Конструктор может вызывать другой конструктор в том же объекте с помощью ключевого слова [this](../../language-reference/keywords/this.md). Как и `base`, `this` можно использовать с параметрами или без, а все параметры в конструкторе доступны как параметры `this` или как часть выражения. Например, второй конструктор в предыдущем примере можно переписать, используя `this`:  
  
 [!code-csharp[EmployeeCallingConstructorInSameClass#8](snippets/using-constructors/Program.cs#8)]
  
 Применение ключевого слова `this` в приведенном выше примере привело к вызову конструктора:  
  
 [!code-csharp[ConstructorBeingCalledByThisKeyword#9](snippets/using-constructors/Program.cs#9)]
  
 Конструкторы могут иметь пометку [public](../../language-reference/keywords/public.md), [private](../../language-reference/keywords/private.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md) или [private protected](../../language-reference/keywords/private-protected.md). Эти модификаторы доступа определяют, каким образом пользователи класса смогут создавать класс. Дополнительные сведения см. в статье [Модификаторы доступа](./access-modifiers.md).  
  
 Конструктор можно объявить статическим, используя ключевое слово [static](../../language-reference/keywords/static.md). Статические конструкторы вызываются автоматически непосредственно перед доступом к статическим полям и обычно используются для инициализации членов статического класса. Дополнительные сведения см. в разделе [Статические конструкторы](./static-constructors.md).  
  
## <a name="c-language-specification"></a>Спецификация языка C#  

Дополнительные сведения см. в разделах [Конструкторы экземпляров](~/_csharplang/spec/classes.md#instance-constructors) и [Статические конструкторы](~/_csharplang/spec/classes.md#static-constructors) в [Спецификации языка C#](/dotnet/csharp/language-reference/language-specification/introduction). Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Классы и структуры](./index.md)
- [Конструкторы](./constructors.md)
- [Методы завершения](./destructors.md)
