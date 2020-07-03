---
title: FTP — .NET
description: Сведения о полной поддержке протокола FTP, которая доступна в .NET Framework посредством классов FtpWebRequest и FtpWebResponse.
ms.date: 03/30/2017
helpviewer_keywords:
- FTP
ms.assetid: 9b43f8b4-89d7-46a7-89fc-71aca916dd32
ms.openlocfilehash: d21ca43cd1041df358dc5e2add9560fb33e85d83
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502591"
---
# <a name="ftp"></a><span data-ttu-id="ade31-103">FTP</span><span class="sxs-lookup"><span data-stu-id="ade31-103">FTP</span></span>

<span data-ttu-id="ade31-104">Платформа .NET Framework обеспечивает полную поддержку протокола FTP посредством классов <xref:System.Net.FtpWebRequest> и <xref:System.Net.FtpWebResponse>.</span><span class="sxs-lookup"><span data-stu-id="ade31-104">The .NET Framework provides comprehensive support for the FTP protocol with the <xref:System.Net.FtpWebRequest> and <xref:System.Net.FtpWebResponse> classes.</span></span> <span data-ttu-id="ade31-105">Эти классы являются производными от <xref:System.Net.WebRequest> и <xref:System.Net.WebResponse>.</span><span class="sxs-lookup"><span data-stu-id="ade31-105">These classes are derived from <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse>.</span></span> <span data-ttu-id="ade31-106">В большинстве случаев классы <xref:System.Net.WebRequest> и <xref:System.Net.WebResponse> предоставляют все необходимое для выполнения запроса, но если вам требуется доступ к возможностям протокола FTP, представленным в виде свойств, можно выполнить приведение типа этих классов к <xref:System.Net.FtpWebRequest> или <xref:System.Net.FtpWebResponse>.</span><span class="sxs-lookup"><span data-stu-id="ade31-106">In most cases, the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes provide all that is necessary to make the request, but if you need access to the FTP-specific features exposed as properties, you can typecast these classes to <xref:System.Net.FtpWebRequest> or <xref:System.Net.FtpWebResponse>.</span></span>

## <a name="examples"></a><span data-ttu-id="ade31-107">Примеры</span><span class="sxs-lookup"><span data-stu-id="ade31-107">Examples</span></span>

<span data-ttu-id="ade31-108">Дополнительные сведения см. в следующих разделах: [Практическое руководство. Скачивание файлов с использованием FTP](how-to-download-files-with-ftp.md), [Практическое руководство. Отправка файлов с использованием FTP](how-to-upload-files-with-ftp.md), [Практическое руководство. Список содержимого каталога с помощью FTP](how-to-list-directory-contents-with-ftp.md).</span><span class="sxs-lookup"><span data-stu-id="ade31-108">For more information, see the following topics: [How to: Download Files with FTP](how-to-download-files-with-ftp.md), [How to: Upload Files with FTP](how-to-upload-files-with-ftp.md), and [How to: List Directory Contents with FTP](how-to-list-directory-contents-with-ftp.md).</span></span>

## <a name="ftp-and-proxies"></a><span data-ttu-id="ade31-109">FTP и прокси-серверы</span><span class="sxs-lookup"><span data-stu-id="ade31-109">FTP and proxies</span></span>

<span data-ttu-id="ade31-110">Если прокси-сервер, заданный свойством <xref:System.Net.FtpWebRequest.Proxy%2A>, является прокси-сервером HTTP, поддерживаются только команды <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory> и <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails>.</span><span class="sxs-lookup"><span data-stu-id="ade31-110">If a proxy (specified by the <xref:System.Net.FtpWebRequest.Proxy%2A> property) is an HTTP proxy, then only the <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory>, and <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails> commands are supported.</span></span>

## <a name="see-also"></a><span data-ttu-id="ade31-111">См. также</span><span class="sxs-lookup"><span data-stu-id="ade31-111">See also</span></span>

- [<span data-ttu-id="ade31-112">Доступ к Интернету через прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="ade31-112">Accessing the Internet Through a Proxy</span></span>](accessing-the-internet-through-a-proxy.md)
- [<span data-ttu-id="ade31-113">Примеры сетевого программирования</span><span class="sxs-lookup"><span data-stu-id="ade31-113">Network Programming Samples</span></span>](network-programming-samples.md)
- [<span data-ttu-id="ade31-114">Использование протоколов приложений</span><span class="sxs-lookup"><span data-stu-id="ade31-114">Using Application Protocols</span></span>](using-application-protocols.md)
