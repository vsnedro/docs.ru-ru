---
title: Средства для разработчиков Azure .NET
description: Получите средства для работы с библиотеками Azure для .NET в среде Windows, Mac и Linux.
ms.date: 06/19/2020
ms.custom: azure-sdk-dotnet
ms.openlocfilehash: fa645b152f15550b25a3542ba0cdbb43799536b9
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174854"
---
# <a name="azure-tools-for-developing-with-net"></a>Средства Azure для разработки с использованием .NET

## <a name="sdk-downloads"></a>Скачиваемые пакеты SDK

Библиотеки Azure для .NET реализуются как [пакеты NuGet](https://www.nuget.org/packages?q=windowsazureofficial). Справочную документацию, упорядоченную по службам Azure, см. в [справочнике по API](/dotnet/api/overview/azure/?view=azure-dotnet).

## <a name="development-tools"></a>Инструменты разработки

Visual Studio содержит встроенный инструментарий для многих служб Azure. Для некоторых служб Azure доступны дополнительные средства или эмуляторы, например [Обозреватель службы хранилища Azure](https://azure.microsoft.com/features/storage-explorer/). При необходимости ознакомьтесь с документацией по соответствующей службе Azure.

Выберите предпочитаемую среду разработки ниже.

## <a name="visual-studio-on-windows"></a>[Visual Studio в Windows](#tab/vs)

В Visual Studio 2017 и более поздних версий есть встроенная поддержка средств разработки для Azure. Ниже описано, как включить поддержку средств разработки Azure в Visual Studio.

В Visual Studio 2015 и более ранних версий <a href="vs2015-install.md">следуйте этим инструкциям</a>.

### <a name="step-1-download-visual-studio-2019"></a>Шаг 1. Скачивание Visual Studio 2019

Вы можете пропустить этот шаг, если уже установили Visual Studio 2019.

> [!div class="nextstepaction"]
> [Скачивание Visual Studio 2019](https://www.visualstudio.com/downloads/)

### <a name="step-2-install-the-two-azure-workloads"></a>Шаг 2. Установка двух рабочих нагрузок Azure

В установщике Visual Studio установите Visual Studio (или измените существующую установку). Убедитесь, что выбраны рабочие нагрузки *Разработка Azure* и *Веб-разработка и разработка ASP.NET*.

### <a name="step-3-develop-with-net-on-azure"></a>Шаг 3. Разработка с помощью .NET в Azure

Начните с [развертывания первого веб-приложения ASP.NET Core в Службе приложений Azure](/azure/app-service-web/app-service-web-get-started-dotnet).

## <a name="visual-studio-code-cross-platform"></a>[Visual Studio Code (кроссплатформенная среда)](#tab/vscode)

В Visual Studio Code есть все необходимое для кроссплатформенной разработки в Azure.

### <a name="step-1-download-the-net-core-sdk"></a>Шаг 1. Скачать пакет SDK .NET Core

Пакет SDK и средства командной строки для приложений .NET Core.

> [!div class="nextstepaction"]
> [Скачать пакет SDK для .NET Core](https://dotnet.microsoft.com/download)

### <a name="step-2-visual-studio-code"></a>Шаг 2. Visual Studio Code

Изменение и отладка приложений .NET Core в любой операционной системе: Windows, Mac и Linux.

> [!div class="nextstepaction"]
> [Скачать Visual Studio Code](https://code.visualstudio.com)

### <a name="step-3-azure-tools-extension"></a>Шаг 3. Расширение Azure Tools

Установите расширение Azure Tools в Visual Studio Code.

> [!div class="nextstepaction"]
> [Установка расширения Azure Tools](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-node-azure-pack)

### <a name="step-4-develop-with-net-on-azure"></a>Шаг 4. Разработка с помощью .NET в Azure

Начните с [развертывания первого веб-приложения ASP.NET Core в Службе приложений Azure в Linux](/azure/app-service/containers/quickstart-dotnetcore).

---
