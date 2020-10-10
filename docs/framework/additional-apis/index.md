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
ms.openlocfilehash: 55cb37cc2c9184eeb55ee0aab39e97f4a3f7b7d8
ms.sourcegitcommit: eb7e87496f42361b1da98562dd75b516c9d58bbc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2020
ms.locfileid: "91877643"
---
# <a name="additional-class-libraries-and-apis"></a><span data-ttu-id="5e57d-103">Дополнительные библиотеки классов и интерфейсы API</span><span class="sxs-lookup"><span data-stu-id="5e57d-103">Additional class libraries and APIs</span></span>

<span data-ttu-id="5e57d-104">В этой статье перечислены .NET Framework интерфейсы API, которые были освобождены с помощью аппаратного контроллера управления, нацелены на определенную платформу или являются частными или внутренними типами.</span><span class="sxs-lookup"><span data-stu-id="5e57d-104">This article lists .NET Framework APIs that either were released out of band, target a specific platform, or are private or internal types.</span></span>

## <a name="oob-projects"></a><span data-ttu-id="5e57d-105">Внештатные проекты</span><span class="sxs-lookup"><span data-stu-id="5e57d-105">OOB projects</span></span>

<span data-ttu-id="5e57d-106">Чтобы улучшить разработку на разных платформах и впервые добавить новые функции, некоторые .NET Framework функции были выпущены с использованием аппаратного контроллера управления (OOB).</span><span class="sxs-lookup"><span data-stu-id="5e57d-106">To improve cross-platform development and introduce new functionality early, some .NET Framework features were released out of band (OOB).</span></span>

| <span data-ttu-id="5e57d-107">Проект</span><span class="sxs-lookup"><span data-stu-id="5e57d-107">Project</span></span> | <span data-ttu-id="5e57d-108">Описание</span><span class="sxs-lookup"><span data-stu-id="5e57d-108">Description</span></span> |
| ------- | ----------- |
| <xref:System.Collections.Immutable> | <span data-ttu-id="5e57d-109">Предоставляет потокобезопасные коллекции, содержимое которых никогда не меняется.</span><span class="sxs-lookup"><span data-stu-id="5e57d-109">Provides collections that are thread safe and guaranteed to never change their contents.</span></span> |
| <xref:System.Net.Http.WinHttpHandler> | <span data-ttu-id="5e57d-110">Предоставляет обработчик сообщений для <xref:System.Net.Http.HttpClient> на основе интерфейса WinHTTP ОС Windows.</span><span class="sxs-lookup"><span data-stu-id="5e57d-110">Provides a message handler for <xref:System.Net.Http.HttpClient> based on the WinHTTP interface of Windows.</span></span> |
| <xref:System.Numerics> | <span data-ttu-id="5e57d-111">Представляет собой библиотеку векторных типов, которые могут использовать преимущества аппаратного ускорения SIMD.</span><span class="sxs-lookup"><span data-stu-id="5e57d-111">Provides a library of vector types that can take advantage of SIMD hardware-based acceleration.</span></span>|
| <xref:System.Threading.Tasks.Dataflow> | <span data-ttu-id="5e57d-112">Библиотека потоков данных TPL предоставляет компоненты потока данных, позволяющие повысить надежность приложений с поддержкой параллелизма.</span><span class="sxs-lookup"><span data-stu-id="5e57d-112">The TPL Dataflow Library provides dataflow components to help increase the robustness of concurrency-enabled applications.</span></span> |

## <a name="platform-specific-libraries"></a><span data-ttu-id="5e57d-113">Библиотеки для конкретных платформ</span><span class="sxs-lookup"><span data-stu-id="5e57d-113">Platform-specific libraries</span></span>

<span data-ttu-id="5e57d-114">Некоторые библиотеки предназначены для конкретных платформ.</span><span class="sxs-lookup"><span data-stu-id="5e57d-114">Some libraries target specific platforms.</span></span> <span data-ttu-id="5e57d-115">Например, <xref:System.Text.CodePagesEncodingProvider> класс делает кодировки кодовых страниц доступными для приложений UWP, разработанных с помощью .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5e57d-115">For example, the <xref:System.Text.CodePagesEncodingProvider> class makes code page encodings available to UWP apps developed using .NET Framework.</span></span>

| <span data-ttu-id="5e57d-116">Проект</span><span class="sxs-lookup"><span data-stu-id="5e57d-116">Project</span></span> | <span data-ttu-id="5e57d-117">Описание</span><span class="sxs-lookup"><span data-stu-id="5e57d-117">Description</span></span> |
| ------- | ----------- |
| <xref:System.Text.CodePagesEncodingProvider> | <span data-ttu-id="5e57d-118">Расширяет <xref:System.Text.EncodingProvider> класс, чтобы сделать кодировки кодовых страниц доступными для приложений, предназначенных для универсальная платформа Windows.</span><span class="sxs-lookup"><span data-stu-id="5e57d-118">Extends the <xref:System.Text.EncodingProvider> class to make code page encodings available to apps that target the Universal Windows Platform.</span></span> |

## <a name="private-apis"></a><span data-ttu-id="5e57d-119">Частные интерфейсы API</span><span class="sxs-lookup"><span data-stu-id="5e57d-119">Private APIs</span></span>

<span data-ttu-id="5e57d-120">Эти API поддерживают инфраструктуру продукта и не предназначены для использования непосредственно из кода.</span><span class="sxs-lookup"><span data-stu-id="5e57d-120">These APIs support the product infrastructure and are not intended or supported to be used directly from your code.</span></span>

* [<span data-ttu-id="5e57d-121">Свойство Microsoft. SqlServer. Server. Смиордерпроперти. Item</span><span class="sxs-lookup"><span data-stu-id="5e57d-121">Microsoft.SqlServer.Server.SmiOrderProperty.Item property</span></span>](microsoft.sqlserver.server.smiorderproperty.item.md)
* [<span data-ttu-id="5e57d-122">Метод System. Exception. Препфорремотинг</span><span class="sxs-lookup"><span data-stu-id="5e57d-122">System.Exception.PrepForRemoting method</span></span>](system.exception.prepforremoting.md)
* [<span data-ttu-id="5e57d-123">Свойство System. Data. SqlTypes. SqlChars. Stream</span><span class="sxs-lookup"><span data-stu-id="5e57d-123">System.Data.SqlTypes.SqlChars.Stream property</span></span>](system.data.sqltypes.sqlchars.stream.md)
* [<span data-ttu-id="5e57d-124">Конструктор System. Data. SqlTypes. Склстреамчарс</span><span class="sxs-lookup"><span data-stu-id="5e57d-124">System.Data.SqlTypes.SqlStreamChars Constructor</span></span>](system.data.sqltypes.sqlstreamchars.-ctor.md)
* [<span data-ttu-id="5e57d-125">Свойство System. Data. SqlTypes. Склстреамчарс. CanSeek</span><span class="sxs-lookup"><span data-stu-id="5e57d-125">System.Data.SqlTypes.SqlStreamChars.CanSeek property</span></span>](system.data.sqltypes.sqlstreamchars.canseek.md)
* [<span data-ttu-id="5e57d-126">Свойство System. Data. SqlTypes. Склстреамчарс. IsNull</span><span class="sxs-lookup"><span data-stu-id="5e57d-126">System.Data.SqlTypes.SqlStreamChars.IsNull property</span></span>](system.data.sqltypes.sqlstreamchars.isnull.md)
* [<span data-ttu-id="5e57d-127">Свойство System. Data. SqlTypes. Склстреамчарс. length</span><span class="sxs-lookup"><span data-stu-id="5e57d-127">System.Data.SqlTypes.SqlStreamChars.Length property</span></span>](system.data.sqltypes.sqlstreamchars.length.md)
* [<span data-ttu-id="5e57d-128">Метод System. Data. SqlTypes. Склстреамчарс. Close</span><span class="sxs-lookup"><span data-stu-id="5e57d-128">System.Data.SqlTypes.SqlStreamChars.Close method</span></span>](system.data.sqltypes.sqlstreamchars.close.md)
* [<span data-ttu-id="5e57d-129">Метод System. Data. SqlTypes. Склстреамчарс. Dispose</span><span class="sxs-lookup"><span data-stu-id="5e57d-129">System.Data.SqlTypes.SqlStreamChars.Dispose method</span></span>](system.data.sqltypes.sqlstreamchars.dispose.md)
* [<span data-ttu-id="5e57d-130">Метод System. Data. SqlTypes. Склстреамчарс. Flush</span><span class="sxs-lookup"><span data-stu-id="5e57d-130">System.Data.SqlTypes.SqlStreamChars.Flush method</span></span>](system.data.sqltypes.sqlstreamchars.flush.md)
* [<span data-ttu-id="5e57d-131">Метод System. Data. SqlTypes. Склстреамчарс. Read</span><span class="sxs-lookup"><span data-stu-id="5e57d-131">System.Data.SqlTypes.SqlStreamChars.Read method</span></span>](system.data.sqltypes.sqlstreamchars.read.md)
* [<span data-ttu-id="5e57d-132">Метод System. Data. SqlTypes. Склстреамчарс. Seek</span><span class="sxs-lookup"><span data-stu-id="5e57d-132">System.Data.SqlTypes.SqlStreamChars.Seek method</span></span>](system.data.sqltypes.sqlstreamchars.seek.md)
* [<span data-ttu-id="5e57d-133">Метод System. Data. SqlTypes. Склстреамчарс. SetLength</span><span class="sxs-lookup"><span data-stu-id="5e57d-133">System.Data.SqlTypes.SqlStreamChars.SetLength method</span></span>](system.data.sqltypes.sqlstreamchars.setlength.md)
* [<span data-ttu-id="5e57d-134">Метод System. Data. SqlTypes. Склстреамчарс. Write</span><span class="sxs-lookup"><span data-stu-id="5e57d-134">System.Data.SqlTypes.SqlStreamChars.Write method</span></span>](system.data.sqltypes.sqlstreamchars.write.md)
* [<span data-ttu-id="5e57d-135">Метод System. IO. MemoryStream. Интерналжеторигинандленгс</span><span class="sxs-lookup"><span data-stu-id="5e57d-135">System.IO.MemoryStream.InternalGetOriginAndLength method</span></span>](system.io.memorystream.internalgetoriginandlength.md)
* [<span data-ttu-id="5e57d-136">Класс System .NET. Комнетос</span><span class="sxs-lookup"><span data-stu-id="5e57d-136">System.Net.ComNetOS class</span></span>](system.net.comnetos.md)
* [<span data-ttu-id="5e57d-137">Класс System .NET. Connection</span><span class="sxs-lookup"><span data-stu-id="5e57d-137">System.Net.Connection class</span></span>](connection.md)
* [<span data-ttu-id="5e57d-138">Поле системы .NET. Connection. m \_ врителист</span><span class="sxs-lookup"><span data-stu-id="5e57d-138">System.Net.Connection.m\_WriteList field</span></span>](m_writelist.md)
* [<span data-ttu-id="5e57d-139">Класс System .NET. Коннектионграуп</span><span class="sxs-lookup"><span data-stu-id="5e57d-139">System.Net.ConnectionGroup class</span></span>](connectiongroup.md)
* [<span data-ttu-id="5e57d-140">System .NET. Коннектионграуп. m \_ коннектионлист, поле</span><span class="sxs-lookup"><span data-stu-id="5e57d-140">System.Net.ConnectionGroup.m\_ConnectionList field</span></span>](m_connectionlist.md)
* [<span data-ttu-id="5e57d-141">Свойство System .NET. Коннектстреам. Connection</span><span class="sxs-lookup"><span data-stu-id="5e57d-141">System.Net.ConnectStream.Connection property</span></span>](system.net.connectstream.connection.md)
* [<span data-ttu-id="5e57d-142">Класс System .NET. Коререспонседата</span><span class="sxs-lookup"><span data-stu-id="5e57d-142">System.Net.CoreResponseData class</span></span>](coreresponsedata.md)
* [<span data-ttu-id="5e57d-143">System .NET. Коререспонседата. m \_ ResponseHeaders, поле</span><span class="sxs-lookup"><span data-stu-id="5e57d-143">System.Net.CoreResponseData.m\_ResponseHeaders field</span></span>](coreresponsedata_m_responseheaders.md)
* [<span data-ttu-id="5e57d-144">Поле StatusCode System .NET. Коререспонседата. m \_</span><span class="sxs-lookup"><span data-stu-id="5e57d-144">System.Net.CoreResponseData.m\_StatusCode field</span></span>](coreresponsedata_m_statuscode.md)
* [<span data-ttu-id="5e57d-145">Класс System .NET. Ексцептионхелпер</span><span class="sxs-lookup"><span data-stu-id="5e57d-145">System.Net.ExceptionHelper class</span></span>](system.net.exceptionhelper.md)
* [<span data-ttu-id="5e57d-146">Класс System .NET. Хттпстатусдескриптион</span><span class="sxs-lookup"><span data-stu-id="5e57d-146">System.Net.HttpStatusDescription class</span></span>](system.net.httpstatusdescription.md)
* [<span data-ttu-id="5e57d-147">System .NET. HttpWebRequest. \_ Поле перенаправлений</span><span class="sxs-lookup"><span data-stu-id="5e57d-147">System.Net.HttpWebRequest.\_AutoRedirects field</span></span>](_autoredirects.md)
* [<span data-ttu-id="5e57d-148">System .NET. HttpWebRequest. \_ Поле Коререспонсе</span><span class="sxs-lookup"><span data-stu-id="5e57d-148">System.Net.HttpWebRequest.\_CoreResponse field</span></span>](httpwebrequest__coreresponse.md)
* [<span data-ttu-id="5e57d-149">System .NET. HttpWebRequest. \_ Поле HttpResponse</span><span class="sxs-lookup"><span data-stu-id="5e57d-149">System.Net.HttpWebRequest.\_HttpResponse field</span></span>](_httpresponse.md)
* [<span data-ttu-id="5e57d-150">Класс System .NET. Logging</span><span class="sxs-lookup"><span data-stu-id="5e57d-150">System.Net.Logging class</span></span>](system.net.logging.md)
* [<span data-ttu-id="5e57d-151">Класс System .NET. mail. Маиладдресспарсер</span><span class="sxs-lookup"><span data-stu-id="5e57d-151">System.Net.Mail.MailAddressParser class</span></span>](system.net.mail.mailaddressparser.md)
* [<span data-ttu-id="5e57d-152">Класс System .NET. mail. Куотедпаирреадер</span><span class="sxs-lookup"><span data-stu-id="5e57d-152">System.Net.Mail.QuotedPairReader class</span></span>](system.net.mail.quotedpairreader.md)
* [<span data-ttu-id="5e57d-153">Класс System .NET. MIME. Маилбнфхелпер</span><span class="sxs-lookup"><span data-stu-id="5e57d-153">System.Net.Mime.MailBnfHelper class</span></span>](system.net.mime.mailbnfhelper.md)
* [<span data-ttu-id="5e57d-154">Свойство System .NET. Пуледстреам. NetworkStream</span><span class="sxs-lookup"><span data-stu-id="5e57d-154">System.Net.PooledStream.NetworkStream property</span></span>](system.net.pooledstream.networkstream.md)
* [<span data-ttu-id="5e57d-155">Класс System .NET. Рткстате</span><span class="sxs-lookup"><span data-stu-id="5e57d-155">System.Net.RtcState class</span></span>](system.net.rtcstate.md)
* [<span data-ttu-id="5e57d-156">Свойство System .NET. Security. Сслстате. Сслпротокол</span><span class="sxs-lookup"><span data-stu-id="5e57d-156">System.Net.Security.SslState.SslProtocol property</span></span>](system.net.security.sslstate.sslprotocol.md)
* [<span data-ttu-id="5e57d-157">System .NET. ServicePoint. m \_ коннектионграуплист, поле</span><span class="sxs-lookup"><span data-stu-id="5e57d-157">System.Net.ServicePoint.m\_ConnectionGroupList field</span></span>](m_connectiongrouplist.md)
* [<span data-ttu-id="5e57d-158">System .NET. ServicePointManager. Клосеконнектионграупс, метод</span><span class="sxs-lookup"><span data-stu-id="5e57d-158">System.Net.ServicePointManager.CloseConnectionGroups method</span></span>](system.net.servicepointmanager.closeconnectiongroups.md)
* [<span data-ttu-id="5e57d-159">Поле System .NET. ServicePointManager. s \_ сервицепоинттабле</span><span class="sxs-lookup"><span data-stu-id="5e57d-159">System.Net.ServicePointManager.s\_ServicePointTable field</span></span>](s_servicepointtable.md)
* [<span data-ttu-id="5e57d-160">System.Net.TlsStream.m_Worker поле</span><span class="sxs-lookup"><span data-stu-id="5e57d-160">System.Net.TlsStream.m_Worker field</span></span>](system.net.tlsstream.m_worker.md)
* [<span data-ttu-id="5e57d-161">Класс System .NET. Унсафенклнативемесодс</span><span class="sxs-lookup"><span data-stu-id="5e57d-161">System.Net.UnsafeNclNativeMethods class</span></span>](system.net.unsafenclnativemethods.md)
* [<span data-ttu-id="5e57d-162">System .NET. Вебхеадерколлектион. Аддинтернал, метод</span><span class="sxs-lookup"><span data-stu-id="5e57d-162">System.Net.WebHeaderCollection.AddInternal method</span></span>](system.net.webheadercollection.addinternal.md)
* [<span data-ttu-id="5e57d-163">Метод System. ServiceModel. Channels. Message. Бодитостринг</span><span class="sxs-lookup"><span data-stu-id="5e57d-163">System.ServiceModel.Channels.Message.BodyToString method</span></span>](system.servicemodel.channels.message.bodytostring.md)
* [<span data-ttu-id="5e57d-164">Метод System. ServiceModel. Channels. Message. Вритестарсеадерс</span><span class="sxs-lookup"><span data-stu-id="5e57d-164">System.ServiceModel.Channels.Message.WriteStartHeaders method</span></span>](system.servicemodel.channels.message.writestartheaders.md)
* [<span data-ttu-id="5e57d-165">Класс System. Web. Compilation. Контролбуилдеринтерцептор</span><span class="sxs-lookup"><span data-stu-id="5e57d-165">System.Web.Compilation.ControlBuilderInterceptor class</span></span>](controlbuilderinterceptor-class.md)
* [<span data-ttu-id="5e57d-166">Метод System. Windows. Controls. Гридвиевхеадерровпресентер. Финдхеадербиколумн</span><span class="sxs-lookup"><span data-stu-id="5e57d-166">System.Windows.Controls.GridViewHeaderRowPresenter.FindHeaderByColumn method</span></span>](system.windows.controls.gridviewheaderrowpresenter.findheaderbycolumn.md)
* [<span data-ttu-id="5e57d-167">Метод System. Windows. Controls. Гридвиевхеадерровпресентер. Макепарентитемсконтролготфокус</span><span class="sxs-lookup"><span data-stu-id="5e57d-167">System.Windows.Controls.GridViewHeaderRowPresenter.MakeParentItemsControlGotFocus method</span></span>](system.windows.controls.gridviewheaderrowpresenter.makeparentitemscontrolgotfocus.md)
* [<span data-ttu-id="5e57d-168">Метод System. Windows. Controls. Гридвиевхеадерровпресентер. Препарехеадердраг</span><span class="sxs-lookup"><span data-stu-id="5e57d-168">System.Windows.Controls.GridViewHeaderRowPresenter.PrepareHeaderDrag method</span></span>](system.windows.controls.gridviewheaderrowpresenter.prepareheaderdrag.md)
* [<span data-ttu-id="5e57d-169">System. Windows. Diagnostics. Висуалдиагностикс. s \_ исдебугжерчеккдисабледфортестпурпосес, поле</span><span class="sxs-lookup"><span data-stu-id="5e57d-169">System.Windows.Diagnostics.VisualDiagnostics.s\_isDebuggerCheckDisabledForTestPurposes field</span></span>](s-isdebuggercheckdisabledfortestpurposes-field.md)
* [<span data-ttu-id="5e57d-170">Класс System. Windows. Forms. Design. DataMemberFieldEditor</span><span class="sxs-lookup"><span data-stu-id="5e57d-170">System.Windows.Forms.Design.DataMemberFieldEditor class</span></span>](datamemberfieldeditor-class.md)
* [<span data-ttu-id="5e57d-171">Класс System. Windows. Forms. Design. DataMemberListEditor</span><span class="sxs-lookup"><span data-stu-id="5e57d-171">System.Windows.Forms.Design.DataMemberListEditor class</span></span>](datamemberlisteditor-class.md)
* [<span data-ttu-id="5e57d-172"> МетодSystem.Xml.XmlReader. Креатесклреадер</span><span class="sxs-lookup"><span data-stu-id="5e57d-172">System.Xml.XmlReader.CreateSqlReader method</span></span>](system.xml.xmlreader.createsqlreader.md)
* [<span data-ttu-id="5e57d-173">ADODB. Интерфейс подключения</span><span class="sxs-lookup"><span data-stu-id="5e57d-173">adodb.Connection interface</span></span>](adodb.connection.md)
* [<span data-ttu-id="5e57d-174">ADODB. Перечисление Евентреасон</span><span class="sxs-lookup"><span data-stu-id="5e57d-174">adodb.EventReason enum</span></span>](adodb.eventreasonenum.md)
* [<span data-ttu-id="5e57d-175">ADODB. Перечисление Евентстатус</span><span class="sxs-lookup"><span data-stu-id="5e57d-175">adodb.EventStatus enum</span></span>](adodb.eventstatusenum.md)
* [<span data-ttu-id="5e57d-176">стдоле. Структура DISPPARAMS</span><span class="sxs-lookup"><span data-stu-id="5e57d-176">stdole.DISPPARAMS Structure</span></span>](stdole.dispparams.md)
* [<span data-ttu-id="5e57d-177">стдоле. Структура ЕКСЦЕПИНФО</span><span class="sxs-lookup"><span data-stu-id="5e57d-177">stdole.EXCEPINFO Structure</span></span>](stdole.excepinfo.md)
* [<span data-ttu-id="5e57d-178">стдоле. IFont.Name, свойство</span><span class="sxs-lookup"><span data-stu-id="5e57d-178">stdole.IFont.Name property</span></span>](stdole.ifont.name.md)
* [<span data-ttu-id="5e57d-179">стдоле. Интерфейс IFontDisp</span><span class="sxs-lookup"><span data-stu-id="5e57d-179">stdole.IFontDisp interface</span></span>](stdole.ifontdisp.md)
* [<span data-ttu-id="5e57d-180">стдоле. Ипиктуре. Handle, свойство</span><span class="sxs-lookup"><span data-stu-id="5e57d-180">stdole.IPicture.Handle property</span></span>](stdole.ipicture.handle.md)
* [<span data-ttu-id="5e57d-181">стдоле. Ипиктуредисп. Handle, свойство</span><span class="sxs-lookup"><span data-stu-id="5e57d-181">stdole.IPictureDisp.Handle property</span></span>](stdole.ipicturedisp.handle.md)
* [<span data-ttu-id="5e57d-182">стдоле. Интерфейс Стдфонт</span><span class="sxs-lookup"><span data-stu-id="5e57d-182">stdole.StdFont interface</span></span>](stdole.stdfont.md)
* [<span data-ttu-id="5e57d-183">стдоле. Интерфейс Стдпиктуре</span><span class="sxs-lookup"><span data-stu-id="5e57d-183">stdole.StdPicture interface</span></span>](stdole.stdpicture.md)

## <a name="see-also"></a><span data-ttu-id="5e57d-184">См. также</span><span class="sxs-lookup"><span data-stu-id="5e57d-184">See also</span></span>

* [<span data-ttu-id="5e57d-185">.NET Framework и внештатные выпуски</span><span class="sxs-lookup"><span data-stu-id="5e57d-185">.NET Framework and Out-of-Band Releases</span></span>](../get-started/the-net-framework-and-out-of-band-releases.md)
