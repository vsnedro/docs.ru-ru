---
title: Контрольный список развертывания .NET в конфигурации Azure
description: В этом разделе приводится краткий обзор всех средств, которые требуется установить для разработки приложений .NET с помощью Azure
ms.date: 1/1/2021
ms.topic: conceptual
ms.custom: devx-track-dotnet
ms.author: daberry
author: daberry
ms.openlocfilehash: 2f22f69ec99baf192d1cbdd28f884b7f47867389
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257984"
---
# <a name="net-on-azure-development-environment-checklist"></a>Контрольный список развертывания .NET в среде разработки Azure

С помощью этого контрольного списка вы можете убедиться, что среда разработки правильно настроена для разработки приложений .NET с помощью Azure.

## <a name="create-an-azure-account"></a>Создание учетной записи Azure

Для доступа к службам Azure или запуска приложений в Azure потребуется учетная запись Azure.

* Если вы являетесь подписчиком Visual Studio, вы будете получать ежемесячные [бесплатные кредиты Azure](https://azure.microsoft.com/pricing/member-offers/credit-for-visual-studio-subscribers/).
* [Создайте бесплатную учетную запись Azure](https://azure.microsoft.com/free/dotnet/), получите кредиты в размере $200 и выберите бесплатные службы на 12-месячный период.
* Используйте учетную запись, назначенную вам администратором Azure вашей компании.

## <a name="configure-your-ide"></a>Настройка интегрированной среды разработки (IDE)

Для популярных средств, таких как Visual Studio и Visual Studio Code, есть расширения, позволяющие работать с Azure прямо из интегрированной среды разработки.

* [Настройте Visual Studio](./configure-visual-studio.md) для разработки приложений .NET с помощью Azure.
* [Настройте Visual Studio Code](./configure-vs-code.md) для разработки приложений .NET с помощью Azure.

## <a name="install-the-azure-cli"></a>Установка Azure CLI

В дополнение к порталу Azure вам может потребоваться установить Azure CLI для создания ресурсов Azure и управления ими.

* [Установка Azure CLI для Windows](/cli/azure/install-azure-cli-windows?tabs=azure-cli)
* [Установка Azure CLI для macOS](/cli/azure/install-azure-cli-macos)
* [Установка Azure CLI для Linux](/cli/azure/install-azure-cli-linux)

## <a name="install-additional-tools-and-utilities"></a>Установка дополнительных инструментов и служебных программ

Эти дополнительные средства предназначены для повышения эффективности работы с Azure.

* [Установите Azure PowerShell](/powershell/azure/install-az-ps), если вы планируете использовать скрипты PowerShell для создания ресурсов Azure и управления ими.
* [Установите обозреватель службы хранилища Azure](https://azure.microsoft.com/features/storage-explorer/) для отправки и скачивания данных в ресурсах службы хранилища Azure, включая большие двоичные объекты, очереди, таблицы и базы данных CosmosDB, а также для управления такими данными.
* [Установите Azure Data Studio](/sql/azure-data-studio/download-azure-data-studio) для работы с Azure SQL.

## <a name="bookmark-the-following-sites"></a>Полезные сайты

При разработке с помощью Azure вам могут часто требоваться следующие сайты.  Добавьте их в закладки для быстрого доступа.

* Портал Azure — [https://portal.azure.com/](https://portal.azure.com/)
* Azure Cloud Shell — [https://shell.azure.com/](https://shell.azure.com/)
