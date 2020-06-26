---
title: Создание библиотеки классов .NET Standard с помощью Visual Studio для Mac
description: Сведения о создании библиотеки классов .NET Standard с помощью Visual Studio для Mac.
ms.date: 06/08/2020
ms.openlocfilehash: 3a107fff2fd6aef5e06d9af3eac334fbf5688fa5
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2020
ms.locfileid: "84713421"
---
# <a name="tutorial-create-a-net-standard-library-using-visual-studio-for-mac"></a>Учебник. Создание библиотеки .NET Standard с помощью Visual Studio для Mac

В этом учебнике вы создадите простую библиотеку классов с одним методом для обработки строк. Вы реализуете его как [метод расширения](../../csharp/programming-guide/classes-and-structs/extension-methods.md), чтобы вызывать его так же, как любой член класса <xref:System.String>.

*Библиотека классов* определяет типы и методы, которые могут быть вызваны из любого приложения. Библиотеку классов, предназначенную для .NET Standard 2.1, может использовать приложение для любой реализации .NET, которая поддерживает версию .NET Standard 2.1. Когда вы завершите создание библиотеки классов, можете распространить ее как независимый компонент или включить в состав одного или нескольких пакетов приложения.

> [!NOTE]
> Ваш отзыв очень важен. Вы можете отправить отзыв о Visual Studio для Mac команде разработчиков двумя способами.
>
> - В Visual Studio для Mac выберите пункт **Справка** > **Сообщить о проблеме** в меню или элемент **Сообщить о проблеме** на экране приветствия. При этом открывается окно для заполнения отчета об ошибках. Отслеживать свои отзывы можно на портале [сообщества разработчиков](https://developercommunity.visualstudio.com/spaces/41/index.html).
> - Чтобы внести предложение, выберите пункт **Справка** > **Отправить предложение** в меню или элемент **Отправить предложение** на экране приветствия. При этом откроется [веб-страница сообщества разработчиков Visual Studio для Mac](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).

## <a name="prerequisites"></a>Предварительные требования

* [Установите Visual Studio для Mac 8.6 или более поздней версии](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link). Выберите вариант установки .NET Core. Установка Xamarin является необязательным шагом для разработки .NET Core. Дополнительные сведения см. в следующих ресурсах:

  * [Учебник. Установка Visual Studio для Mac](/visualstudio/mac/installation).
  * [Поддерживаемые версии macOS](../install/dependencies.md?pivots=os-macos).
  * [Версии .NET Core, поддерживаемые Visual Studio для Mac](/visualstudio/mac/net-core-support).

## <a name="create-a-solution-with-a-class-library-project"></a>Создание решения с помощью проекта библиотеки классов

Решение Visual Studio служит контейнером для одного или нескольких проектов. Создайте решение и проект библиотеки классов в решении. Позже вы добавите дополнительные связанные проекты в одно решение.

1. Запустите Visual Studio для Mac.

1. В окне запуска выберите **Создать проект**.

1. В узле **Многоплатформенность** диалогового окна **Создание проекта** выберите **Библиотека**, а затем — шаблон **Библиотека .NET Standard** и нажмите кнопку **Далее**.

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-new-project.png" alt-text="Диалоговое окно Новый проект":::

1. В диалоговом окне **Configure your new .NET Standard Library** (Настройка новой библиотеки .NET Standard) выберите ".NET Standard 2.1", а затем нажмите кнопку **Далее**.

   :::image type="content" source="media/library-with-visual-studio-mac/choose-net-std-21.png" alt-text="Выбор .NET Standard 2.1":::

1. Присвойте проекту имя StringLibrary, а решению — ClassLibraryProjects. Оставьте флажок **Создайте каталог проекта в каталоге решения** установленным. Выберите **Создать**.

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-new-project-options.png" alt-text="Параметры диалогового окна Создание проекта Visual Studio для Mac":::

1. В главном меню выберите **Вид** > **Панели** > **Решение** и щелкните значок закрепления, чтобы панель была открытой.

   :::image type="content" source="media/library-with-visual-studio-mac/solution-dock-icon.png" alt-text="Значок закрепления для панели решения":::

1. На панели **Решение** разверните узел `StringLibrary`, чтобы отобразить предоставленный шаблоном файл класса *Class1.cs*. Удерживая нажатой клавишу <kbd>CTRL</kbd>, щелкните файл, выберите **Переименовать** в контекстном меню и переименуйте файл в *StringLibrary.cs*. Откройте файл и замените его содержимое на следующий код:

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::

1. Нажмите <kbd>⌘</kbd><kbd>S</kbd> (<kbd>Command</kbd>+<kbd>S</kbd>), чтобы сохранить файл.

1. Выберите **Ошибки** в нижней части окна интегрированной среды разработки, чтобы открыть панель **Ошибки**. Нажмите кнопку **Выходные данные сборки**.

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-error-button.png" alt-text="Нижнее поле окна интегрированной среды разработки Visual Studio для Mac с кнопкой Ошибки":::

1. Выберите в меню **Сборка** > **Собрать все**.

   Выполняется сборка решения. На панели выходных данных отображается сообщение об успешной сборке.

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-build-panel.png" alt-text="Область выходных данных Visual Studio для Mac на панели Ошибки c сообщением об успешной сборке":::

## <a name="add-a-console-app-to-the-solution"></a>Добавление консольного приложения в решение

Добавьте консольное приложение, использующее библиотеку классов. В приложении пользователю будет предложено ввести строку и сообщить, начинается ли строка с символа верхнего регистра.

1. На панели **Решение** щелкните решение `ClassLibraryProjects` при нажатой клавише <kbd>CTRL</kbd>. Добавьте новый проект **Консольное приложение**, выбрав шаблон в области **Web and Console** (Интернет и консоль) > **Приложение**, а затем нажмите кнопку **Далее**.

1. Выберите **.NET Core 3.1** в качестве **требуемой версии .NET Framework**, а затем нажмите кнопку **Далее**.

1. Назовите проект **ShowCase**. Выберите **Создать**, чтобы создать проект в решении.

   :::image type="content" source="media/library-with-visual-studio-mac/add-showcase-project.png" alt-text="Добавление проекта ShowCase":::

1. Откройте файл *Program.cs*. Замените код следующим кодом:

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::

   Сама программа предлагает пользователю ввести строку. Она сообщает, начинается ли строка с символа верхнего регистра. Если пользователь нажимает клавишу <kbd>ВВОД</kbd>, не введя никакой строки, приложение завершает свою работу и окно консоли закрывается.

   В этом коде используется переменная `row` для сохранения количества строк данных, записываемых в окно консоли. Всякий раз, когда оно достигает значения 25 или превышает его, код очищает окно консоли и отображается сообщение для пользователя.

## <a name="add-a-project-reference"></a>Добавление ссылки на проект

Изначально новый проект консольного приложения не имеет доступа к библиотеке классов. Чтобы позволить приложению вызывать методы из библиотеки классов, создайте в проекте ссылку на проект библиотеки классов.

1. На панели **Решения**, удерживая нажатой клавишу <kbd>CTRL</kbd>, щелкните узел **Зависимости** нового проекта **ShowCase**. В контекстном меню выберите пункт **Добавить ссылку**.

1. В диалоговом окне **Ссылки** выберите проект **StringLibrary** и нажмите кнопку **OK**.

## <a name="run-the-app"></a>Запуск приложения

1. Удерживая нажатой клавишу <kbd>CTRL</kbd>, щелкните проект ShowCase и выберите **Запустить проект** в контекстном меню.

1. Проверьте, как работает программа: вводите строки и нажимайте клавишу <kbd>ВВОД</kbd>. Чтобы выйти, просто нажмите клавишу <kbd>ВВОД</kbd>.

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-console-window.png" alt-text="Окно консоли Visual Studio для Mac с отображением запуска приложения":::

## <a name="additional-resources"></a>Дополнительные ресурсы

* [Разработка библиотек с помощью .NET Core CLI](libraries.md)
* [Список версий .NET Standard и поддерживаемых ими платформ](../../standard/net-standard.md)
* [Заметки о выпуске Visual Studio 2019 для Mac](/visualstudio/releasenotes/vs2019-mac-relnotes)

## <a name="next-steps"></a>Следующие шаги

В этом учебнике вы создали решение и проект библиотеки, а также добавили проект консольного приложения, использующего эту библиотеку. В следующем руководстве вы добавите в решение проект модульного теста.

> [!div class="nextstepaction"]
> [Тестирование библиотеки .NET Standard с помощью .NET Core и Visual Studio для Mac](testing-library-with-visual-studio-mac.md)
