---
title: Настройка Visual Studio для разработки Azure с помощью .NET
description: Сведения в этой статье помогут вам настроить Visual Studio для разработки Azure, включая получение правильных рабочих нагрузок и подключение Visual Studio к учетной записи Azure
ms.date: 11/30/2020
ms.topic: conceptual
ms.custom: devx-track-dotnet
ms.author: daberry
author: daberry
ms.openlocfilehash: 986469bd07657d968045465803047dc21d76dd62
ms.sourcegitcommit: 3d6d6595a03915f617349781f455f838a44b0f44
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2020
ms.locfileid: "97701037"
---
# <a name="configure-visual-studio-for-azure-development-with-net"></a>Настройка Visual Studio для разработки Azure с помощью .NET

Visual Studio включает инструментарий, помогающий в разработке и развертывании приложений в Azure.  Данное руководство поможет правильно настроить Visual Studio для разработки Azure.

### <a name="download-visual-studio-2019"></a>Скачивание Visual Studio 2019

Вы можете пропустить этот шаг, если уже установили Visual Studio 2019.

> [!div class="nextstepaction"]
> [Скачивание Visual Studio 2019](https://www.visualstudio.com/downloads/)

### <a name="install-azure-workloads"></a>Установка рабочих нагрузок Azure

Запустите **Visual Studio Installer** и проверьте, что установлены рабочие нагрузки **Разработка Azure** и **ASP.NET и веб-разработка**.  Если какая-либо из этих рабочих нагрузок не установлена, выберите эти рабочие нагрузки, чтобы установить их.

![Снимок экрана Visual Studio Installer с выбранными рабочими нагрузками "Разработка Azure" и "ASP.NET и веб-разработка".](./media/visual-studio-installer-azure-development.png)

### <a name="authenticate-visual-studio-with-azure"></a>Проверка подлинности Visual Studio в Azure

При отладке приложений в Visual Studio может использоваться учетная запись Azure для проверки подлинности и доступа к ресурсам Azure.  Эта учетная запись также используется при публикации приложений непосредственно из Visual Studio в Azure.

Чтобы проверить подлинность учетной записи Azure из Visual Studio, выберите меню **Сервис** > **Параметры**, чтобы открыть диалоговое окно **Параметры**. Перейдите к параметрам `Azure Service Authentication` и выполните вход с помощью учетной записи Azure.

![Снимок экрана: диалоговое окно параметров Visual Studio, в котором отображается имя для входа Azure](./media/visual-studio-azure-login-dialog.png)

### <a name="next-steps"></a>Дальнейшие действия

Если вы также используете [Visual Studio Code](https://code.visualstudio.com/) для разработки на .NET или на любом другом языке, необходимо также [настроить Visual Studio Code для разработки Azure](./configure-vs-code.md). В противном случае перейдите к [установке Azure CLI](./install-azure-cli.md).
