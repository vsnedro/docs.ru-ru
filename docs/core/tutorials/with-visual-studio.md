---
title: Создание консольного приложения .NET Core в Visual Studio
description: Узнайте, как консольное приложение .NET Core с помощью C# или Visual Basic в Visual Studio.
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 7ef8e17b8a42defc0858123332976d30c83f20c8
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2020
ms.locfileid: "84700436"
---
# <a name="tutorial-create-a-net-core-console-application-using-visual-studio"></a>Учебник. Создание консольного приложения .NET Core в Visual Studio

В этом учебнике показано, как создать и запустить консольное приложение .NET Core в помощью Visual Studio 2019.

## <a name="prerequisites"></a>Предварительные требования

- [Visual Studio 2019 версии 16.6 или более поздней](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) с установленной рабочей нагрузкой **Кроссплатформенная разработка .NET Core**. Пакет SDK для .NET Core 3.1 устанавливается автоматически при выборе этой рабочей нагрузки.

  См. раздел [Установка с помощью Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio).

## <a name="create-the-app"></a>Создание приложения

Создайте проект консольного приложения .NET Core с именем HelloWorld.

1. Запустите Visual Studio 2019.

1. На начальной странице выберите **Создать проект**.

   ![Кнопка "Создать проект", выбранная на начальной странице Visual Studio](./media/with-visual-studio/start-window.png)

1. На странице **Создание проекта** введите в поле поиска **консоль**. Затем выберите **C#** или **Visual Basic** из списка языков, а затем — **Все платформы** из списка платформ. Выберите шаблон **Консольное приложение (.NET Core)** и щелкните **Далее**.

   ![Окно "Создание проекта" с выбранными фильтрами](./media/with-visual-studio/create-new-project.png)

   > [!TIP]
   > Если вы не видите шаблоны .NET Core, вероятно, у вас не установлена требуемая рабочая нагрузка. В сообщении **Не удается найти то, что ищете?** выберите ссылку **Установка других средств и компонентов**. Откроется Visual Studio Installer. Убедитесь, что у вас установлена рабочая нагрузка **Кроссплатформенная разработка .NET Core**.

1. В диалоговом окне **Настройка нового проекта** в поле **Имя проекта** введите **HelloWorld**. Затем нажмите кнопку **Создать**.

   ![Окно настройки нового проекта с полями имени проекта, расположения и имени решения](./media/with-visual-studio/configure-new-project.png)

Этот шаблон создает простое приложение Hello World. Он вызывает метод <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> для отображения сообщения "Hello World!" в окне консоли.

Код шаблона определяет класс `Program` с одним методом `Main`, который принимает в качестве аргумента массив <xref:System.String>.

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

```vb
Imports System

Module Program
    Sub Main(args As String())
        Console.WriteLine("Hello World!")
    End Sub
End Module
```

`Main` — точка входа в приложение. Это метод, который автоматически вызывается средой выполнения при запуске приложения. Все аргументы, предоставленные в командной строке при запуске приложения, доступны через массив *args*.

Если нужный язык не отображается, измените выбор языка в верхней части страницы.

## <a name="run-the-app"></a>Запуск приложения

1. Нажмите клавиши <kbd>SHIFT</kbd>+<kbd>F5</kbd>, чтобы запустить программу без отладки.

   Откроется окно консоли с текстом "Hello World!" на экране и информацией об отладке Visual Studio.

   ![Окно консоли с приложением Hello World и надписью "Чтобы продолжить, нажмите любую клавишу"](./media/with-visual-studio/hello-world-console.png)

1. Для закрытия консольного окна нажмите любую клавишу.

## <a name="enhance-the-app"></a>Улучшение приложения

Давайте расширим приложение. Теперь у пользователя будет запрашиваться имя, которое затем будет отображаться с датой и временем.

1. В *Program.cs* или *Program.vb* замените содержимое метода `Main` (строка, вызывающая `Console.WriteLine`) следующим кодом:

   [!code-csharp[GettingStarted#1](./snippets/with-visual-studio/csharp/Program.cs#1)]
   [!code-vb[GettingStarted#1](./snippets/with-visual-studio/vb/Program.vb#1)]

   Теперь код выдает строку "What is your name?" (Как вас зовут?) в окно консоли и ожидает, чтобы пользователь ввел строку текста и нажал клавишу <kbd>ВВОД</kbd>. Приложение сохраняет полученную строку в переменной с именем `name`. Оно также получает значение свойства <xref:System.DateTime.Now?displayProperty=nameWithType>, которое содержит текущее локальное время, и присваивает его переменной с именем `date` (`currentDate` в Visual Basic). Наконец, оно отображает эти значения в окне консоли.

   `\n` (`vbCrLf` в Visual Basic) представляет собой символ новой строки.

   Знак доллара (`$`) перед строкой позволяет вставить такие выражения, как имена переменных, в фигурные скобки в строке. Значение выражения вставляется в строку вместо выражения. Такой синтаксис называется [интерполированными строками](../../csharp/language-reference/tokens/interpolated.md).

1. Нажмите клавиши <kbd>SHIFT</kbd>+<kbd>F5</kbd>, чтобы запустить программу без отладки.

1. В ответ на приглашение в командной строке введите имя и нажмите клавишу <kbd>ВВОД</kbd>.

   ![Окно консоли с измененными выходными данными программы](./media/with-visual-studio/hello-world-update.png)

1. Для закрытия консольного окна нажмите любую клавишу.

## <a name="next-steps"></a>Следующие шаги

В этом руководстве показано, как создать консольное приложение .NET Core. В следующем учебнике описывается отладка приложения.

> [!div class="nextstepaction"]
> [Отладка консольного приложения .NET Core в Visual Studio](debugging-with-visual-studio.md)
