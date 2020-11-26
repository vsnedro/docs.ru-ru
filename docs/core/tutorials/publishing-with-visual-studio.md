---
title: Публикация консольного приложения .NET с помощью Visual Studio
description: Узнайте, как использовать Visual Studio для создания набора файлов, необходимых для запуска приложения .NET.
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: b0c6bd85ddf86f0eb11c56f01abb74a7e9786363
ms.sourcegitcommit: 5114e7847e0ff8ddb8c266802d47af78567949cf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "94916033"
---
# <a name="tutorial-publish-a-net-console-application-using-visual-studio"></a>Учебник. Публикация консольного приложения .NET с помощью Visual Studio

В этом руководстве показано, как опубликовать консольное приложение, чтобы его могли запускать другие пользователи. При публикации создается набор файлов, которые необходимы для запуска приложения. Чтобы развернуть файлы, скопируйте их на целевой компьютер.

## <a name="prerequisites"></a>Предварительные требования

- В этом руководстве используется консольное приложение, созданное в руководстве [Создание консольного приложения .NET в Visual Studio](with-visual-studio.md).

## <a name="publish-the-app"></a>Публикация приложения

1. Запустите Visual Studio.

1. Откройте проект *HelloWorld*, созданный по инструкциям из статьи [Создание консольного приложения .NET в Visual Studio](with-visual-studio.md).

1. Убедитесь, что в Visual Studio используется конфигурация сборки Release. При необходимости измените конфигурацию сборки на панели инструментов, указав конфигурацию **Выпуск** вместо конфигурации **Отладка**.

   :::image type="content" source="media/publishing-with-visual-studio/visual-studio-toolbar-release.png" alt-text="Панель инструментов Visual Studio с выбранной сборкой выпуска":::

1. Щелкните проект **HelloWorld** (не решение HelloWorld) правой кнопкой мыши и выберите **Опубликовать**.

   :::image type="content" source="media/publishing-with-visual-studio/publish-context-menu.png" alt-text="Контекстное меню Опубликовать в Visual Studio":::

1. На вкладке **Целевой объект** на странице **Публикация** выберите **Папка**, а затем нажмите кнопку **Далее**.

   :::image type="content" source="media/publishing-with-visual-studio/pick-publish-target.png" alt-text="Выбор целевого объекта публикации в Visual Studio":::

1. На вкладке **Определенный целевой объект** на странице **Публикация** выберите **Папка**, а затем нажмите кнопку **Далее**.

   :::image type="content" source="media/publishing-with-visual-studio/pick-specific-publish-target.png" alt-text="Выбор определенного целевого объекта публикации в Visual Studio":::

1. На вкладке **Расположение** на странице **Публикация** нажмите кнопку **Готово**.

   :::image type="content" source="media/publishing-with-visual-studio/publish-page-loc-tab.png" alt-text="Вкладка &quot;Расположение&quot; на странице &quot;Публикация&quot; в Visual Studio":::

1. На вкладке **Публикация** в окне **Публикация** нажмите кнопку **Опубликовать**.

   :::image type="content" source="media/publishing-with-visual-studio/publish-page.png" alt-text="Окно публикации в Visual Studio":::

## <a name="inspect-the-files"></a>Проверка файлов

По умолчанию при публикации создается развертывание, зависящее от платформы. При таком развертывании опубликованное приложение выполняется на компьютере с установленной средой выполнения .NET. Пользователи могут запустить опубликованное приложение, дважды щелкнув исполняемый файл или выполнив команду `dotnet HelloWorld.dll` из командной строки.

В следующих шагах будут рассмотрены файлы, созданные в процессе публикации.

1. В **обозревателе решений** выберите **Показать все файлы**.

1. В папке проекта разверните узел *bin/Release/net5.0/publish*.

   :::image type="content" source="media/publishing-with-visual-studio/published-files-output.png" alt-text="Опубликованные файлы в обозревателе решений":::

   Как показано на рисунке, опубликованные выходные данные включают следующие файлы:

   * *HelloWorld.deps.json*

      Это файл зависимостей среды выполнения приложения. Он определяет библиотеки и компоненты .NET (включая библиотеку DLL, содержащую приложение), необходимые для запуска приложения. Дополнительные сведения см. в разделе [Runtime Configuration Files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md) (Файлы конфигурации среды выполнения).

   * *HelloWorld.dll*

      Это версия [зависимого от платформы развертывания](../deploying/deploy-with-cli.md#framework-dependent-deployment) приложения. Чтобы выполнить эту библиотеку динамической компоновки, введите `dotnet HelloWorld.dll` в командной строке. Этот метод запуска приложения работает на любой платформе, где установлена среда выполнения .NET.

   * *HelloWorld.exe*

      Это версия [исполняемого, зависящего от платформы файла](../deploying/deploy-with-cli.md#framework-dependent-executable) приложения. Чтобы запустить его, введите `HelloWorld.exe` в командной строке. Файл зависит от операционной системы.

   * *HelloWorld.pdb* (необязателен для развертывания)

      Это файл отладочных символов. Этот файл не нужно распространять вместе с приложением, но желательно сохранить его на случай, если придется выполнять отладку опубликованной версии приложения.

   * *HelloWorld.runtimeconfig.json*

      Это файл конфигурации среды выполнения для приложения. Он определяет версию платформы .NET, для которой предназначено приложение. Кроме того, в него можно добавить параметры конфигурации. Дополнительные сведения см. в статье [Параметры конфигурации среды выполнения .NET](../run-time-config/index.md#runtimeconfigjson).

## <a name="run-the-published-app"></a>Запуск опубликованного приложения

1. В **обозревателе решений** щелкните папку *publish* правой кнопкой мыши и выберите команду **Копировать полный путь**.

1. Откройте командную строку и перейдите к папке *publish*. Для этого введите `cd` и вставьте полный путь. Пример:

   ```console
   cd C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\publish\
   ```

1. Запустите приложение с помощью исполняемого файла:

   1. Введите `HelloWorld.exe` и нажмите клавишу <kbd>ВВОД</kbd>.

   1. В ответ на запрос введите имя и нажмите любую клавишу, чтобы выйти.

1. Запустите приложение с помощью команды `dotnet`:

   1. Введите `dotnet HelloWorld.dll` и нажмите клавишу <kbd>ВВОД</kbd>.

   1. В ответ на запрос введите имя и нажмите любую клавишу, чтобы выйти.

## <a name="additional-resources"></a>Дополнительные ресурсы

- [развертывание приложений .NET](../deploying/index.md)

## <a name="next-steps"></a>Следующие шаги

В этом руководстве вы опубликовали консольное приложение. Далее вы создадите библиотеку классов.

> [!div class="nextstepaction"]
> [Создание библиотеки классов .NET с помощью Visual Studio](library-with-visual-studio.md)
