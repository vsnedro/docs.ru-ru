---
title: Настройка Visual Studio Code для разработки Azure с помощью .NET
description: Сведения в этой статье помогут вам настроить Visual Studio Code для разработки Azure, включая установку и настройку соответствующих подключаемых модулей в VS Code
ms.date: 11/30/2020
ms.topic: conceptual
ms.custom: devx-track-dotnet
ms.author: daberry
author: daberry
ms.openlocfilehash: 65ced99befe12d137062b4ea6a59a1ccd3099e0b
ms.sourcegitcommit: 3d6d6595a03915f617349781f455f838a44b0f44
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2020
ms.locfileid: "97701030"
---
# <a name="configure-visual-studio-code-for-azure-development"></a>Настройка Visual Studio Code для разработки Azure

Если вы используете Visual Studio Code для разработки для .NET, создания одностраничных приложений с помощью таких платформ, как Angular, React или Vue, или для написания приложений на другом языке, например Python, вам потребуется настроить Visual Studio Code для разработки Azure.

### <a name="download-visual-studio-code"></a>Скачать Visual Studio Code

Вы можете пропустить этот шаг, если уже установили Visual Studio Code.

> [!div class="nextstepaction"]
> [Скачать Visual Studio Code](https://code.visualstudio.com/download)

### <a name="install-the-azure-tools-extension-pack"></a>Установка пакета расширений "Средства Azure"

[Пакет расширений средств Azure](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-node-azure-pack) содержит расширения для работы со Службой приложений Azure, Функциями Azure, службой хранилища Azure, Cosmos DB и виртуальными машинами Azure — все это в одном удобном пакете.

Чтобы установить расширение из Visual Studio Code, выполните указанные ниже действия.

1. Нажмите клавиши <kbd>CTRL+SHIFT+X</kbd>, чтобы открыть окно **Расширения**.
1. Выполните поиск расширения *Средства Azure*.
1. Нажмите кнопку **Установить**.

![Снимок экрана: панель расширений в Visual Studio Code, поиск пакета расширений "Средства Azure"](./media/visual-studio-code-azure-tools.png)

Дополнительные сведения об установке расширений в Visual Studio Code см. в документе [Магазин расширений](https://code.visualstudio.com/docs/editor/extension-gallery) на веб-сайте Visual Studio Code.

### <a name="sign-in-to-your-azure-account-with-azure-tools"></a>Вход в учетную запись Azure с помощью средств Azure

На панели слева вы увидите значок Azure. Выберите этот значок, после чего отобразится панель управления для служб Azure. Выберите **Войти в Azure** в любой службе, чтобы завершить процесс проверки подлинности средств Azure в Visual Studio Code.

![Снимок экрана Visual Studio Code: вход в Azure для работы со средствами Azure](./media/visual-studio-code-azure-login.png)

### <a name="next-steps"></a>Дальнейшие действия

Далее необходимо установить Azure CLI на рабочую станцию.

> [!div class="nextstepaction"]
> [Установка Azure CLI](./install-azure-cli.md)
