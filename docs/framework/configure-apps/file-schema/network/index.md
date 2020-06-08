---
title: Схема параметров сети
description: Сведения о схеме параметров сети, указывающих, как .NET Framework подключается к Интернету и обрабатывает URI.
ms.date: 03/30/2017
helpviewer_keywords:
- elements [.NET Framework], network configuration elements
- sending data, network configuration elements
- receiving data, network configuration elements
- configuration settings [.NET Framework], networks
- Internet, network configuration elements
- network configuration elements
- network settings
- connections [.NET Framework], network configuration elements
- network resources, network configuration elements
ms.assetid: f1de5a0f-76c5-4833-819f-5222b8146340
ms.openlocfilehash: 6a22d7f1608db2e8909d0ead11e9110ec8a8a2c5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504580"
---
# <a name="network-settings-schema"></a>Схема параметров сети
Параметры сети определяют способ подключения .NET Framework к Интернету.

\<system.net>Параметры указывают, как .NET Framework подключается к сети. В следующей таблице описывается функция каждого дочернего элемента конфигурации в [ \<system.Net> элементе (параметры сети)](system-net-element-network-settings.md).  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<authenticationModules>Элемент (параметры сети)](authenticationmodules-element-network-settings.md)|Определяет модули, используемые для проверки подлинности интернет-запросов.|  
|[\<connectionManagement>Элемент (параметры сети)](connectionmanagement-element-network-settings.md)|Задает максимальное число подключений к узлам в Интернете.|  
|[\<defaultProxy>Элемент (параметры сети)](defaultproxy-element-network-settings.md)|Задает прокси-сервер, используемый для HTTP-запросов к Интернету.|  
|[\<mailSettings>Элемент (параметры сети)](mailsettings-element-network-settings.md)|Содержит параметры отправки почты.|  
|[\<requestCaching>Элемент (параметры сети)](requestcaching-element-network-settings.md)|Управляет механизмом кэширования для сетевых запросов.|  
|[\<webRequestModules>Элемент (параметры сети)](webrequestmodules-element-network-settings.md)|Задает модули, используемые для запроса данных от узлов в Интернете.|  
  
\<uri>Параметры определяют, как .NET Framework обрабатывает веб-адреса, выраженные с помощью универсальных идентификаторов ресурсов (URI). В следующей таблице описывается функция каждого дочернего элемента конфигурации в [ \<uri> элементе (Параметры URI)](uri-element-uri-settings.md).  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<idn>Элемент (Параметры URI)](idn-element-uri-settings.md)|Определяет, применяется ли к доменным именам анализ международных доменных имен (IDN).|  
|[\<iriParsing>Элемент (Параметры URI)](iriparsing-element-uri-settings.md)|Определяет, применяется ли к <xref:System.Uri> анализ международных идентификаторов ресурсов (IRI) и применяются ли правила анализа IRI.|  
|[\<schemeSettings>Элемент (Параметры URI)](schemesettings-element-uri-settings.md)|Определяет, как <xref:System.Uri> анализируется для определенных схем.|  
  
## <a name="see-also"></a>См. также

- [Настройка веб-приложений](../../../network-programming/configuring-internet-applications.md)
- [Схема файла конфигурации](../index.md)
