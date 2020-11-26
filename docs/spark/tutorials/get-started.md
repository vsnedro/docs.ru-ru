---
title: Начало работы с .NET для Apache Spark
description: Узнайте, как запустить приложение .NET для Apache Spark, используя .NET Core на Windows, macOS и Ubuntu.
ms.date: 10/09/2020
ms.topic: tutorial
ms.custom: mvc
ms.author: luquinta
author: luisquintanilla
ms.openlocfilehash: 16ccc8f40f290c4bc10f03d1f4d1b296b17f6b11
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/17/2020
ms.locfileid: "94687829"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a>Учебник. Начало работы с .NET для Apache Spark

В этом руководстве описывается, как запустить приложение .NET для Apache Spark, используя .NET Core на Windows, macOS и Ubuntu.

В этом руководстве вы узнаете, как:

> [!div class="checklist"]
>
> * подготовить среду под .NET для Apache Spark;
> * написать свое первое приложение .NET для Apache Spark;
> * скомпилировать и запустить приложение .NET для Apache Spark.

## <a name="prepare-your-environment"></a>Подготовка среды

Прежде чем приступить к написанию приложения, нужно настроить некоторые необходимые зависимости. Если вы можете выполнить `dotnet`, `java`, `spark-shell` из среды командной строки, то ваша среда уже подготовлена, и вы можете перейти к следующему разделу. Если эти команды или хотя бы одну из них выполнить не получается, сделайте следующее.

### <a name="1-install-net"></a>1. Установка .NET

Чтобы приступить к созданию приложений .NET, необходимо загрузить и установить пакет средств разработки программного обеспечения (SDK) для .NET.

Скачайте и установите [пакет SDK для .NET Core](https://dotnet.microsoft.com/download/dotnet-core/3.1). При установке пакета SDK в переменную PATH добавляется цепочка инструментов `dotnet`.

Установив пакет SDK для .NET Core, откройте новое окно командной строки или терминала и выполните команду `dotnet`.

Если команда выполняется и выводит сведения об использовании dotnet, можно перейти к следующему шагу. Если возникает ошибка `'dotnet' is not recognized as an internal or external command`, убедитесь, что команда выполняется в **новом** окне терминала или командной строки.

### <a name="2-install-java"></a>2. Установка Java

Установите [Java 8.1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) для Windows и macOS или [OpenJDK 8](https://openjdk.java.net/install/) для Ubuntu.

Выберите соответствующую версию для вашей операционной системы. Например, выберите **jdk-8u201-windows-x64.exe** для компьютера с 64-разрядной версией Windows (как показано ниже) или **jdk-8u231-macosx-x64.dmg** для macOS. Затем используйте команду `java`, чтобы проверить установку.

![Скачать Java](https://dotnet.microsoft.com/static/images/java-jdk-downloads-windows.png?v=6BbJHoNyDO-PyYVciImr5wzh2AW_YHNcyb3p093AwPA)

### <a name="3-install-compression-software"></a>3. Установка ПО для сжатия

Apache Spark загружается как сжатый файл TGZ. Чтобы извлечь файл, используйте программу-архиватор, например [7-Zip](https://www.7-zip.org/) или [WinZip](https://www.winzip.com/).

### <a name="4-install-apache-spark"></a>4. Установка Apache Spark

[Скачайте и установите Apache Spark](https://spark.apache.org/downloads.html). Вам потребуется выбрать одну из следующих версий: 2.3.* либо 2.4.0, 2.4.1, 2.4.3, 2.4.4, 2.4.5, 2.4.6, 2.4.7, 3.0.0 или 3.0.1 (.NET для Apache Spark несовместима с другими версиями Apache Spark).

Команды, используемые на следующих этапах, подразумевают, что [скачана и установлена версия Apache Spark 3.0.1](https://spark.apache.org/downloads.html). Если вы хотите использовать другую версию, замените **3.0.1** на соответствующий номер версии. Затем извлеките файл **TAR** и файлы Apache Spark.

Чтобы извлечь вложенный файл **TAR**:

* Найдите скачанный файл **spark-3.0.1-bin-hadoop2.7.tgz**.
* Щелкните файл правой кнопкой мыши и выберите **7-Zip -> Извлечь сюда**.
* **spark-3.0.1-bin-hadoop2.7.tar** будет создан рядом со скачанным файлом **TGZ**.

Чтобы извлечь файлы Apache Spark:

* Щелкните правой кнопкой мыши **spark-3.0.1-bin-hadoop2.7.tar** и выберите **7-Zip -> Извлечь файлы...**
* Введите **C:\bin** в поле **Извлечь в**.
* Снимите флажок под полем **Извлечь в**.
* Нажмите кнопку **ОК**.
* Файлы Apache Spark будут извлечены в папку C:\bin\spark-3.0.1-bin-hadoop2.7\

![Установка Spark](./media/spark-extract-with-7-zip.png)

Выполните следующие команды, чтобы задать переменные среды, используемые для размещения Apache Spark. В Windows обязательно запускайте командную строку от имени администратора.

#### <a name="windows"></a>[Windows](#tab/windows)

```console
setx /M HADOOP_HOME C:\bin\spark-3.0.1-bin-hadoop2.7\
setx /M SPARK_HOME C:\bin\spark-3.0.1-bin-hadoop2.7\
setx /M PATH "%PATH%;%HADOOP_HOME%;%SPARK_HOME%\bin"
```

#### <a name="maclinux"></a>[Mac/Linux](#tab/linux)

```bash
export SPARK_HOME=~/bin/spark-3.0.1-bin-hadoop2.7/
export PATH="$SPARK_HOME/bin:$PATH"
source ~/.bashrc
```

---

Установив все необходимое и задав переменные сред, откройте **новое** окно командной строки или терминала и выполните следующую команду:

```text
spark-submit --version
```

Если команда выполняется и выводит сведения о версии, можно перейти к следующему шагу.

При возникновении ошибки `'spark-submit' is not recognized as an internal or external command` убедитесь, что вы открыли **новую** командную строку.

### <a name="5-install-net-for-apache-spark"></a>5. Установка .NET для Apache Spark

Загрузите выпуск [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases) со страницы выпусков .NET для Apache Spark в GitHub. Например, если вы планируете использовать .NET Core на компьютере под управлением Windows, [скачайте выпуск netcoreapp3.1 для Windows x64](https://github.com/dotnet/spark/releases).

Для извлечения Microsoft.Spark.Worker:

* Найдите скачанный файл **Microsoft.Spark.Worker.netcoreapp3.1.win-x64-1.0.0.zip**.
* Щелкните правой кнопкой мыши и выберите **7-Zip -> Извлечь файлы**.
* Введите **C:\bin** в поле **Извлечь в**.
* Снимите флажок под полем **Извлечь в**.
* Нажмите кнопку **ОК**.

### <a name="6-install-winutils-windows-only"></a>6.  Установка WinUtils (только для Windows)

.NET для Apache Spark требует установки WinUtils вместе с Apache Spark. [Скачайте winutils.exe](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe). Затем скопируйте WinUtils в папку **C:\bin\spark-3.0.1-bin-hadoop2.7\bin**.

> [!NOTE]
> Если вы используете другую версию Hadoop, которая указывается в конце имени папки установки Spark, [выберите версию WinUtils](https://github.com/steveloughran/winutils), совместимую с вашей версией Hadoop.

### <a name="7-set-dotnet_worker_dir-and-check-dependencies"></a>7. Установка DOTNET_WORKER_DIR и проверка зависимостей

Выполните одну из следующих команд, чтобы задать переменную среды `DOTNET_WORKER_DIR`, которая используется приложениями .NET для обнаружения .NET для двоичных файлов рабочих ролей Apache Spark. Обязательно замените `<PATH-DOTNET_WORKER_DIR>` каталогом, который вы использовали для скачивания и распаковки `Microsoft.Spark.Worker`. В Windows обязательно запускайте командную строку от имени администратора.

#### <a name="windows"></a>[Windows](#tab/windows)

```console
setx /M DOTNET_WORKER_DIR <PATH-DOTNET-WORKER-DIR>
```

#### <a name="maclinux"></a>[Mac/Linux](#tab/linux)

```bash
export DOTNET_WORKER_DIR=<PATH-DOTNET-WORKER-DIR>
```

---

Наконец, перед переходом к следующему разделу еще раз проверьте, можно ли выполнить команды `dotnet`, `java`, `spark-shell` из командной строки.

## <a name="write-a-net-for-apache-spark-app"></a>Написание приложения .NET для Apache Spark

### <a name="1-create-a-console-app"></a>1. Создание консольного приложения

В командной строке или терминале выполните следующие команды, чтобы создать новое консольное приложение:

```dotnetcli
dotnet new console -o MySparkApp
cd MySparkApp
```

Команда `dotnet` создаст для вас приложение `new` типа `console`. Параметр `-o` создаст каталог с именем *MySparkApp*, в котором хранится приложение и используемые им файлы. Команда `cd MySparkApp` изменит каталог на созданный каталог приложения.

### <a name="2-install-nuget-package"></a>2. Установка пакета NuGet

Чтобы использовать .NET для Apache Spark в приложении, установите пакет Microsoft.Spark. В командной строке или терминале выполните следующую команду:

```dotnetcli
dotnet add package Microsoft.Spark
```

> [!NOTE]
> Для работы с этим руководством используйте последнюю версию пакета NuGet `Microsoft.Spark` (если не указано иное).

### <a name="3-write-your-app"></a>3. Написание приложения

Откройте *Program.cs* в Visual Studio Code или любом текстовом редакторе и замените весь код следующим:

```csharp
using Microsoft.Spark.Sql;
using static Microsoft.Spark.Sql.Functions;

namespace MySparkApp
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create Spark session
            SparkSession spark =
                SparkSession
                    .Builder()
                    .AppName("word_count_sample")
                    .GetOrCreate();

            // Create initial DataFrame
            string filePath = args[0];
            DataFrame dataFrame = spark.Read().Text(filePath);

            //Count words
            DataFrame words =
                dataFrame
                    .Select(Split(Col("value")," ").Alias("words"))
                    .Select(Explode(Col("words")).Alias("word"))
                    .GroupBy("word")
                    .Count()
                    .OrderBy(Col("count").Desc());

            // Display results
            words.Show();

            // Stop Spark session
            spark.Stop();
        }
    }
}
```

[SparkSession](xref:Microsoft.Spark.Sql.SparkSession) — это точка входа приложений Apache Spark, которая управляет контекстом и сведениями о приложении. С помощью метода [Text](xref:Microsoft.Spark.Sql.DataFrameReader.Text%2A) текстовые данные из файла, указанного с помощью параметра `filePath`, считываются в [DataFrame](xref:Microsoft.Spark.Sql.DataFrame). DataFrame представляет способ упорядочивания данных в набор именованных столбцов. Над ними затем выполняется серия преобразований для разделения предложений в файле, определения каждого слова в группу, подсчета слов и упорядочивания их в порядке убывания. Результат этих операций хранится в другом DataFrame. Обратите внимание, что на этом этапе операции не выполнялись, так как .NET для Apache Spark оценивает данные в отложенном режиме. Операции, определенные в строках выше, начнут выполняться только после того, как будет вызван метод [Show](xref:Microsoft.Spark.Sql.DataFrame.Show%2A) для отображения содержимого записи `words` преобразованного DataFrame в консоли. Если вы не будете продолжать работу с сеансом Spark, завершите его с помощью метода [Stop](xref:Microsoft.Spark.Sql.SparkSession.Stop%2A).

### <a name="4-create-data-file"></a>4. Создание файла данных

Ваше приложение обрабатывает файл, содержащий строки текста. В каталоге *MySparkApp* создайте файл *input.txt*, содержащий следующий текст:

```text
Hello World
This .NET app uses .NET for Apache Spark
This .NET app counts words with Apache Spark
```

Сохраните изменения и закройте файл.

## <a name="run-your-net-for-apache-spark-app"></a>Запуск приложения .NET для Apache Spark

Запустите сборку приложения с помощью следующей команды:

```dotnetcli
dotnet build
```

Перейдите к каталогу выходных данных сборки и с помощью команды `spark-submit` отправьте приложение для выполнения в Apache Spark. Обязательно замените `<version>` версией своей рабочей роли .NET, а `<path-of-input.txt>` — путем к вашему сохраненному файлу *input.txt*.

### <a name="windows"></a>[Windows](#tab/windows)

```console
spark-submit ^
--class org.apache.spark.deploy.dotnet.DotnetRunner ^
--master local ^
microsoft-spark-3-0_2.12-<version>.jar ^
dotnet MySparkApp.dll <path-of-input.txt>
```

### <a name="maclinux"></a>[Mac/Linux](#tab/linux)

```bash
spark-submit \
--class org.apache.spark.deploy.dotnet.DotnetRunner \
--master local \
microsoft-spark-3-0_2.12-<version>.jar \
dotnet MySparkApp.dll <path-of-input.txt>
```

---

> [!NOTE]
> При выполнении этой команды предполагается, что вы скачали Apache Spark и добавили это решение в переменную среды PATH, чтобы использовать `spark-submit`. В противном случае потребуется использовать полный путь (например, *C:\bin\apache-spark\bin\spark-submit* или *~/spark/bin/spark-submit*).

При запуске приложения данные подсчета слов из файла *input.txt* записываются в консоль.

```console
+------+-----+
|  word|count|
+------+-----+
|  .NET|    3|
|Apache|    2|
|   app|    2|
|  This|    2|
| Spark|    2|
| World|    1|
|counts|    1|
|   for|    1|
| words|    1|
|  with|    1|
| Hello|    1|
|  uses|    1|
+------+-----+
```

Поздравляем! Вы успешно создали и запустили приложение .NET для Apache Spark.

## <a name="next-steps"></a>Следующие шаги

В этом руководстве вы узнали, как выполнять следующие задачи:
> [!div class="checklist"]
>
> * подготовить среду под .NET для Apache Spark;
> * написать свое первое приложение .NET для Apache Spark;
> * скомпилировать и запустить приложение .NET для Apache Spark.

Видео, в котором подробнее объясняются приведенные выше шаги, можно найти в серии видео с [общими сведениями о .NET для Apache Spark](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App).

Дополнительные сведения см. на странице ресурсов.
> [!div class="nextstepaction"]
> [Ресурсы по .NET для Apache Spark](../resources/index.md)
