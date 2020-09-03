---
title: Публикация консольного приложения .NET Core с помощью Visual Studio для Mac
description: При публикации создается набор файлов, которые необходимы для запуска приложения .NET Core.
ms.date: 06/08/2020
ms.openlocfilehash: ec6b867f145ffdea491187de3745149f2cebd8dd
ms.sourcegitcommit: b9122d1af21898eaba81e990c70fef46fef74a8d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2020
ms.locfileid: "88867546"
---
# <a name="tutorial-publish-a-net-core-console-application-using-visual-studio-for-mac"></a>Учебник. Публикация консольного приложения .NET Core с помощью Visual Studio для Mac

В этом руководстве показано, как опубликовать консольное приложение, чтобы его могли запускать другие пользователи. При публикации создается набор файлов, которые необходимы для запуска приложения. Чтобы развернуть файлы, скопируйте их на целевой компьютер.

## <a name="prerequisites"></a>Предварительные требования

- В этом учебнике используется консольное приложение, созданное по инструкциям из статьи [Создание консольного приложения .NET Core в Visual Studio для Mac](with-visual-studio-mac.md).

## <a name="publish-the-app"></a>Публикация приложения

1. Запустите Visual Studio для Mac.

1. Откройте проект HelloWorld, созданный по инструкциям из статьи [Создание консольного приложения .NET Core в Visual Studio для Mac](with-visual-studio-mac.md).

1. Убедитесь, что в Visual Studio настроен режим сборки для версии выпуска. При необходимости измените конфигурацию сборки на панели инструментов, указав конфигурацию **Выпуск** вместо конфигурации **Отладка**.

   :::image type="content" source="media/publishing-with-visual-studio-mac/toolbar-release.png" alt-text="Панель инструментов Visual Studio с выбранной сборкой выпуска":::

1. В главном меню выберите **Сборка** > **Опубликовать в папке…**

   :::image type="content" source="media/publishing-with-visual-studio-mac/publish-context-menu.png" alt-text="Контекстное меню Опубликовать в Visual Studio":::

1. В диалоговом окне **Опубликовать в папке** выберите **Опубликовать**.

   :::image type="content" source="media/publishing-with-visual-studio-mac/publish-to-folder-dialog.png" alt-text="Диалоговое окно Опубликовать в папке в Visual Studio":::

   Откроется папка публикации с созданными файлами.

   :::image type="content" source="media/publishing-with-visual-studio-mac/publish-folder.png" alt-text="папка публикации":::

1. Щелкните значок шестеренки, а затем в контекстном меню выберите **Copy "publish" as Pathname** (Копировать publish как путь к папке).

   :::image type="content" source="media/publishing-with-visual-studio-mac/copy-path.png" alt-text="Копирование пути к папке публикации":::

## <a name="inspect-the-files"></a>Проверка файлов

В ходе публикации создается платформенно-зависимое развертывание. При таком развертывании опубликованное приложение выполняется на компьютере с установленной средой выполнения .NET Core. Пользователи могут запустить опубликованное приложение, выполнив команду `dotnet HelloWorld.dll` из командной строки.

Как показано на предыдущем рисунке, опубликованные выходные данные включают следующие файлы:

* *HelloWorld.deps.json*

  Это файл зависимостей среды выполнения приложения. Он определяет библиотеки и компоненты .NET Core (включая библиотеку DLL, содержащую приложение), необходимые для запуска приложения. Дополнительные сведения см. в разделе [Runtime Configuration Files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md) (Файлы конфигурации среды выполнения).

* *HelloWorld.dll*

   Это версия [зависимого от платформы развертывания](../deploying/deploy-with-cli.md#framework-dependent-deployment) приложения. Чтобы выполнить эту библиотеку динамической компоновки, введите `dotnet HelloWorld.dll` в командной строке. Этот метод запуска приложения работает на любой платформе, где установлена среда выполнения .NET Core.

* *HelloWorld.pdb* (необязателен для развертывания)

   Это файл отладочных символов. Этот файл не нужно распространять вместе с приложением, но желательно сохранить его на случай, если придется выполнять отладку опубликованной версии приложения.

* *HelloWorld.runtimeconfig.json*

   Это файл конфигурации среды выполнения для приложения. Он определяет версию платформы .NET Core, для которой предназначено приложение. Кроме того, в него можно добавить параметры конфигурации. Дополнительные сведения см. в статье [Параметры конфигурации среды выполнения .NET Core](../run-time-config/index.md#runtimeconfigjson).

## <a name="run-the-published-app"></a>Запуск опубликованного приложения

1. Откройте терминал и перейдите в папку *publish*. Для этого введите `cd` и вставьте скопированный ранее путь. Пример:

   ```console
   cd ~/Projects/HelloWorld/HelloWorld/bin/Release/netcoreapp3.1/publish/
   ```

1. Запустите приложение с помощью команды `dotnet`:

   1. Введите `dotnet HelloWorld.dll` и нажмите клавишу <kbd>ВВОД</kbd>.

   1. В ответ на запрос введите имя и нажмите любую клавишу, чтобы выйти.

## <a name="additional-resources"></a>Дополнительные ресурсы

- [Развертывание приложений .NET Core](../deploying/index.md)

## <a name="next-steps"></a>Следующие шаги

В этом руководстве вы опубликовали консольное приложение. Далее вы создадите библиотеку классов.

> [!div class="nextstepaction"]
> [Создание библиотеки .NET Standard с помощью Visual Studio для Mac](library-with-visual-studio-mac.md)
