---
description: 'Дополнительные сведения о: размещение в службы IIS'
title: Размещение в службах IIS
ms.date: 03/30/2017
helpviewer_keywords:
- hosting services [WCF], IIS
ms.assetid: ddae14e8-143c-442d-b660-2046809b2d43
ms.openlocfilehash: 23c81bcfccba316500d333d277907d66e5d457c7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99743139"
---
# <a name="host-in-internet-information-services"></a>Размещение в службы IIS

Один из вариантов размещения служб Windows Communication Foundation (WCF) находится внутри приложения службы IIS (IIS). Эта модель размещения похожа на модель, используемую веб-службами ASP.NET и ASP.NET Web Services (ASMX).

## <a name="versions-of-iis"></a>Версии IIS

WCF может размещаться на следующих версиях служб IIS в следующих операционных системах:

- IIS 5,1 в Windows XP с пакетом обновления 2 (SP2). Эта среда полезна при проектировании и разработке приложений, размещенных в IIS, которые позже развертываются в серверной операционной системе, такой как Windows Server 2003.

- IIS 6,0 на Windows Server 2003. IIS 6,0 предоставляет расширенную модель процессов, обеспечивающую улучшенную масштабируемость, надежность и изоляцию приложений. Эта среда подходит для рабочего развертывания служб WCF, использующих исключительно обмен данными по протоколу HTTP.

- IIS 7,0 в Windows Vista и Windows Server 2008. IIS 7,0 предоставляет ту же модель расширенных процессов, что и IIS 6,0, но использует службу активации процессов Windows (WAS), чтобы обеспечить активацию и сетевую связь по протоколам, отличным от HTTP. Эта среда подходит для разработки служб WCF, взаимодействующих по любому сетевому протоколу, поддерживаемому WCF (включая HTTP, net. TCP, net. pipe и net. MSMQ). Дополнительные сведения о WAS см. [в разделе Размещение в службе активации Windows](hosting-in-windows-process-activation-service.md).

- [Windows Server AppFabric](/previous-versions/appfabric/ff384253(v=azure.10)) работает с IIS 7,0 и службой активации Windows (WAS), чтобы предоставить обширную среду размещения приложений для служб NET4 WCF и WF. К ее преимуществам относятся управление жизненным циклом, перезапуск процессов, совместное размещение, быстрая защита от сбоев, обработка потерянных процессов, активация по запросу и наблюдение за работоспособностью. Подробные сведения см. в разделе [функции размещения AppFabric](/previous-versions/appfabric/ee677189(v=azure.10)) и [Основные понятия размещения AppFabric](/previous-versions/appfabric/ee677371(v=azure.10)).

## <a name="benefits-of-iis-hosting"></a>Преимущества размещения служб IIS

Размещение служб WCF в IIS имеет несколько преимуществ:

- Службы WCF, размещенные в IIS, развертываются и управляются как любые другие типы приложений IIS, включая приложения ASP.NET и ASMX.

- службы IIS предоставляют функции активации процессов, управления работоспособностью и перезапуска процессов, что позволяет повысить надежность приложений;

- Как и ASP.NET, службы WCF, размещенные в ASP.NET, могут использовать преимущества общей модели размещения ASP.NET, в которой несколько приложений находятся в общем рабочем процессе для повышения плотности и масштабируемости серверов.

- Службы WCF, размещенные в IIS, используют ту же динамическую модель компиляции, что и ASP.NET 2,0, что упрощает разработку и развертывание размещенных служб.

При принятии решения о размещении служб WCF в IIS важно помнить, что IIS 5,1 и IIS 6,0 ограничены только HTTP-связью. Дополнительные сведения о выборе среды размещения см. в разделе [службы хостинга](../hosting-services.md).

## <a name="deploy-an-iis-hosted-wcf-service"></a>Развертывание размещенной в IIS службы WCF

Разработка и развертывание службы WCF, размещенной в IIS, состоит из следующих задач.

- Убедитесь, что службы IIS, ASP.NET, WCF и компонент активации HTTP WCF правильно установлены и зарегистрированы.

- Создайте новое приложение IIS или повторно используйте существующее приложение ASP.NET.

- Создайте SVC-файл для службы WCF.

- Развертывание реализации службы в приложение IIS.

- Настройте службу WCF.

Обсуждение каждой из этих задач см. в разделе [Deploying an Internet Information Services-Hosted WCF Service](deploying-an-internet-information-services-hosted-wcf-service.md).

## <a name="wcf-services-and-aspnet"></a>Службы WCF и ASP.NET

Службы WCF могут размещаться либо параллельно с ASP.NET, либо в режиме совместимости ASP.NET, в котором службы могут использовать все преимущества функций, предоставляемых платформой веб-приложений ASP.NET. Описание этих функций см. в разделе [WCF Services and ASP.NET](wcf-services-and-aspnet.md).

## <a name="see-also"></a>См. также

- [Расширение размещения с использованием ServiceHostFactory](../extending/extending-hosting-using-servicehostfactory.md)
- [Развертывание службы WCF, размещенной в IIS](deploying-an-internet-information-services-hosted-wcf-service.md)
- [Службы WCF и ASP.NET](wcf-services-and-aspnet.md)
- [Рекомендации по размещению в службах IIS](internet-information-services-hosting-best-practices.md)
- [Настройка IIS 7.0 для Windows Communication Foundation](configuring-iis-for-wcf.md)
- [Функции размещения Windows Server App Fabric](/previous-versions/appfabric/ee677189(v=azure.10))
