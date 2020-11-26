---
title: Учебник. Начало работы с Windows Communication Foundation приложениями
description: В этих руководствах содержатся общие сведения о создании приложений WCF.
ms.date: 01/25/2019
helpviewer_keywords:
- WCF [WCF], get started
- Windows Communication Foundation [WCF], get started
- get started [WCF]
ms.assetid: df939177-73cb-4440-bd95-092a421516a1
ms.openlocfilehash: 620a83260f01e27a19b19227165695a621c88e5e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238240"
---
# <a name="tutorial-get-started-with-windows-communication-foundation-applications"></a>Учебник. Начало работы с Windows Communication Foundation приложениями

В приведенной ниже серии руководств представлены инструкции по программированию Windows Communication Foundation (WCF). При работе с этими учебниками вы получите вводные сведения о шагах, необходимых для создания приложений WCF. После завершения работы у вас будет работающая служба WCF и клиент WCF, который вызывает службу.

В учебнике предполагается, что вы используете Visual Studio в качестве среды разработки. Если вы используете другую среду разработки, пропустите инструкции, относящиеся к Visual Studio.

Примеры приложений WCF, которые можно скачать и запустить, см. в разделе [Windows Communication Foundation Samples](samples/index.md). Общие сведения о примерах см. в статье [Приступая к работе](samples/getting-started-sample.md).

Более подробные сведения о создании служб и клиентов см. в разделе [Базовая программирование WCF](basic-wcf-programming.md).

## <a name="wcf-tutorials"></a>Учебники по WCF

В первых трех руководствах описывается, как определить контракт службы WCF, как его реализовать и как разместить его. Создаваемая служба является саморазмещенной в консольном приложении. Службы также можно размещать в Microsoft службы IIS (IIS). Дополнительные сведения см. в разделе [инструкции. размещение службы WCF в IIS](feature-details/how-to-host-a-wcf-service-in-iis.md). Хотя для настройки службы в этом учебнике используется код, можно также [настроить службы в файле конфигурации](configuring-services-using-configuration-files.md).

- [Учебник. определение контракта службы](how-to-define-a-wcf-service-contract.md)

    Вы создаете контракт WCF с определяемым пользователем интерфейсом. Этот контракт определяет функциональные возможности, предоставляемые службой.

- [Учебник. Реализация контракта службы](how-to-implement-a-wcf-contract.md)

    После определения контракта его необходимо реализовать с помощью класса службы.

- [Учебник. размещение и запуск базовой службы](how-to-host-and-run-a-basic-wcf-service.md)

    Настройте конечную точку для службы и разместите ее в консольном приложении. Чтобы служба стала активной, ее необходимо настроить и разместить в среде выполнения. Эта среда времени выполнения создает службу и управляет ее контекстом и временем существования.

В следующих двух учебниках описывается создание, Настройка и использование клиентского приложения для вызова операций, предоставляемых службой. Службы публикуют доступные метаданные, определяющие сведения, необходимые клиентским приложениям для взаимодействия со службой. Visual Studio автоматизирует процесс доступа к этим метаданным и использует его для создания клиентского приложения для службы. Если вы решили не использовать Visual Studio, вместо этого можно использовать [средство служебной программы метаданных ServiceModel (*Svcutil.exe*)](servicemodel-metadata-utility-tool-svcutil-exe.md) .

- [Учебник. Создание клиента](how-to-create-a-wcf-client.md)

    Получите метаданные для создания прокси клиента WCF из службы WCF. Метаданные извлекаются с помощью Visual Studio для добавления ссылки на службу или можно использовать средство служебной программы метаданных ServiceModel. Укажите конечную точку, которую клиент использует для доступа к службе.

- [Учебник. Использование клиента](how-to-use-a-wcf-client.md)

    Используйте прокси клиента WCF для вызова операций службы.

## <a name="reference"></a>Справочник

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>

## <a name="see-also"></a>См. также

- [Обзор концепции](conceptual-overview.md)
- [Руководство по документации](guide-to-the-documentation.md)
- [Что такое Windows Communication Foundation](whats-wcf.md)
- [Подробные сведения о возможностях WCF](feature-details/index.md)
- [Базовый жизненный цикл программирования](basic-programming-lifecycle.md)
- [Создание клиентов](building-clients.md)
- [Базовое программирование WCF](basic-wcf-programming.md)
- [Как создать дуплексный контракт](feature-details/how-to-create-a-duplex-contract.md)
- [Руководство. доступ к службам с помощью дуплексного контракта](feature-details/how-to-access-services-with-a-duplex-contract.md)
- [Средство служебной программы метаданных ServiceModel (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Как использовать Svcutil.exe для скачивания документов метаданных](feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)
- [Инструкции. Публикация метаданных для службы с помощью файла конфигурации](feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [Использование привязок для настройки служб и клиентов](using-bindings-to-configure-services-and-clients.md)
- [Пример Приступая к работе](samples/getting-started-sample.md)
- [Примеры Windows Communication Foundation](samples/index.md)
- [Резидентное размещение](samples/self-host.md)
