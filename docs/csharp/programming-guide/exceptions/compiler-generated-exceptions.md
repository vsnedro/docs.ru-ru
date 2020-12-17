---
title: Руководство по программированию на C#. Исключения, создаваемые компилятором
description: Сведения об исключениях, создаваемых компилятором. Просмотрите список автоматически создаваемых исключений и условия возникновения ошибок.
ms.date: 12/09/2020
helpviewer_keywords:
- exceptions [C#], compiler-generated
ms.assetid: 53b52f97-b366-4ed7-b05b-9eb78096b7f9
ms.openlocfilehash: 43bacbb1025bc0af3a5f21979315b3d1b0d61066
ms.sourcegitcommit: 9b877e160c326577e8aa5ead22a937110d80fa44
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2020
ms.locfileid: "97110355"
---
# <a name="compiler-generated-exceptions-c-programming-guide"></a>Исключения, создаваемые компилятором (Руководство по программированию в C#)

Некоторые исключения создаются средой выполнения .NET автоматически в случае сбоя основных операций. В следующей таблице перечислены эти исключения и условия возникновения ошибок.

|Исключение|Описание|
|---------------|-----------------|
|<xref:System.ArithmeticException>|Базовый класс для исключений, которые возникают при выполнении арифметических операций, таких как <xref:System.DivideByZeroException> и <xref:System.OverflowException>.|
|<xref:System.ArrayTypeMismatchException>|Возникает, когда массив не может сохранить данный элемент, поскольку фактический тип элемента несовместим с фактическим типом массива.|
|<xref:System.DivideByZeroException>|Возникает при попытке деления целого значения на ноль.|
|<xref:System.IndexOutOfRangeException>|Возникает при попытке индексирования массива, если индекс меньше нуля или выходит за границы массива.|
|<xref:System.InvalidCastException>|Возникает, если явное преобразование из базового типа в интерфейс или в производный тип завершается ошибкой во время выполнения.|
|<xref:System.NullReferenceException>|Возникает при попытке сослаться на объект, имеющий значение [null](../../language-reference/keywords/null.md).|
|<xref:System.OutOfMemoryException>|Возникает, если попытка распределения памяти с помощью оператора [new](../../language-reference/operators/new-operator.md) завершается ошибкой. Это исключение указывает, что ресурсы памяти, доступные для среды CLR, исчерпаны.|
|<xref:System.OverflowException>|Возникает при переполнении арифметической операции в контексте `checked`.|
|<xref:System.StackOverflowException>|Возникает, когда чрезмерное количество ожидающих вызовов метода истощает стек выполнения; обычно это указывает на крайне глубокую или бесконечную рекурсию.|
|<xref:System.TypeInitializationException>|Возникает, когда статический конструктор создает исключение, а совместимого предложения `catch` для его захвата нет.|

## <a name="see-also"></a>См. также

- [try-catch](../../language-reference/keywords/try-catch.md)
- [try-finally](../../language-reference/keywords/try-finally.md)
- [try-catch-finally](../../language-reference/keywords/try-catch-finally.md)
