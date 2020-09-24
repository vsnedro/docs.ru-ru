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
ms.openlocfilehash: 8071fcfcdb16b6e71d8d7af05a704d8842b3e963
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158920"
---
# <a name="network-settings-schema"></a>Схема параметров сети

Параметры сети определяют способ подключения .NET Framework к Интернету.

\<system.net>Параметры указывают, как .NET Framework подключается к сети. В следующей таблице описывается функция каждого дочернего элемента конфигурации в [ \<system.Net> элементе (параметры сети)](system-net-element-network-settings.md).  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[Элемент \<authenticationModules> (параметры сети)](authenticationmodules-element-network-settings.md)|Определяет модули, используемые для проверки подлинности интернет-запросов.|  
|[Элемент \<connectionManagement> (параметры сети)](connectionmanagement-element-network-settings.md)|Задает максимальное число подключений к узлам в Интернете.|  
|[Элемент \<defaultProxy> (параметры сети)](defaultproxy-element-network-settings.md)|Задает прокси-сервер, используемый для HTTP-запросов к Интернету.|  
|[Элемент \<mailSettings> (параметры сети)](mailsettings-element-network-settings.md)|Содержит параметры отправки почты.|  
|[Элемент \<requestCaching> (параметры сети)](requestcaching-element-network-settings.md)|Управляет механизмом кэширования для сетевых запросов.|  
|[Элемент \<webRequestModules> (параметры сети)](webrequestmodules-element-network-settings.md)|Задает модули, используемые для запроса данных от узлов в Интернете.|  
  
\<uri>Параметры определяют, как .NET Framework обрабатывает веб-адреса, выраженные с помощью универсальных идентификаторов ресурсов (URI). В следующей таблице описывается функция каждого дочернего элемента конфигурации в [ \<uri> элементе (Параметры URI)](uri-element-uri-settings.md).  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<idn> Элемент (Параметры URI)](idn-element-uri-settings.md)|Определяет, применяется ли к доменным именам анализ международных доменных имен (IDN).|  
|[\<iriParsing> Элемент (Параметры URI)](iriparsing-element-uri-settings.md)|Определяет, применяется ли к <xref:System.Uri> анализ международных идентификаторов ресурсов (IRI) и применяются ли правила анализа IRI.|  
|[\<schemeSettings> Элемент (Параметры URI)](schemesettings-element-uri-settings.md)|Определяет, как <xref:System.Uri> анализируется для определенных схем.|  
  
## <a name="see-also"></a>См. также раздел

- [Настройка веб-приложений](../../../network-programming/configuring-internet-applications.md)
- [Схема файла конфигурации](../index.md)
