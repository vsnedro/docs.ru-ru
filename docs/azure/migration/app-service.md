---
title: Перенос веб-приложения или службы .NET в Службу приложений Azure
description: Узнайте о миграции веб-приложения или сервиса .NET из предварительного приложения в Службу приложений Azure.
ms.topic: conceptual
ms.date: 08/11/2018
ms.openlocfilehash: c9ef679743ce00add422110b11f2bfbdd8343530
ms.sourcegitcommit: b75a45f0cfe012b71b45dd9bf723adf32369d40c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "81433238"
---
# <a name="migrate-your-net-web-app-or-service-to-azure-app-service"></a>Перенос веб-приложения или службы .NET в Службу приложений Azure

[App Service](https://docs.microsoft.com/azure/app-service/app-service-web-overview#why-use-web-apps) — это полностью управляемый сервис вычислительной платформы, оптимизированный для хостинга масштабируемых веб-сайтов и веб-приложений. В этой статье приводится информация о том, как поднять и перенести существующее приложение в службу приложений Azure, изменения для рассмотрения и дополнительные ресурсы для [перехода в облако.](https://azure.microsoft.com/migration/web-applications/) Большинство веб-сайтов ASP.NET (WebForms, MVC) и служб (веб-API, WCF) можно переместить в Службу приложений Azure без каких-либо изменений. Для некоторых могут потребоваться незначительные изменения, в то время как для других может понадобиться рефакторинг.

Готовы начать работу? [Опубликуйте свое приложение ASP.NET + SQL в службе приложений Azure](https://tutorials.visualstudio.com/azure-webapp-migrate/intro).

## <a name="considerations"></a>Особенности

### <a name="on-premises-resources-including-sql-server"></a>Локальные ресурсы (включая SQL Server)

Проверьте доступ к локальным ресурсам, так как их, возможно, потребуется перенести или изменить. Вот несколько вариантов действий для упрощения доступа к локальным ресурсам:

* С помощью службы [Виртуальная сеть Azure](https://docs.microsoft.com/azure/app-service/web-sites-integrate-with-vnet) создайте сеть VPN для подключения Службы приложений к локальным ресурсам.
* С помощью [Azure Relay](https://docs.microsoft.com/azure/service-bus-relay/relay-what-is-it) предоставьте облаку защищенный доступ к локальным службам, не внося изменения в брандмауэр.
* Перенесите зависимости в Azure (например, [базу данных SQL](https://go.microsoft.com/fwlink/?linkid=863217)).
* Используйте предложения платформы как услуги в облаке для уменьшения зависимостей. Например, вместо подключения к локальному почтовому серверу используйте [SendGrid](https://docs.microsoft.com/azure/sendgrid-dotnet-how-to-send-email).

### <a name="port-bindings"></a>Привязки портов

Служба приложений Azure поддерживает порт 80 для HTTP-трафика и порт 443 для HTTPS-трафика.

Для WCF поддерживаются такие привязки:

Привязка | Примечания
--------|--------
BasicHttp |
WSHttp |
WSDualHttpBinding | Необходимо включить [поддержку веб-сокетов](https://docs.microsoft.com/azure/app-service/web-sites-configure).
NetHttpBinding | Необходимо включить [поддержку веб-сокетов](https://docs.microsoft.com/azure/app-service/web-sites-configure) для дуплексных контрактов.
NetHttpsBinding | Необходимо включить [поддержку веб-сокетов](https://docs.microsoft.com/azure/app-service/web-sites-configure) для дуплексных контрактов.
BasicHttpContextBinding |
WebHttpBinding |
WSHttpContextBinding |

### <a name="authentication"></a>Проверка подлинности

Служба приложений Azure поддерживает анонимную аутентификацию по умолчанию. При необходимости можно настроить аутентификацию с помощью форм. Аутентификация Windows может использоваться только при интеграции с Azure Active Directory и ADFS. [Подробнее об интеграции локальных каталогов с Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).

### <a name="assemblies-in-the-gac-global-assembly-cache"></a>Сборки в глобальном кэше сборок (GAC)

Эта возможность не поддерживается. Рассмотрите возможность копирования необходимых сборок в папку *приложения «Зуб».* Пользовательские файлы *.msi,* установленные на сервере (например, генераторы PDF), не могут быть использованы.

### <a name="iis-settings"></a>Параметры служб IIS
Теперь все параметры приложения, которые традиционно настраиваются с помощью файла applicationHost.config, можно настроить на портале Azure. Это относится к битне AppPool, включить / отключить WebSockets, управляемая версия конвейера, .NET Framework версии (2.0/4.0), и так далее. Чтобы изменить [параметры приложения](https://docs.microsoft.com/azure/app-service/web-sites-configure), перейдите на [портал Azure](https://portal.azure.com), откройте колонку нужного веб-приложения и выберите вкладку **Параметры приложения**.

#### <a name="iis5-compatibility-mode"></a>Режим совместимости с IIS5
Режим совместимости с IIS5 не поддерживается. В Azure App Service каждое веб-приложение и все приложения под ним работают в одном и том же процессе работы с определенным набором [пулов приложений.](https://technet.microsoft.com/library/cc735247(v=WS.10).aspx)

#### <a name="iis7-schema-compliance"></a>Соответствие схеме IIS7+  
Некоторые элементы и атрибуты не определены в схеме IIS Службы приложений Azure. При возникновении проблем рекомендуется использовать [преобразования XDT](https://azure.microsoft.com/documentation/articles/web-sites-transform-extend/).

#### <a name="single-application-pool-per-site"></a>Один пул приложений на сайт  
В Azure App Service каждое веб-приложение и все приложения под ним работают в одном пуле приложений. Рассмотрите возможность создания единого пула приложений с общими настройками или создания отдельного веб-приложения для каждого приложения.

### <a name="com-and-com-components"></a>Компоненты COM и COM+  
Служба приложений Azure не разрешает регистрацию COM-компонентов на платформе. Если ваше приложение использует какие-либо компоненты COM, они должны быть переписаны в управляемом коде и развернуты с помощью сайта или приложения.

### <a name="physical-directories"></a>Физические каталоги
Служба приложений Azure не разрешает доступ к физическим дискам. Возможно, вам придется использовать [файлы Azure](https://docs.microsoft.com/azure/storage/files/storage-files-introduction) для доступа к файлам через SMB. Доступ к файлам в [хранилище BLOB-объектов Azure](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) осуществляется по протоколу HTTPS.

### <a name="isapi-filters"></a>Фильтры ISAPI  
Служба приложений Azure может поддерживать использование фильтров ISAPI, но для этого вместе с сайтом необходимо развернуть DLL-библиотеку ISAPI и зарегистрировать ее с помощью файла web.config.

### <a name="https-bindings-and-ssl"></a>HTTPS-привязки и SSL
Привязки HTTPS не мигрируют, равно как и сертификаты SSL, связанные с вашими веб-сайтами. но после переноса сайта [SSL-сертификаты можно будет передать вручную](https://docs.microsoft.com/azure/app-service/app-service-web-tutorial-custom-ssl).

### <a name="sharepoint-and-frontpage"></a>SharePoint и FrontPage
Расширения SharePoint и серверные расширения FrontPage (FPSE) не поддерживаются.

### <a name="web-site-size"></a>Размер веб-сайта  
Максимальный размер содержимого на бесплатном сайте не должен превышать 1 ГБ. Если размер сайта превышает 1 ГБ, необходимо перейти на платный SKU. См. [цены на Службу приложений](https://azure.microsoft.com/pricing/details/app-service/windows/).

### <a name="database-size"></a>Размер базы данных  
Для баз данных SQL Server см. [цены на Базу данных SQL](https://azure.microsoft.com/pricing/details/sql-database).

### <a name="azure-active-directory-aad-integration"></a>Интеграция с Azure Active Directory (AAD)  
AAD не работает с бесплатными приложениями. Для использования AAD необходимо перевести приложение на платный SKU. См. [цены на Службу приложений](https://azure.microsoft.com/pricing/details/app-service/windows/).

### <a name="monitoring-and-diagnostics"></a>Мониторинг и диагностика
Решения для мониторинга и диагностики, которые вы используете сейчас в локальной среде, вряд ли будут работать в облаке. Но Azure предоставляет средства для ведения журнала, мониторинга и диагностики, позволяющие определять и устранять проблемы, связанные с веб-приложениями. Диагностику веб-приложения можно без труда включить в его конфигурации, а записи журналов доступны для просмотра в Azure Application Insights. [Подробнее о включении ведения журнала диагностики для веб-приложений](https://docs.microsoft.com/azure/app-service/web-sites-enable-diagnostic-log).

### <a name="connection-strings-and-application-settings"></a>Строки подключения и параметры приложения
Рекомендуется использовать [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/). Это служба, в которой надежно хранятся конфиденциальные сведения, используемые в вашем приложении. Кроме того, эти данные можно хранить в настройках службы приложений.

### <a name="dns"></a>DNS
Возможно, вам понадобится обновить конфигурацию DNS в соответствии с требованиями приложения. Эти параметры DNS можно настроить в [параметрах личного домена](https://docs.microsoft.com/azure/app-service/app-service-web-tutorial-custom-domain) службы приложений.

## <a name="azure-app-service-with-windows-containers"></a>Служба приложений Azure с контейнерами Windows
Если приложение не удается перенести непосредственно в Службу приложений, попробуйте воспользоваться Службой приложений с контейнерами Windows. Это даст возможность использовать GAC, COM-компоненты, пакеты MSI, даст полный доступ к API-интерфейсам .NET FX, DirectX и др.

## <a name="see-also"></a>См. также

* [Как определить, соответствует ли ваше приложение требованиям службы приложений?](https://appmigration.microsoft.com/)
* [Перенос базы данных в облако.](https://go.microsoft.com/fwlink/?linkid=863217)
* [Лазурное веб-приложение песочнице детали и ограничения](https://github.com/projectkudu/kudu/wiki/Azure-Web-App-sandbox)
