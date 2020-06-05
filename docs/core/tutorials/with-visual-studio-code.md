---
title: Создание консольного приложения с помощью .NET Core в Visual Studio Code
description: Узнайте, как создать консольное приложение .NET Core с помощью Visual Studio Code и .NET Core CLI.
ms.date: 05/22/2020
ms.openlocfilehash: 673c4a639a2cab26261b7cdafd5d8e20acfafb94
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2020
ms.locfileid: "84201704"
---
# <a name="tutorial-create-a-console-application-with-net-core-using-visual-studio-code"></a>Учебник. Создание консольного приложения с помощью .NET Core в Visual Studio Code

В этом учебнике показано, как создать и запустить консольное приложение .NET Core с помощью Visual Studio Code и .NET Core CLI. Задачи проекта, такие как создание, компиляция и запуск проекта, выполняются с помощью интерфейса командной строки, поэтому вы можете следовать этому учебнику, используя другой редактор кода, и выполнять команды в терминале при желании.

## <a name="prerequisites"></a>Предварительные требования

1. Установленная платформа [Visual Studio Code](https://code.visualstudio.com/) с [расширением C#](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp). См. сведения об [установке расширений Visual Studio Code из Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).
2. [Пакет SDK для .NET Core 3.1 или более поздней версии](https://dotnet.microsoft.com/download)

## <a name="create-the-app"></a>Создание приложения

1. Откройте Visual Studio Code.

1. Создайте проект.

   1. В главном меню выберите **Файл** > **Открыть папку**/**Открыть**, создайте папку *HelloWorld* и нажмите **Выбрать папку**/**Открыть**.

      Имя папки по умолчанию преобразуется в имя проекта и имя пространства имен. Вы добавите код позже в этом учебнике. Предполагается, что пространство имен проекта — `HelloWorld`.

   1. Откройте **терминал** в Visual Studio Code, выбрав в основном меню пункт **Вид** > **Терминал**.

      Откроется окно **Терминал** с командной строкой в папке *HelloWorld*.

   1. В **окне терминала** введите следующую команду:

      ```dotnetcli
      dotnet new console
      ```

Шаблон консольного приложения для .NET Core определяет класс `Program` с одним методом `Main`, который принимает в качестве аргумента массив <xref:System.String>. В файле *Program.cs* находится следующий код:

```csharp
using System;

namespace HelloWorld
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

`Main` — точка входа в приложение. Это метод, который автоматически вызывается средой выполнения при запуске приложения. Все аргументы, предоставленные в командной строке при запуске приложения, доступны через массив *args*.

Шаблон создает простое приложение, которое вызывает метод <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> для вывода сообщения "Hello World!" в окне консоли.

## <a name="run-the-app"></a>Запуск приложения

Выполните следующие команды в **окне терминала**:

```dotnetcli
dotnet run
```

В программе отобразится сообщение "Hello World!", после чего она завершится.

![Команда dotnet run](media/with-visual-studio-code/dotnet-run-command.png)

## <a name="enhance-the-app"></a>Улучшение приложения

Давайте расширим приложение. Теперь у пользователя будет запрашиваться имя, которое затем будет отображаться с датой и временем.

1. Откройте файл *Program.cs*, щелкнув его.

   Когда вы в первый раз открываете файл C# в Visual Studio Code, в редакторе загружается [OmniSharp](https://www.omnisharp.net/).

   ![Откройте файл Program.cs](media/with-visual-studio-code/open-program-cs.png)

1. Когда в Visual Studio Code будет предложено добавить недостающие ресурсы для сборки и отладки приложения, выберите **Да**.

   ![Предупреждение о недостающих ресурсах](media/with-visual-studio-code/missing-assets.png)

1. Замените содержимое метода `Main` в файле *Program.cs* (в настоящий момент это просто строка, вызывающая `Console.WriteLine`) следующим кодом:

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="Snippet1":::

   Теперь код выдает строку "What is your name?" (Как вас зовут?) в окно консоли и ожидает, чтобы пользователь ввел строку текста и нажал клавишу **ВВОД**. Приложение сохраняет полученную строку в переменной с именем `name`. Оно также получает значение свойства <xref:System.DateTime.Now?displayProperty=nameWithType>, которое содержит текущее локальное время, и присваивает его переменной с именем `date`. Наконец, оно отображает эти значения в окне консоли.

   `\n` — это символ новой строки.

   Знак доллара (`$`) перед строкой позволяет вставить такие выражения, как имена переменных, в фигурные скобки в строке. Значение выражения вставляется в строку вместо выражения. Такой синтаксис называется [интерполированными строками](../../csharp/language-reference/tokens/interpolated.md).

1. Сохраните изменения.

   > [!IMPORTANT]
   > В Visual Studio Code необходимо явно сохранить изменения. В отличие от Visual Studio, изменения файлов не сохраняются автоматически при сборке и запуске приложения.

1. Запустите программу еще раз:

   ```dotnetcli
   dotnet run
   ```

1. В ответ на приглашение в командной строке введите имя и нажмите клавишу **ВВОД**.

   :::image type="content" source="media/debugging-with-visual-studio-code/run-modified-program.png" alt-text="Окно терминала с измененными выходными данными программы":::

1. Нажмите любую клавишу для выхода из программы.

## <a name="additional-resources"></a>Дополнительные ресурсы

- [Setting up Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview) (Настройка Visual Studio Code)

## <a name="next-steps"></a>Следующие шаги

В этом учебнике вы создали приложение .NET Core. В следующем учебнике описывается отладка приложения.

> [!div class="nextstepaction"]
> [Отладка консольного приложения .NET Core с помощью Visual Studio Code](debugging-with-visual-studio-code.md)
