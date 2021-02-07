---
description: 'Дополнительные сведения: основные коммуникации: поддержка WebHost'
title: 'Основное взаимодействие: Поддержка WebHost'
ms.date: 03/30/2017
ms.assetid: 034c501f-96f9-4ef7-9602-3ac21788fd3e
ms.openlocfilehash: c132527caf4d08b7423ff8af9442ca609d4e645f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99686522"
---
# <a name="core-communications-webhost-support"></a>Основное взаимодействие: Поддержка WebHost

В этом разделе перечислены все исключения, вызываемые средствами поддержки Webhost.

## <a name="exception-list"></a>Список исключений

|Код ресурса|Строка ресурса|
|-------------------|---------------------|
|Hosting_CompatibilityServiceNotHosted|Эта служба требует совместимости с ASP.NET. Она должна также быть размещена в IIS. Либо разместите службу в IIS с включенной совместимостью с ASP.NET в файле Web.config, либо задайте для свойства AspNetCompatibilityRequirementsAttribute.AspNetCompatibilityRequirementsMode значение, отличное от "Required".|
|Hosting_ListenerNotFoundForActivationInRecycling|В настоящее время ни один канал не ожидает передачу данных на заданном адресе. Если приложение перезапускается, служба закрывается.|
|Hosting_NonHTTPInCompatibilityMode|При совместимости с ASP.NET поддерживаются только протоколы HTTP и HTTPS. Удалите указанную конечную точку или отключите совместимость с ASP.NET для приложения.|
|Hosting_ProcessNotExecutingUnderHostedContext|Указанный ведущий процесс не может быть вызван в текущей среде размещения. Этот API требует, чтобы вызывающее приложение было размещено в службах IIS или в службе активации Windows.|
|Hosting_ServiceCompatibilityRequire|Активировать службу невозможно, поскольку она требует совместимости с ASP.NET. Совместимость с ASP.NET для этого приложения не включена. Либо включите совместимость с ASP.NET в файле Web.config, либо установите AspNetCompatibilityRequirementsAttribute.AspNetCompatibility.|
