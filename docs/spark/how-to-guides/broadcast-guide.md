---
title: Использование широковещательных переменных в .NET для Apache Spark
description: Сведения об использовании широковещательных переменных в .NET для приложений Apache Spark.
ms.date: 06/25/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: d86b160855cc4d3f3a6502f5606d4766b7c06aa0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617860"
---
# <a name="use-broadcast-variables-in-net-for-apache-spark"></a>Использование широковещательных переменных в .NET для Apache Spark

Из этой статьи вы узнаете, как использовать широковещательные переменные в .NET для Apache Spark. Механизм [широковещательных переменных в Apache Spark](https://spark.apache.org/docs/2.2.0/rdd-programming-guide.html#broadcast-variables) обеспечивает совместное использование исполнителями переменных, которые предназначены исключительно для чтения. При таком подходе доступные только для чтения широковещательные переменные кэшируются на каждом компьютере, что позволяет не передавать их копии вместе с задачами. Применение широковещательных переменных позволяет эффективно передавать на каждый узел крупные наборы входных данных.

Поскольку при использовании широковещательных переменных данные передаются только один раз, это позволяет добиться лучшей производительности по сравнению с локальными переменными, которые передаются исполнителям вместе с каждой задачей. Более подробные сведения о широковещательных переменных и причинах их применения см. в [официальной документации](https://spark.apache.org/docs/2.2.0/rdd-programming-guide.html#broadcast-variables).

[!INCLUDE [spark-preview-note](../../../includes/spark-preview-note.md)]

## <a name="create-broadcast-variables"></a>Создание широковещательных переменных

Чтобы создать широковещательную переменную, вызовите метод `SparkContext.Broadcast(v)` для любой переменной `v`. Широковещательная переменная представляет собой оболочку для переменной `v`. Чтобы получить доступ к ее значению, можно вызвать метод `Value()`.

В следующем фрагменте кода создается строковая переменная `v`, после чего создается широковещательная переменная `bv` посредством вызова метода `SparkContext.Broadcast(v)`. Обратите внимание, что параметр типа `Broadcast` (строка) совпадает с типом транслируемой переменной. Определяемая пользователем функция возвращает значение `bv`.

```csharp
string v = "Variable to be broadcasted";
Broadcast<string> bv = SparkContext.Broadcast(v);

Func<Column, Column> udf = Udf<string, string>(
    str => $"{str}: {bv.Value()}");
```

## <a name="delete-broadcast-variables"></a>Удаление широковещательных переменных

Широковещательную переменную можно удалить из всех исполнителей, вызвав метод `Destroy()`.

```csharp
bv.Destroy();
```

Поскольку метод `Destroy()` удаляет все данные и метаданные, связанные с широковещательной переменной, его следует использовать с осторожностью. После уничтожения широковещательной переменной ее нельзя использовать повторно.

## <a name="limit-broadcast-variable-scope-in-udfs"></a>Ограничение области действия широковещательных переменных в определяемых пользователем функциях

При использовании широковещательных переменных в определяемых пользователем функциях необходимо ограничивать область действия таких переменных самой функцией, которая ссылается на переменную. Подробнее это требование описывается в [руководстве по работе с определяемыми пользователем функциями](udf-guide.md). Область действия особенно важна при вызове метода `Destroy()` для широковещательной переменной.

Если уничтоженная широковещательная переменная по-прежнему видна или доступна из других определяемых пользователем функций, во всех этих функциях она выбирается для сериализации, даже если они не ссылаются на эту переменную. .NET для Apache Spark не может сериализовать уничтоженную широковещательную переменную, что приводит к ошибке. Эта ошибка показана в следующем фрагменте кода.

```csharp
string v = "Variable to be broadcasted";
Broadcast<string> bv = SparkContext.Broadcast(v);

// Using the broadcast variable in a UDF:
Func<Column, Column> udf1 = Udf<string, string>(
    str => $"{str}: {bv.Value()}");

// Destroying bv
bv.Destroy();

// Calling udf1 after destroying bv throws the following expected exception:
// org.apache.spark.SparkException: Attempted to use Broadcast(0) after it was destroyed
df.Select(udf1(df["_1"])).Show();

// Different UDF udf2 that is not referencing bv
Func<Column, Column> udf2 = Udf<string, string>(
    str => $"{str}: not referencing broadcast variable");

// Calling udf2 throws the following (unexpected) exception:
// [Error] [JvmBridge] org.apache.spark.SparkException: Task not serializable
df.Select(udf2(df["_1"])).Show();
```

В следующем фрагменте кода показано, как гарантировать, что уничтожение `bv` не повлияет на `udf2` в связи с непредвиденным поведением сериализации.

```csharp
string v = "Variable to be broadcasted";
// Restricting the visibility of bv to only the UDF referencing it
{
    Broadcast<string> bv = SparkContext.Broadcast(v);

    // Using the broadcast variable in a UDF:
    Func<Column, Column> udf1 = Udf<string, string>(
        str => $"{str}: {bv.Value()}");

    // Destroying bv
    bv.Destroy();
}

// Different UDF udf2 that is not referencing bv
Func<Column, Column> udf2 = Udf<string, string>(
    str => $"{str}: not referencing broadcast variable");

// Calling udf2 works fine as expected
df.Select(udf2(df["_1"])).Show();
```

## <a name="next-steps"></a>Следующие шаги

* [Начало работы с .NET для Apache Spark](../tutorials/get-started.md)
* [Отладка приложения .NET для Apache Spark в Windows](debug.md)
* [Развертывание рабочей роли и двоичных файлов пользовательских функций .NET для Apache Spark](deploy-worker-udf-binaries.md)
