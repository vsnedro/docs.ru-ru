---
title: Установка локализованных файлов IntelliSense
description: Узнайте, как настроить на компьютере разработки использование локализованных файлов IntelliSense для проектов .NET 5+ (включая .NET Core) в Visual Studio.
ms.date: 11/06/2020
ms.openlocfilehash: 121439199f0de6d29a18ea55031976680fc1f833
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94439824"
---
# <a name="how-to-install-localized-intellisense-files-for-net"></a>Установка локализованных файлов IntelliSense для .NET

[IntelliSense](/visualstudio/ide/using-intellisense) — это вспомогательное средство для завершения кода, доступное в различных интегрированных средах разработки (IDE), таких как Visual Studio. По умолчанию при разработке проектов .NET в пакет SDK входит только английская версия файлов IntelliSense. В этой статье описано, как выполнить следующие задачи.

- Установка локализованной версии файлов.
- Изменение установки Visual Studio для использования другого языка.

## <a name="prerequisites"></a>Необходимые компоненты

- [Пакет SDK для .NET Core 3.0](https://dotnet.microsoft.com/download/dotnet-core) или более поздней версии, например [пакет SDK для .NET 5](https://dotnet.microsoft.com/download/dotnet/5.0).
- [Visual Studio 2019 версии 16.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) или более поздней версии.

## <a name="download-and-install-the-localized-intellisense-files"></a>Скачивание и установка локализованных файлов IntelliSense

> [!IMPORTANT]
> Эта процедура требует наличия прав администратора, чтобы копировать файлы IntelliSense в папку установки .NET.

1. Перейдите на страницу [скачивания файлов IntelliSense](https://dotnet.microsoft.com/download/intellisense).

1. Скачайте файл IntelliSense для нужных языка и версии.

1. Извлеките содержимое ZIP-файла.

1. Перейдите в папку IntelliSense для .NET.

   1. Перейдите в папку установки .NET. Ее расположение по умолчанию: *%ProgramFiles%\dotnet\packs*.
   1. Выберите пакет SDK, для которого необходимо установить IntelliSense, и перейдите по соответствующему пути. Можно выбрать один из следующих параметров.

      | Тип пакета SDK              | Путь                               |
      |-----------------------|------------------------------------|
      | .NET версии 5 или выше и .NET Core | *Microsoft.NETCore.App.Ref*        |
      | Классические приложения       | *Microsoft.WindowsDesktop.App.Ref* |
      | .NET Standard         | *NETStandard.Library.Ref*          |

   1. Перейдите к версии, для которой необходимо установить локализованные файлы IntelliSense. Например, *3.1.0*.
   1. Откройте папку *ref*.
   1. Откройте папку моникера. Например: *net5.0*.

   Таким образом, полный путь для перехода будет выглядеть примерно так: *C:\Program Files\dotnet\packs\Microsoft.NETCore.App.Ref\5.0.0\ref\net5.0*.

1. В открытой папке моникера создайте вложенную папку. Имя папки указывает, какой язык будет использоваться. В следующей таблице приводятся различные варианты.

   | Язык              | Имя папки |
   | --------------------- | ----------- |
   | Португальский (Бразилия)  | *pt-br*     |
   | Китайский (упрощенное письмо)  | *zh-hans*   |
   | Китайский (традиционное письмо) | *zh-hant*   |
   | Французский                | *fr*        |
   | Немецкий                | *de*        |
   | Итальянский               | *it*        |
   | Японский              | *ja*        |
   | Корейский                | *ko*        |
   | Русский               | *ru*        |
   | Испанский               | *es*        |

1. Скопируйте в эту новую папку файлы *.xml* , извлеченные на шаге 3. Файлы *.xml* распределяются по папкам пакетов SDK, поэтому скопируйте их в соответствующий SDK, выбранный на шаге 4.

## <a name="modify-visual-studio-language"></a>Изменение языка Visual Studio

Чтобы в Visual Studio использовать другой язык для IntelliSense, необходимо установить соответствующий языковой пакет. Это можно сделать [во время установки](/visualstudio/install/install-visual-studio#step-6---install-language-packs-optional) или позднее, изменив установку Visual Studio. Если среда Visual Studio уже настроена с нужным вам языком, установка IntelliSense также будет готова.

### <a name="install-the-language-pack"></a>Установка языкового пакета

Если нужный языковой пакет не был установлен, обновите Visual Studio, как показано ниже.

> [!IMPORTANT]
> Чтобы установить, обновить или изменить среду Visual Studio, необходимо войти в учетную запись с правами администратора. Дополнительные сведения см. в статье [Разрешения пользователей и Visual Studio](/visualstudio/ide/user-permissions-and-visual-studio).

1. Найдите установщик Visual Studio на своем компьютере.

   Например, на компьютере с Windows 10 нажмите кнопку **Пуск** и прокрутите список до буквы **V** , где расположен пункт **Visual Studio Installer**.

   ![Открытие Visual Studio Installer в Windows](./media/localized-intellisense/vs-installer-windows-start.png)

   > [!NOTE]
   > Кроме того, Visual Studio Installer можно найти в следующем расположении:
   >
   > `C:\Program Files (x86)\Microsoft Visual Studio\Installer\vs_installer.exe`

   Для продолжения работы может потребоваться обновление самого установщика. Если это так, следуйте инструкциям на экране.

1. В установщике найдите установленный у вас выпуск Visual Studio, для которого нужно добавить языковой пакет, и щелкните **Изменить**.

   ![Обновление или изменение Visual Studio](./media/localized-intellisense/vs-installer-modify.png)

   > [!IMPORTANT]
   > Если кнопка **Изменить** отсутствует, но доступна кнопка **Обновить** , необходимо обновить Visual Studio и лишь затем изменить установку.
   > После завершения обновления должна появиться кнопка **Изменить**.

1. На вкладке **Языковые пакеты** выберите языки, которые нужно установить, или отмените выбор тех, которые нужно удалить.

   ![Вкладка "Языковые пакеты" в Visual Studio](./media/localized-intellisense/vs-modify-language-packs.png)

1. Выберите **Изменить**. Начнется обновление.

### <a name="modify-language-settings-in-visual-studio"></a>Изменение языковых параметров в Visual Studio

После установки нужных языковых пакетов измените параметры Visual Studio для использования другого языка, как описано ниже.

1. Запустите Visual Studio.

1. В начальном окне выберите **Продолжить без кода**.

1. В строке меню выберите **Сервис** > **Параметры**. Откроется диалоговое окно "Параметры ".

1. В узле **Среда** выберите **Выбор языка**.

1. В раскрывающемся списке **Язык** выберите язык. Нажмите кнопку **ОК**.

1. Появится диалоговое окно, информирующее о необходимости перезапуска Visual Studio для применения изменений. Нажмите кнопку **ОК**.

1. Перезапустите Visual Studio.

Теперь при открытии проекта .NET, предназначенного для версии только что установленных файлов IntelliSense, функции IntelliSense должны работать надлежащим образом.

## <a name="see-also"></a>См. также раздел

- [IntelliSense в Visual Studio](/visualstudio/ide/using-intellisense)
