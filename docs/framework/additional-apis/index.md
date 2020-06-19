---
title: Дополнительные библиотеки классов и интерфейсы API
description: Изучите дополнительные библиотеки классов и API-интерфейсы в .NET, включая проекты с внешними интерфейсами (OOB), библиотеки для конкретных платформ и частные интерфейсы API.
ms.date: 06/12/2020
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
ms.topic: conceptual
ms.openlocfilehash: 0b888d2f0e80685ba993682b2f3067cf8aee15bc
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989735"
---
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="5046a-103">Дополнительные библиотеки классов и интерфейсы API</span><span class="sxs-lookup"><span data-stu-id="5046a-103">Additional class libraries and APIs</span></span>

<span data-ttu-id="5046a-104">В этой статье перечислены .NET Framework интерфейсы API, которые были освобождены с помощью аппаратного контроллера управления, нацелены на определенную платформу или являются частными или внутренними типами.</span><span class="sxs-lookup"><span data-stu-id="5046a-104">This article lists .NET Framework APIs that either were released out of band, target a specific platform, or are private or internal types.</span></span>

## <a name="oob-projects"></a><span data-ttu-id="5046a-105">Внештатные проекты</span><span class="sxs-lookup"><span data-stu-id="5046a-105">OOB projects</span></span>

<span data-ttu-id="5046a-106">Чтобы улучшить разработку на разных платформах и впервые добавить новые функции, некоторые .NET Framework функции были выпущены с использованием аппаратного контроллера управления (OOB).</span><span class="sxs-lookup"><span data-stu-id="5046a-106">To improve cross-platform development and introduce new functionality early, some .NET Framework features were released out of band (OOB).</span></span>

| <span data-ttu-id="5046a-107">Project</span><span class="sxs-lookup"><span data-stu-id="5046a-107">Project</span></span> | <span data-ttu-id="5046a-108">Описание</span><span class="sxs-lookup"><span data-stu-id="5046a-108">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | <span data-ttu-id="5046a-109">Предоставляет потокобезопасные коллекции, содержимое которых никогда не меняется.</span><span class="sxs-lookup"><span data-stu-id="5046a-109">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="5046a-110">Предоставляет обработчик сообщений для <xref:System.Net.Http.HttpClient> на основе интерфейса WinHTTP ОС Windows.</span><span class="sxs-lookup"><span data-stu-id="5046a-110">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| <xref:System.Numerics> | <span data-ttu-id="5046a-111">Представляет собой библиотеку векторных типов, которые могут использовать преимущества аппаратного ускорения SIMD.</span><span class="sxs-lookup"><span data-stu-id="5046a-111">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>|
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="5046a-112">Библиотека потоков данных TPL предоставляет компоненты потока данных, позволяющие повысить надежность приложений с поддержкой параллелизма.</span><span class="sxs-lookup"><span data-stu-id="5046a-112">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |  

## <a name="platform-specific-libraries"></a><span data-ttu-id="5046a-113">Библиотеки для конкретных платформ</span><span class="sxs-lookup"><span data-stu-id="5046a-113">Platform-specific libraries</span></span>

<span data-ttu-id="5046a-114">Некоторые библиотеки предназначены для конкретных платформ.</span><span class="sxs-lookup"><span data-stu-id="5046a-114">Some libraries target specific platforms.</span></span> <span data-ttu-id="5046a-115">Например, <xref:System.Text.CodePagesEncodingProvider> класс делает кодировки кодовых страниц доступными для приложений UWP, разработанных с помощью .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5046a-115">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using .NET Framework.</span></span>
  
| <span data-ttu-id="5046a-116">Project</span><span class="sxs-lookup"><span data-stu-id="5046a-116">Project</span></span> | <span data-ttu-id="5046a-117">Описание</span><span class="sxs-lookup"><span data-stu-id="5046a-117">Description</span></span> |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="5046a-118">Расширяет <xref:System.Text.EncodingProvider> класс, чтобы сделать кодировки кодовых страниц доступными для приложений, предназначенных для универсальная платформа Windows.</span><span class="sxs-lookup"><span data-stu-id="5046a-118">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |  
  
## <a name="private-apis"></a><span data-ttu-id="5046a-119">Частные интерфейсы API</span><span class="sxs-lookup"><span data-stu-id="5046a-119">Private APIs</span></span>  

<span data-ttu-id="5046a-120">Эти API поддерживают инфраструктуру продукта и не предназначены для использования непосредственно из кода.</span><span class="sxs-lookup"><span data-stu-id="5046a-120">These APIs support the product infrastructure and are not intended or supported to be used directly from your code.</span></span>  
  
* [<span data-ttu-id="5046a-121">Свойство Microsoft. SqlServer. Server. Смиордерпроперти. Item</span><span class="sxs-lookup"><span data-stu-id="5046a-121">Microsoft.SqlServer.Server.SmiOrderProperty.Item property</span></span>](microsoft.sqlserver.server.smiorderproperty.item.md)
* [<span data-ttu-id="5046a-122">Метод System. Exception. Препфорремотинг</span><span class="sxs-lookup"><span data-stu-id="5046a-122">System.Exception.PrepForRemoting method</span></span>](system.exception.prepforremoting.md)
* [<span data-ttu-id="5046a-123">Свойство System. Data. SqlTypes. SqlChars. Stream</span><span class="sxs-lookup"><span data-stu-id="5046a-123">System.Data.SqlTypes.SqlChars.Stream property</span></span>](system.data.sqltypes.sqlchars.stream.md)
* [<span data-ttu-id="5046a-124">Конструктор System. Data. SqlTypes. Склстреамчарс</span><span class="sxs-lookup"><span data-stu-id="5046a-124">System.Data.SqlTypes.SqlStreamChars Constructor</span></span>](system.data.sqltypes.sqlstreamchars.-ctor.md)
* [<span data-ttu-id="5046a-125">Свойство System. Data. SqlTypes. Склстреамчарс. CanSeek</span><span class="sxs-lookup"><span data-stu-id="5046a-125">System.Data.SqlTypes.SqlStreamChars.CanSeek property</span></span>](system.data.sqltypes.sqlstreamchars.canseek.md)
* [<span data-ttu-id="5046a-126">Свойство System. Data. SqlTypes. Склстреамчарс. IsNull</span><span class="sxs-lookup"><span data-stu-id="5046a-126">System.Data.SqlTypes.SqlStreamChars.IsNull property</span></span>](system.data.sqltypes.sqlstreamchars.isnull.md)
* [<span data-ttu-id="5046a-127">Свойство System. Data. SqlTypes. Склстреамчарс. length</span><span class="sxs-lookup"><span data-stu-id="5046a-127">System.Data.SqlTypes.SqlStreamChars.Length property</span></span>](system.data.sqltypes.sqlstreamchars.length.md)
* [<span data-ttu-id="5046a-128">Метод System. Data. SqlTypes. Склстреамчарс. Close</span><span class="sxs-lookup"><span data-stu-id="5046a-128">System.Data.SqlTypes.SqlStreamChars.Close method</span></span>](system.data.sqltypes.sqlstreamchars.close.md)
* [<span data-ttu-id="5046a-129">Метод System. Data. SqlTypes. Склстреамчарс. Dispose</span><span class="sxs-lookup"><span data-stu-id="5046a-129">System.Data.SqlTypes.SqlStreamChars.Dispose method</span></span>](system.data.sqltypes.sqlstreamchars.dispose.md)
* [<span data-ttu-id="5046a-130">Метод System. Data. SqlTypes. Склстреамчарс. Flush</span><span class="sxs-lookup"><span data-stu-id="5046a-130">System.Data.SqlTypes.SqlStreamChars.Flush method</span></span>](system.data.sqltypes.sqlstreamchars.flush.md)
* [<span data-ttu-id="5046a-131">Метод System. Data. SqlTypes. Склстреамчарс. Read</span><span class="sxs-lookup"><span data-stu-id="5046a-131">System.Data.SqlTypes.SqlStreamChars.Read method</span></span>](system.data.sqltypes.sqlstreamchars.read.md)
* [<span data-ttu-id="5046a-132">Метод System. Data. SqlTypes. Склстреамчарс. Seek</span><span class="sxs-lookup"><span data-stu-id="5046a-132">System.Data.SqlTypes.SqlStreamChars.Seek method</span></span>](system.data.sqltypes.sqlstreamchars.seek.md)
* [<span data-ttu-id="5046a-133">Метод System. Data. SqlTypes. Склстреамчарс. SetLength</span><span class="sxs-lookup"><span data-stu-id="5046a-133">System.Data.SqlTypes.SqlStreamChars.SetLength method</span></span>](system.data.sqltypes.sqlstreamchars.setlength.md)
* [<span data-ttu-id="5046a-134">Метод System. Data. SqlTypes. Склстреамчарс. Write</span><span class="sxs-lookup"><span data-stu-id="5046a-134">System.Data.SqlTypes.SqlStreamChars.Write method</span></span>](system.data.sqltypes.sqlstreamchars.write.md)
* [<span data-ttu-id="5046a-135">Метод System. IO. MemoryStream. Интерналжеторигинандленгс</span><span class="sxs-lookup"><span data-stu-id="5046a-135">System.IO.MemoryStream.InternalGetOriginAndLength method</span></span>](system.io.memorystream.internalgetoriginandlength.md)
* [<span data-ttu-id="5046a-136">Класс System .NET. Комнетос</span><span class="sxs-lookup"><span data-stu-id="5046a-136">System.Net.ComNetOS class</span></span>](system.net.comnetos.md)
* [<span data-ttu-id="5046a-137">Класс System .NET. Connection</span><span class="sxs-lookup"><span data-stu-id="5046a-137">System.Net.Connection class</span></span>](connection.md)
* [<span data-ttu-id="5046a-138">Поле системы .NET. Connection. m \_ врителист</span><span class="sxs-lookup"><span data-stu-id="5046a-138">System.Net.Connection.m\_WriteList field</span></span>](m_writelist.md)
* [<span data-ttu-id="5046a-139">Класс System .NET. Коннектионграуп</span><span class="sxs-lookup"><span data-stu-id="5046a-139">System.Net.ConnectionGroup class</span></span>](connectiongroup.md)
* [<span data-ttu-id="5046a-140">System .NET. Коннектионграуп. m \_ коннектионлист, поле</span><span class="sxs-lookup"><span data-stu-id="5046a-140">System.Net.ConnectionGroup.m\_ConnectionList field</span></span>](m_connectionlist.md)
* [<span data-ttu-id="5046a-141">Свойство System .NET. Коннектстреам. Connection</span><span class="sxs-lookup"><span data-stu-id="5046a-141">System.Net.ConnectStream.Connection property</span></span>](system.net.connectstream.connection.md)
* [<span data-ttu-id="5046a-142">Класс System .NET. Коререспонседата</span><span class="sxs-lookup"><span data-stu-id="5046a-142">System.Net.CoreResponseData class</span></span>](coreresponsedata.md)
* [<span data-ttu-id="5046a-143">System .NET. Коререспонседата. m \_ ResponseHeaders, поле</span><span class="sxs-lookup"><span data-stu-id="5046a-143">System.Net.CoreResponseData.m\_ResponseHeaders field</span></span>](coreresponsedata_m_responseheaders.md)
* [<span data-ttu-id="5046a-144">Поле StatusCode System .NET. Коререспонседата. m \_</span><span class="sxs-lookup"><span data-stu-id="5046a-144">System.Net.CoreResponseData.m\_StatusCode field</span></span>](coreresponsedata_m_statuscode.md)
* [<span data-ttu-id="5046a-145">Класс System .NET. Ексцептионхелпер</span><span class="sxs-lookup"><span data-stu-id="5046a-145">System.Net.ExceptionHelper class</span></span>](system.net.exceptionhelper.md)
* [<span data-ttu-id="5046a-146">Класс System .NET. Хттпстатусдескриптион</span><span class="sxs-lookup"><span data-stu-id="5046a-146">System.Net.HttpStatusDescription class</span></span>](system.net.httpstatusdescription.md)
* [<span data-ttu-id="5046a-147">System .NET. HttpWebRequest. \_ Поле перенаправлений</span><span class="sxs-lookup"><span data-stu-id="5046a-147">System.Net.HttpWebRequest.\_AutoRedirects field</span></span>](_autoredirects.md)
* [<span data-ttu-id="5046a-148">System .NET. HttpWebRequest. \_ Поле Коререспонсе</span><span class="sxs-lookup"><span data-stu-id="5046a-148">System.Net.HttpWebRequest.\_CoreResponse field</span></span>](httpwebrequest__coreresponse.md)
* [<span data-ttu-id="5046a-149">System .NET. HttpWebRequest. \_ Поле HttpResponse</span><span class="sxs-lookup"><span data-stu-id="5046a-149">System.Net.HttpWebRequest.\_HttpResponse field</span></span>](_httpresponse.md)
* [<span data-ttu-id="5046a-150">Класс System .NET. Logging</span><span class="sxs-lookup"><span data-stu-id="5046a-150">System.Net.Logging class</span></span>](system.net.logging.md)
* [<span data-ttu-id="5046a-151">Класс System .NET. mail. Маиладдресспарсер</span><span class="sxs-lookup"><span data-stu-id="5046a-151">System.Net.Mail.MailAddressParser class</span></span>](system.net.mail.mailaddressparser.md)
* [<span data-ttu-id="5046a-152">Класс System .NET. mail. Куотедпаирреадер</span><span class="sxs-lookup"><span data-stu-id="5046a-152">System.Net.Mail.QuotedPairReader class</span></span>](system.net.mail.quotedpairreader.md)
* [<span data-ttu-id="5046a-153">Класс System .NET. MIME. Маилбнфхелпер</span><span class="sxs-lookup"><span data-stu-id="5046a-153">System.Net.Mime.MailBnfHelper class</span></span>](system.net.mime.mailbnfhelper.md)
* [<span data-ttu-id="5046a-154">Свойство System .NET. Пуледстреам. NetworkStream</span><span class="sxs-lookup"><span data-stu-id="5046a-154">System.Net.PooledStream.NetworkStream property</span></span>](system.net.pooledstream.networkstream.md)
* [<span data-ttu-id="5046a-155">Класс System .NET. Рткстате</span><span class="sxs-lookup"><span data-stu-id="5046a-155">System.Net.RtcState class</span></span>](system.net.rtcstate.md)
* [<span data-ttu-id="5046a-156">Свойство System .NET. Security. Сслстате. Сслпротокол</span><span class="sxs-lookup"><span data-stu-id="5046a-156">System.Net.Security.SslState.SslProtocol property</span></span>](system.net.security.sslstate.sslprotocol.md)
* [<span data-ttu-id="5046a-157">System .NET. ServicePoint. m \_ коннектионграуплист, поле</span><span class="sxs-lookup"><span data-stu-id="5046a-157">System.Net.ServicePoint.m\_ConnectionGroupList field</span></span>](m_connectiongrouplist.md)
* [<span data-ttu-id="5046a-158">System .NET. ServicePointManager. Клосеконнектионграупс, метод</span><span class="sxs-lookup"><span data-stu-id="5046a-158">System.Net.ServicePointManager.CloseConnectionGroups method</span></span>](system.net.servicepointmanager.closeconnectiongroups.md)
* [<span data-ttu-id="5046a-159">Поле System .NET. ServicePointManager. s \_ сервицепоинттабле</span><span class="sxs-lookup"><span data-stu-id="5046a-159">System.Net.ServicePointManager.s\_ServicePointTable field</span></span>](s_servicepointtable.md)
* [<span data-ttu-id="5046a-160">Поле System .NET. Тлсстреам. m_Worker</span><span class="sxs-lookup"><span data-stu-id="5046a-160">System.Net.TlsStream.m_Worker field</span></span>](system.net.tlsstream.m_worker.md)
* [<span data-ttu-id="5046a-161">Класс System .NET. Унсафенклнативемесодс</span><span class="sxs-lookup"><span data-stu-id="5046a-161">System.Net.UnsafeNclNativeMethods class</span></span>](system.net.unsafenclnativemethods.md)
* [<span data-ttu-id="5046a-162">System .NET. Вебхеадерколлектион. Аддинтернал, метод</span><span class="sxs-lookup"><span data-stu-id="5046a-162">System.Net.WebHeaderCollection.AddInternal method</span></span>](system.net.webheadercollection.addinternal.md)
* [<span data-ttu-id="5046a-163">Метод System. ServiceModel. Channels. Message. Бодитостринг</span><span class="sxs-lookup"><span data-stu-id="5046a-163">System.ServiceModel.Channels.Message.BodyToString method</span></span>](system.servicemodel.channels.message.bodytostring.md)
* [<span data-ttu-id="5046a-164">Метод System. ServiceModel. Channels. Message. Вритестарсеадерс</span><span class="sxs-lookup"><span data-stu-id="5046a-164">System.ServiceModel.Channels.Message.WriteStartHeaders method</span></span>](system.servicemodel.channels.message.writestartheaders.md)
* [<span data-ttu-id="5046a-165">System. Windows. Diagnostics. Висуалдиагностикс. s \_ исдебугжерчеккдисабледфортестпурпосес, поле</span><span class="sxs-lookup"><span data-stu-id="5046a-165">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes field</span></span>](s-isdebuggercheckdisabledfortestpurposes-field.md)
* [<span data-ttu-id="5046a-166">Класс System. Windows. Forms. Design. DataMemberFieldEditor</span><span class="sxs-lookup"><span data-stu-id="5046a-166">System.Windows.Forms.Design.DataMemberFieldEditor class</span></span>](datamemberfieldeditor-class.md)
* [<span data-ttu-id="5046a-167">Класс System. Windows. Forms. Design. DataMemberListEditor</span><span class="sxs-lookup"><span data-stu-id="5046a-167">System.Windows.Forms.Design.DataMemberListEditor class</span></span>](datamemberlisteditor-class.md)
* [<span data-ttu-id="5046a-168">МетодSystem.Xml.XmlReader. Креатесклреадер</span><span class="sxs-lookup"><span data-stu-id="5046a-168">System.Xml.XmlReader.CreateSqlReader method</span></span>](system.xml.xmlreader.createsqlreader.md)
* [<span data-ttu-id="5046a-169">ADODB. Интерфейс подключения</span><span class="sxs-lookup"><span data-stu-id="5046a-169">adodb.Connection interface</span></span>](adodb.connection.md)
* [<span data-ttu-id="5046a-170">ADODB. Перечисление Евентреасон</span><span class="sxs-lookup"><span data-stu-id="5046a-170">adodb.EventReason enum</span></span>](adodb.eventreasonenum.md)
* [<span data-ttu-id="5046a-171">ADODB. Перечисление Евентстатус</span><span class="sxs-lookup"><span data-stu-id="5046a-171">adodb.EventStatus enum</span></span>](adodb.eventstatusenum.md)
* [<span data-ttu-id="5046a-172">стдоле. Структура DISPPARAMS</span><span class="sxs-lookup"><span data-stu-id="5046a-172">stdole.DISPPARAMS Structure</span></span>](stdole.dispparams.md)
* [<span data-ttu-id="5046a-173">стдоле. Структура ЕКСЦЕПИНФО</span><span class="sxs-lookup"><span data-stu-id="5046a-173">stdole.EXCEPINFO Structure</span></span>](stdole.excepinfo.md)
* [<span data-ttu-id="5046a-174">стдоле. IFont.Name, свойство</span><span class="sxs-lookup"><span data-stu-id="5046a-174">stdole.IFont.Name property</span></span>](stdole.ifont.name.md)
* [<span data-ttu-id="5046a-175">стдоле. Интерфейс IFontDisp</span><span class="sxs-lookup"><span data-stu-id="5046a-175">stdole.IFontDisp interface</span></span>](stdole.ifontdisp.md)
* [<span data-ttu-id="5046a-176">стдоле. Ипиктуре. Handle, свойство</span><span class="sxs-lookup"><span data-stu-id="5046a-176">stdole.IPicture.Handle property</span></span>](stdole.ipicture.handle.md)
* [<span data-ttu-id="5046a-177">стдоле. Ипиктуредисп. Handle, свойство</span><span class="sxs-lookup"><span data-stu-id="5046a-177">stdole.IPictureDisp.Handle property</span></span>](stdole.ipicturedisp.handle.md)
* [<span data-ttu-id="5046a-178">стдоле. Интерфейс Стдфонт</span><span class="sxs-lookup"><span data-stu-id="5046a-178">stdole.StdFont interface</span></span>](stdole.stdfont.md)
* [<span data-ttu-id="5046a-179">стдоле. Интерфейс Стдпиктуре</span><span class="sxs-lookup"><span data-stu-id="5046a-179">stdole.StdPicture interface</span></span>](stdole.stdpicture.md)
  
## <a name="see-also"></a><span data-ttu-id="5046a-180">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="5046a-180">See also</span></span>

* [<span data-ttu-id="5046a-181">.NET Framework и внештатные выпуски</span><span class="sxs-lookup"><span data-stu-id="5046a-181">.NET Framework and Out-of-Band Releases</span></span>](../get-started/the-net-framework-and-out-of-band-releases.md)
