---
title: Дополнительные библиотеки классов и интерфейсы API
description: Изучите дополнительные библиотеки классов и API-интерфейсы в .NET, включая проекты с внешними интерфейсами (OOB), библиотеки для конкретных платформ и частные интерфейсы API.
ms.date: 08/11/2020
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
ms.topic: conceptual
ms.openlocfilehash: c6404df5d4f0be381bc0a9c1924fcf82cf078306
ms.sourcegitcommit: 70d6a7e4f7187cbfa332f0f8be76566f7828cfcd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/11/2020
ms.locfileid: "88075479"
---
# <a name="additional-class-libraries-and-apis"></a>Дополнительные библиотеки классов и интерфейсы API

В этой статье перечислены .NET Framework интерфейсы API, которые были освобождены с помощью аппаратного контроллера управления, нацелены на определенную платформу или являются частными или внутренними типами.

## <a name="oob-projects"></a>Внештатные проекты

Чтобы улучшить разработку на разных платформах и впервые добавить новые функции, некоторые .NET Framework функции были выпущены с использованием аппаратного контроллера управления (OOB).

| Проект | Описание |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | Предоставляет потокобезопасные коллекции, содержимое которых никогда не меняется. |
| <xref:System.Net.Http.WinHttpHandler> | Предоставляет обработчик сообщений для <xref:System.Net.Http.HttpClient> на основе интерфейса WinHTTP ОС Windows. |
| <xref:System.Numerics> | Представляет собой библиотеку векторных типов, которые могут использовать преимущества аппаратного ускорения SIMD.|
| <xref:System.Threading.Tasks.Dataflow> | Библиотека потоков данных TPL предоставляет компоненты потока данных, позволяющие повысить надежность приложений с поддержкой параллелизма. |  

## <a name="platform-specific-libraries"></a>Библиотеки для конкретных платформ

Некоторые библиотеки предназначены для конкретных платформ. Например, <xref:System.Text.CodePagesEncodingProvider> класс делает кодировки кодовых страниц доступными для приложений UWP, разработанных с помощью .NET Framework.
  
| Проект | Описание |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | Расширяет <xref:System.Text.EncodingProvider> класс, чтобы сделать кодировки кодовых страниц доступными для приложений, предназначенных для универсальная платформа Windows. |  
  
## <a name="private-apis"></a>Частные интерфейсы API  

Эти API поддерживают инфраструктуру продукта и не предназначены для использования непосредственно из кода.  
  
* [Свойство Microsoft. SqlServer. Server. Смиордерпроперти. Item](microsoft.sqlserver.server.smiorderproperty.item.md)
* [Метод System. Exception. Препфорремотинг](system.exception.prepforremoting.md)
* [Свойство System. Data. SqlTypes. SqlChars. Stream](system.data.sqltypes.sqlchars.stream.md)
* [Конструктор System. Data. SqlTypes. Склстреамчарс](system.data.sqltypes.sqlstreamchars.-ctor.md)
* [Свойство System. Data. SqlTypes. Склстреамчарс. CanSeek](system.data.sqltypes.sqlstreamchars.canseek.md)
* [Свойство System. Data. SqlTypes. Склстреамчарс. IsNull](system.data.sqltypes.sqlstreamchars.isnull.md)
* [Свойство System. Data. SqlTypes. Склстреамчарс. length](system.data.sqltypes.sqlstreamchars.length.md)
* [Метод System. Data. SqlTypes. Склстреамчарс. Close](system.data.sqltypes.sqlstreamchars.close.md)
* [Метод System. Data. SqlTypes. Склстреамчарс. Dispose](system.data.sqltypes.sqlstreamchars.dispose.md)
* [Метод System. Data. SqlTypes. Склстреамчарс. Flush](system.data.sqltypes.sqlstreamchars.flush.md)
* [Метод System. Data. SqlTypes. Склстреамчарс. Read](system.data.sqltypes.sqlstreamchars.read.md)
* [Метод System. Data. SqlTypes. Склстреамчарс. Seek](system.data.sqltypes.sqlstreamchars.seek.md)
* [Метод System. Data. SqlTypes. Склстреамчарс. SetLength](system.data.sqltypes.sqlstreamchars.setlength.md)
* [Метод System. Data. SqlTypes. Склстреамчарс. Write](system.data.sqltypes.sqlstreamchars.write.md)
* [Метод System. IO. MemoryStream. Интерналжеторигинандленгс](system.io.memorystream.internalgetoriginandlength.md)
* [Класс System .NET. Комнетос](system.net.comnetos.md)
* [Класс System .NET. Connection](connection.md)
* [Поле системы .NET. Connection. m \_ врителист](m_writelist.md)
* [Класс System .NET. Коннектионграуп](connectiongroup.md)
* [System .NET. Коннектионграуп. m \_ коннектионлист, поле](m_connectionlist.md)
* [Свойство System .NET. Коннектстреам. Connection](system.net.connectstream.connection.md)
* [Класс System .NET. Коререспонседата](coreresponsedata.md)
* [System .NET. Коререспонседата. m \_ ResponseHeaders, поле](coreresponsedata_m_responseheaders.md)
* [Поле StatusCode System .NET. Коререспонседата. m \_](coreresponsedata_m_statuscode.md)
* [Класс System .NET. Ексцептионхелпер](system.net.exceptionhelper.md)
* [Класс System .NET. Хттпстатусдескриптион](system.net.httpstatusdescription.md)
* [System .NET. HttpWebRequest. \_ Поле перенаправлений](_autoredirects.md)
* [System .NET. HttpWebRequest. \_ Поле Коререспонсе](httpwebrequest__coreresponse.md)
* [System .NET. HttpWebRequest. \_ Поле HttpResponse](_httpresponse.md)
* [Класс System .NET. Logging](system.net.logging.md)
* [Класс System .NET. mail. Маиладдресспарсер](system.net.mail.mailaddressparser.md)
* [Класс System .NET. mail. Куотедпаирреадер](system.net.mail.quotedpairreader.md)
* [Класс System .NET. MIME. Маилбнфхелпер](system.net.mime.mailbnfhelper.md)
* [Свойство System .NET. Пуледстреам. NetworkStream](system.net.pooledstream.networkstream.md)
* [Класс System .NET. Рткстате](system.net.rtcstate.md)
* [Свойство System .NET. Security. Сслстате. Сслпротокол](system.net.security.sslstate.sslprotocol.md)
* [System .NET. ServicePoint. m \_ коннектионграуплист, поле](m_connectiongrouplist.md)
* [System .NET. ServicePointManager. Клосеконнектионграупс, метод](system.net.servicepointmanager.closeconnectiongroups.md)
* [Поле System .NET. ServicePointManager. s \_ сервицепоинттабле](s_servicepointtable.md)
* [Поле System .NET. Тлсстреам. m_Worker](system.net.tlsstream.m_worker.md)
* [Класс System .NET. Унсафенклнативемесодс](system.net.unsafenclnativemethods.md)
* [System .NET. Вебхеадерколлектион. Аддинтернал, метод](system.net.webheadercollection.addinternal.md)
* [Метод System. ServiceModel. Channels. Message. Бодитостринг](system.servicemodel.channels.message.bodytostring.md)
* [Метод System. ServiceModel. Channels. Message. Вритестарсеадерс](system.servicemodel.channels.message.writestartheaders.md)
* [Класс System. Web. Compilation. Контролбуилдеринтерцептор](controlbuilderinterceptor-class.md)
* [System. Windows. Diagnostics. Висуалдиагностикс. s \_ исдебугжерчеккдисабледфортестпурпосес, поле](s-isdebuggercheckdisabledfortestpurposes-field.md)
* [Класс System. Windows. Forms. Design. DataMemberFieldEditor](datamemberfieldeditor-class.md)
* [Класс System. Windows. Forms. Design. DataMemberListEditor](datamemberlisteditor-class.md)
* [МетодSystem.Xml.XmlReader. Креатесклреадер](system.xml.xmlreader.createsqlreader.md)
* [ADODB. Интерфейс подключения](adodb.connection.md)
* [ADODB. Перечисление Евентреасон](adodb.eventreasonenum.md)
* [ADODB. Перечисление Евентстатус](adodb.eventstatusenum.md)
* [стдоле. Структура DISPPARAMS](stdole.dispparams.md)
* [стдоле. Структура ЕКСЦЕПИНФО](stdole.excepinfo.md)
* [стдоле. IFont.Name, свойство](stdole.ifont.name.md)
* [стдоле. Интерфейс IFontDisp](stdole.ifontdisp.md)
* [стдоле. Ипиктуре. Handle, свойство](stdole.ipicture.handle.md)
* [стдоле. Ипиктуредисп. Handle, свойство](stdole.ipicturedisp.handle.md)
* [стдоле. Интерфейс Стдфонт](stdole.stdfont.md)
* [стдоле. Интерфейс Стдпиктуре](stdole.stdpicture.md)
  
## <a name="see-also"></a>Дополнительно

* [.NET Framework и внештатные выпуски](../get-started/the-net-framework-and-out-of-band-releases.md)
