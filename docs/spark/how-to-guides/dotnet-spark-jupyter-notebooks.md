---
title: Использование записных книжек Jupyter
titleSuffix: .NET for Apache Spark
description: Использование .NET для Apache Spark в интерактивных средах, таких как Jupyter Notebook, Jupyter Lab или Visual Studio Code (VS Code)
ms.author: luquinta
author: luisquintanilla
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc, how-to
ms.openlocfilehash: 9c0e713731b5e2ad742bdd257a99f9029f244363
ms.sourcegitcommit: 3a8f1979a98c6c19217a1930e0af5908988eb8ba
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2021
ms.locfileid: "98536116"
---
# <a name="use-net-for-apache-spark-in-jupyter-notebooks"></a>Использование .NET для Apache Spark в записных книжках Jupyter

Из этой статьи вы узнаете, как запускать задания .NET для Apache Spark в интерактивном режиме в Jupyter Notebook и Visual Studio Code (VS Code) с помощью .NET Interactive.

## <a name="about-jupyter"></a>Сведения о Jupyter

[Jupyter](https://jupyter.org/) — это кроссплатформенная вычислительная среда с открытым исходным кодом, которая позволяет пользователям создавать прототипы и разрабатывать приложения в интерактивном режиме. Для взаимодействия с Jupyter можно использовать широкий набор интерфейсов, таких как Jupyter Notebook, Jupyter Lab и VS Code.

В контексте .NET, [.NET Interactive](https://github.com/dotnet/interactive), глобальное средство .NET Core, предоставляет ядро для написания кода .NET (C#/F#) в интерактивных вычислительных средах, таких как Jupyter Notebook.

## <a name="prerequisites"></a>Предварительные требования

- [Пакет SDK для .NET Core 3.1](../../core/install/index.yml)
- [Apache Spark](https://spark.apache.org/downloads.html)
- [Рабочая роль Apache Spark .NET](https://github.com/dotnet/spark/releases)

Дополнительные сведения о настройке среды .NET для Apache Spark см. в [руководстве по началу работы](../tutorials/get-started.md).

## <a name="prepare-environment"></a>Подготовка среды

Для работы с записными книжками Jupyter Notebook потребуется две вещи.

1. Установите [глобальное средство .NET Interactive](https://github.com/dotnet/interactive/blob/main/docs/NotebooksLocalExperience.md).
1. Скачайте пакет NuGet `Microsoft.Spark`.
    1. Перейдите на страницу пакета NuGet [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/).

        > [!IMPORTANT]
        > По умолчанию скачивается последняя версия пакета. **Убедитесь, что загружаемая версия совпадает с версией рабочей роли .NET Apache Spark.**

    1. В области **Сведения** выберите **Скачать пакет**, чтобы скачать последнюю версию пакета. Имя пакета аналогично *microsoft.spark.[PACKAGE-VERSION].nupkg*.
    1. Распакуйте скачанный пакет. В распакованном каталоге должен содержаться подкаталог *jars*. Запишите путь, так как он потребуется позже.

## <a name="start-net-for-apache-spark"></a>Запуск .NET для Apache Spark

Выполните следующую команду, чтобы запустить .NET для Apache Spark в режиме отладки. Команда `spark-submit` запускает процесс и ожидает подключения от [SparkSession](xref:Microsoft.Spark.Sql.SparkSession). Обязательно укажите путь к `microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar` для соответствующей используемой версии .NET для Apache Spark.

**Ubuntu**

```bash
spark-submit \
    --class org.apache.spark.deploy.dotnet.DotnetRunner \
    --master local \
    <path-to-microsoft-spark-jar> \
    debug
```

**Windows**

```cmd
spark-submit ^
    --class org.apache.spark.deploy.dotnet.DotnetRunner ^
    --master local ^
    <path-to-microsoft-spark-jar> ^
    debug
```

## <a name="create-a-notebook"></a>Создание записной книжки

Для взаимодействия с Jupyter можно использовать различные интерфейсы. Для интерфейса на основе браузера используйте Jupyter Notebook или Jupyter Lab. Для работы с локальным редактором используйте VS Code.

### <a name="jupyter-notebooks--jupyter-lab"></a>Jupyter Notebook и Jupyter Lab

1. В другой командной строке запустите Jupyter Notebook или Jupyter Lab с помощью одной из следующих команд:

    **Записная книжка Jupyter**

    ```bash
    jupyter notebook
    ```

    **Jupyter Lab**

    ```bash
    jupyter lab
    ```

    Эти команды запускают окно браузера с интерфейсом Jupyter Notebook или Jupyter Lab.

1. В браузере создайте новую записную книжку.

    **Записная книжка Jupyter**

    Выберите **Создать > .NET (C#)** или **Создать > .NET (F#)**

    **Jupyter Lab**

    В окне средства запуска выберите **.NET (C#)** или **.NET (F#).**

### <a name="visual-studio-code-preview"></a>Visual Studio Code (предварительная версия)

> [!IMPORTANT]
> Чтобы использовать Jupyter Notebook в VS Code, необходимо установить следующее:
>
>- [VS Code Insiders](https://code.visualstudio.com/insiders/)
>- [Расширение Notebooks для .NET Interactive](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.dotnet-interactive-vscode)

1. Откройте VS Code.
1. Откройте палитру команд **Вид > Палитра команд**.

    Когда появится палитра команд, введите следующую команду, чтобы создать новую записную книжку .NET Interactive:

    ```text
    >.NET Interactive: Create new blank notebook
    ```

    Кроме того, если вы хотите открыть существующую записную книжку .NET Interactive с расширением *IPYNB*, используйте следующую команду:

    ```text
    >.NET Interactive: Open notebook
    ```

## <a name="initialize-a-spark-session"></a>Инициализация сеанса Spark

1. После открытия записной книжки установите пакет NuGet `Microsoft.Spark`. Убедитесь, что устанавливаемая версия совпадает с рабочей ролью .NET.

    ```text
    #r "nuget:Microsoft.Spark, 1.0.0"
    ```

1. Добавьте в файл следующую инструкцию using.

    ```csharp
    using Microsoft.Spark.Sql;
    ```

1. Инициализируйте [SparkSession](xref:Microsoft.Spark.Sql.SparkSession).

    ```csharp
    var sparkSession =
    SparkSession
        .Builder()
        .AppName("dotnet-interactive-spark")
        .GetOrCreate();
    ```

Записная книжка должна выглядеть примерно так, как показано на рисунке ниже. В этом примере используется VS Code, однако Jupyter Notebook и Jupyter Lab должны выглядеть примерно так же.

> [!div class="mx-imgBorder"]
![Jupyter Notebook VS Code .NET для Apache Spark](media/dotnet-spark-jupyter-notebooks/jupyter-notebooks-dotnet-spark-vscode.png)

## <a name="next-steps"></a>Next Steps

- [Начало работы с .NET для Apache Spark](../tutorials/get-started.md)
- [Прогнозирование тональности с помощью .NET для Apache Spark и ML.NET](../tutorials/ml-sentiment-analysis.md)
- Дополнительные сведения о .NET Interactive см. в [документации по .NET Interactive](https://github.com/dotnet/interactive/blob/main/docs/README.md).
