---
title: Использование широковещательных переменных в .NET для Apache Spark
description: Сведения об использовании широковещательных переменных в .NET для приложений Apache Spark.
ms.author: nidutta
author: Niharikadutta
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: ca6dab01cbd639594da0b51f145272a9a150e93c
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "94687757"
---
# <a name="use-broadcast-variables-in-net-for-apache-spark"></a><span data-ttu-id="2899d-103">Использование широковещательных переменных в .NET для Apache Spark</span><span class="sxs-lookup"><span data-stu-id="2899d-103">Use broadcast variables in .NET for Apache Spark</span></span>

<span data-ttu-id="2899d-104">Из этой статьи вы узнаете, как использовать широковещательные переменные в .NET для Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="2899d-104">In this article, you learn how to use broadcast variables in .NET for Apache Spark.</span></span> <span data-ttu-id="2899d-105">Механизм [широковещательных переменных в Apache Spark](https://spark.apache.org/docs/2.2.0/rdd-programming-guide.html#broadcast-variables) обеспечивает совместное использование исполнителями переменных, которые предназначены исключительно для чтения.</span><span class="sxs-lookup"><span data-stu-id="2899d-105">[Broadcast variables in Apache Spark](https://spark.apache.org/docs/2.2.0/rdd-programming-guide.html#broadcast-variables) are mechanisms for sharing variables across executors that are meant to be read-only.</span></span> <span data-ttu-id="2899d-106">При таком подходе доступные только для чтения широковещательные переменные кэшируются на каждом компьютере, что позволяет не передавать их копии вместе с задачами.</span><span class="sxs-lookup"><span data-stu-id="2899d-106">Broadcast variables allow you to keep a read-only variable cached on each machine rather than shipping a copy of it with tasks.</span></span> <span data-ttu-id="2899d-107">Применение широковещательных переменных позволяет эффективно передавать на каждый узел крупные наборы входных данных.</span><span class="sxs-lookup"><span data-stu-id="2899d-107">You can use broadcast variables to give every node a copy of a large input dataset in an efficient manner.</span></span>

<span data-ttu-id="2899d-108">Поскольку при использовании широковещательных переменных данные передаются только один раз, это позволяет добиться лучшей производительности по сравнению с локальными переменными, которые передаются исполнителям вместе с каждой задачей.</span><span class="sxs-lookup"><span data-stu-id="2899d-108">Because the data is sent only once, broadcast variables have performance benefits when compared to local variables that are shipped to the executors with each task.</span></span> <span data-ttu-id="2899d-109">Более подробные сведения о широковещательных переменных и причинах их применения см. в [официальной документации](https://spark.apache.org/docs/2.2.0/rdd-programming-guide.html#broadcast-variables).</span><span class="sxs-lookup"><span data-stu-id="2899d-109">Refer to the [official broadcast variable documentation](https://spark.apache.org/docs/2.2.0/rdd-programming-guide.html#broadcast-variables) to get a deeper understanding of broadcast variables and why they are used.</span></span>

## <a name="create-broadcast-variables"></a><span data-ttu-id="2899d-110">Создание широковещательных переменных</span><span class="sxs-lookup"><span data-stu-id="2899d-110">Create broadcast variables</span></span>

<span data-ttu-id="2899d-111">Чтобы создать широковещательную переменную, вызовите метод `SparkContext.Broadcast(v)` для любой переменной `v`.</span><span class="sxs-lookup"><span data-stu-id="2899d-111">To create a broadcast variable, call `SparkContext.Broadcast(v)` for any variable `v`.</span></span> <span data-ttu-id="2899d-112">Широковещательная переменная представляет собой оболочку для переменной `v`. Чтобы получить доступ к ее значению, можно вызвать метод `Value()`.</span><span class="sxs-lookup"><span data-stu-id="2899d-112">The broadcast variable is a wrapper around the variable `v`, and its value can be accessed by calling the `Value()` method.</span></span>

<span data-ttu-id="2899d-113">В следующем фрагменте кода создается строковая переменная `v`, после чего создается широковещательная переменная `bv` посредством вызова метода `SparkContext.Broadcast(v)`.</span><span class="sxs-lookup"><span data-stu-id="2899d-113">In the following code snippet, a string variable `v` is created, and a broadcast variable `bv` is created when `SparkContext.Broadcast(v)`is called.</span></span> <span data-ttu-id="2899d-114">Обратите внимание, что параметр типа `Broadcast` (строка) совпадает с типом транслируемой переменной.</span><span class="sxs-lookup"><span data-stu-id="2899d-114">Notice the type parameter for `Broadcast`, string, matches the type of the variable being broadcasted.</span></span> <span data-ttu-id="2899d-115">Определяемая пользователем функция возвращает значение `bv`.</span><span class="sxs-lookup"><span data-stu-id="2899d-115">The user-defined function (UDF) returns the value of `bv`.</span></span>

```csharp
string v = "Variable to be broadcasted";
Broadcast<string> bv = SparkContext.Broadcast(v);

Func<Column, Column> udf = Udf<string, string>(
    str => $"{str}: {bv.Value()}");
```

## <a name="delete-broadcast-variables"></a><span data-ttu-id="2899d-116">Удаление широковещательных переменных</span><span class="sxs-lookup"><span data-stu-id="2899d-116">Delete broadcast variables</span></span>

<span data-ttu-id="2899d-117">Широковещательную переменную можно удалить из всех исполнителей, вызвав метод `Destroy()`.</span><span class="sxs-lookup"><span data-stu-id="2899d-117">The broadcast variable can be deleted from all executors by calling the `Destroy()` method.</span></span>

```csharp
bv.Destroy();
```

<span data-ttu-id="2899d-118">Поскольку метод `Destroy()` удаляет все данные и метаданные, связанные с широковещательной переменной, его следует использовать с осторожностью.</span><span class="sxs-lookup"><span data-stu-id="2899d-118">`Destroy()` deletes all data and metadata related to the broadcast variable and should be used with caution.</span></span> <span data-ttu-id="2899d-119">После уничтожения широковещательной переменной ее нельзя использовать повторно.</span><span class="sxs-lookup"><span data-stu-id="2899d-119">Once a broadcast variable is destroyed, it can't be used again.</span></span>

## <a name="limit-broadcast-variable-scope-in-udfs"></a><span data-ttu-id="2899d-120">Ограничение области действия широковещательных переменных в определяемых пользователем функциях</span><span class="sxs-lookup"><span data-stu-id="2899d-120">Limit broadcast variable scope in UDFs</span></span>

<span data-ttu-id="2899d-121">При использовании широковещательных переменных в определяемых пользователем функциях необходимо ограничивать область действия таких переменных самой функцией, которая ссылается на переменную.</span><span class="sxs-lookup"><span data-stu-id="2899d-121">When you use broadcast variables in UDFs, you need to limit the scope of the variable to only the UDF that is referencing the variable.</span></span> <span data-ttu-id="2899d-122">Подробнее это требование описывается в [руководстве по работе с определяемыми пользователем функциями](udf-guide.md).</span><span class="sxs-lookup"><span data-stu-id="2899d-122">The [guide to using UDFs](udf-guide.md) describes this phenomenon in detail.</span></span> <span data-ttu-id="2899d-123">Область действия особенно важна при вызове метода `Destroy()` для широковещательной переменной.</span><span class="sxs-lookup"><span data-stu-id="2899d-123">Scope is especially crucial when you call `Destroy()` on the broadcast variable.</span></span>

<span data-ttu-id="2899d-124">Если уничтоженная широковещательная переменная по-прежнему видна или доступна из других определяемых пользователем функций, во всех этих функциях она выбирается для сериализации, даже если они не ссылаются на эту переменную.</span><span class="sxs-lookup"><span data-stu-id="2899d-124">If the broadcast variable that has been destroyed is visible to or accessible from other UDFs, it gets picked up for serialization by all of the UDFs, even if it is not being referenced by them.</span></span> <span data-ttu-id="2899d-125">.NET для Apache Spark не может сериализовать уничтоженную широковещательную переменную, что приводит к ошибке.</span><span class="sxs-lookup"><span data-stu-id="2899d-125">.NET for Apache Spark is unable to serialize the destroyed broadcast variable, which results in an error.</span></span> <span data-ttu-id="2899d-126">Эта ошибка показана в следующем фрагменте кода.</span><span class="sxs-lookup"><span data-stu-id="2899d-126">The following code snippet demonstrates this error:</span></span>

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

<span data-ttu-id="2899d-127">В следующем фрагменте кода показано, как гарантировать, что уничтожение `bv` не повлияет на `udf2` в связи с непредвиденным поведением сериализации.</span><span class="sxs-lookup"><span data-stu-id="2899d-127">The following code snippet demonstrates how to ensure that destroying `bv` doesn't affect `udf2` because of an unexpected serialization behavior:</span></span>

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

## <a name="faqs"></a><span data-ttu-id="2899d-128">Часто задаваемые вопросы</span><span class="sxs-lookup"><span data-stu-id="2899d-128">FAQs</span></span>

<span data-ttu-id="2899d-129">**Почему широковещательные переменные не работают с .NET Interactive?**</span><span class="sxs-lookup"><span data-stu-id="2899d-129">**Why don't Broadcast Variables work with .NET Interactive?**</span></span>  
<span data-ttu-id="2899d-130">Причины, по которым широковещательные переменные не работают с интерактивными сценариями, обусловлены тем, что в NET Interactive каждый объект, определенный в ячейке с помощью класса отправки ячейки и поэтому не помеченный как сериализуемый, завершается с тем же исключением, как показано выше.</span><span class="sxs-lookup"><span data-stu-id="2899d-130">Broadcast variables don't work with interactive scenarios because of .NET interactive's design of appending each object defined in a cell with its cell submission class, which since is not marked serializable, fails with the same exception as shown previously.</span></span> <span data-ttu-id="2899d-131">Чтобы получить дополнительные сведения, прочитайте [эту статью](dotnet-interactive-udf-issue.md).</span><span class="sxs-lookup"><span data-stu-id="2899d-131">For more information, please check out [this article](dotnet-interactive-udf-issue.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="2899d-132">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="2899d-132">Next steps</span></span>

* [<span data-ttu-id="2899d-133">Начало работы с .NET для Apache Spark</span><span class="sxs-lookup"><span data-stu-id="2899d-133">Get started with .NET for Apache Spark</span></span>](../tutorials/get-started.md)
* [<span data-ttu-id="2899d-134">Отладка приложения .NET для Apache Spark в Windows</span><span class="sxs-lookup"><span data-stu-id="2899d-134">Debug a .NET for Apache Spark application on Windows</span></span>](debug.md)
* [<span data-ttu-id="2899d-135">Развертывание рабочей роли и двоичных файлов пользовательских функций .NET для Apache Spark</span><span class="sxs-lookup"><span data-stu-id="2899d-135">Deploy .NET for Apache Spark worker and user-defined function binaries</span></span>](deploy-worker-udf-binaries.md)
