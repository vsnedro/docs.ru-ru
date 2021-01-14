---
title: Установка Azure CLI
description: Разработчикам Azure потребуется установка Azure CLI. В этой статье описывается, зачем нужен интерфейс командной строки (CLI) и откуда его можно скачать и установить.
ms.date: 11/30/2020
ms.topic: conceptual
ms.custom: devx-track-dotnet
ms.author: daberry
author: daberry
ms.openlocfilehash: aa2739cc6c11145887e64921398c72affeaec729
ms.sourcegitcommit: 5d9cee27d9ffe8f5670e5f663434511e81b8ac38
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2021
ms.locfileid: "98025033"
---
# <a name="install-the-azure-cli"></a>Установка Azure CLI

В дополнение к порталу Azure в Azure также предлагается [Azure CLI](/cli/azure/), средство командной строки для создания ресурсов Azure и управления ими. Azure CLI позволяет повысить степень эффективности и воспроизводимости повторяющихся задач, а также использовать скрипты для их выполнения.  

На практике большинство разработчиков используют и портал Azure, и Azure CLI. Портал Azure удобен для знакомства с новыми службами и обзора всех ресурсов в учетной записи Azure, но при этом большинство разработчиков считают Azure CLI более быстрым и эффективным инструментом.  Зачастую в Azure CLI с помощью одной команды можно выполнить задачу, требующую нескольких действий на портале Azure.  Кроме того, команды Azure CLI можно сохранять в файл, благодаря чему гарантируется единообразное выполнение повторяющихся задач.

Azure CLI доступен для Windows, macOS и Linux.

> [!div class="nextstepaction"]
> [Установка Azure CLI для Windows](/cli/azure/install-azure-cli-windows?tabs=azure-cli)

> [!div class="nextstepaction"]
> [Установка Azure CLI для macOS](/cli/azure/install-azure-cli-macos)

> [!div class="nextstepaction"]
> [Установка Azure CLI для Linux](/cli/azure/install-azure-cli-linux)

### <a name="azure-cloud-shell"></a>Azure Cloud Shell

Azure CLI также можно использовать в Azure Cloud Shell по адресу [https://shell.azure.com](https://shell.azure.com).  Azure Cloud Shell представляет собой полнофункциональную браузерную оболочку для управления ресурсами Azure.  Azure Cloud Shell удобно использовать в тех случаях, когда требуется среда командной строки, но работа ведется на устройстве, где нельзя установить Azure CLI.

![Снимок экрана: Azure Cloud Shell в браузере](media/azure-cloud-shell.png)

### <a name="next-steps"></a>Дальнейшие действия

Затем необходимо [установить дополнительные инструменты Azure](./azure-tools.md), такие как Обозреватель службы хранилища Azure и Azure Data Studio, чтобы повысить эффективность работы с Azure.
