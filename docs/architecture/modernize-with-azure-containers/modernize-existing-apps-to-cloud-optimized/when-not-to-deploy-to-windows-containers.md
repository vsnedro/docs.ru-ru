---
title: Технологии, не поддерживающие развертывание в контейнерах Windows
description: Модернизация существующих приложений .NET с помощью облака Azure и контейнеров Windows | Технологии, не поддерживающие развертывание в контейнерах Windows
ms.date: 12/21/2020
ms.openlocfilehash: 4eea24ab8deb3719c778b45b3ddc1309277a3f50
ms.sourcegitcommit: 5d9cee27d9ffe8f5670e5f663434511e81b8ac38
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2021
ms.locfileid: "98025177"
---
# <a name="when-not-to-deploy-to-windows-containers"></a>Технологии, не поддерживающие развертывание в контейнерах Windows

Некоторые технологии Windows не поддерживаются контейнерами Windows. В таких случаях вам по-прежнему нужно выполнить миграцию на стандартные виртуальные машины, обычно с использованием только Windows и IIS.

Сценарии, не поддерживающиеся в контейнерах Windows по состоянию на май 2018 года:

- В настоящее время технология очередей сообщений (MSMQ) доступна только в контейнерах Windows с выпуском Windows Server версии 1803, но не с предыдущими выпусками.

  - [Форум по запросам UserVoice](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/15719031-create-base-container-image-with-msmq-server)

  - [Форум обсуждения](https://social.msdn.microsoft.com/Forums/bce99a7d-aa60-44fa-a348-450855650810/msmqserver-is-it-supported?forum=windowscontainers)

- Координатор распределенных транзакций Майкрософт (MSDTC) в настоящее время не поддерживается в контейнерах Windows.

  - [Проблема, рассмотренная на сайте GitHub](https://github.com/MicrosoftDocs/Virtualization-Documentation/issues/494)

- Microsoft Office в настоящее время не поддерживает контейнеры.

  - [Форум по запросам UserVoice](https://windowsserver.uservoice.com/forums/304624-containers/suggestions/19686220-provide-office-support-for-containers)

- Приложения пользовательского интерфейса (клиентские приложения с визуальным пользовательским интерфейсом) не поддерживаются.

- Роли инфраструктуры Windows (DNS, DHCP, DC, NTP, PRINT, файловый сервер, IAM и т. д.) не поддерживаются.

Другие неподдерживаемые сценарии и запросы от сообщества см. в разделе форума UserVoice, посвященном контейнерам Windows: <https://windowsserver.uservoice.com/forums/304624-containers>.

### <a name="additional-resources"></a>Дополнительные ресурсы

- **Виртуальные машины и контейнеры в Azure**

    <https://azure.microsoft.com/overview/containers/>

> [!div class="step-by-step"]
> [Назад](deploy-existing-net-apps-as-windows-containers.md)
> [Вперед](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
