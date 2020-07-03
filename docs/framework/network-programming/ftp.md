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
# <a name="ftp"></a>FTP

Платформа .NET Framework обеспечивает полную поддержку протокола FTP посредством классов <xref:System.Net.FtpWebRequest> и <xref:System.Net.FtpWebResponse>. Эти классы являются производными от <xref:System.Net.WebRequest> и <xref:System.Net.WebResponse>. В большинстве случаев классы <xref:System.Net.WebRequest> и <xref:System.Net.WebResponse> предоставляют все необходимое для выполнения запроса, но если вам требуется доступ к возможностям протокола FTP, представленным в виде свойств, можно выполнить приведение типа этих классов к <xref:System.Net.FtpWebRequest> или <xref:System.Net.FtpWebResponse>.

## <a name="examples"></a>Примеры

Дополнительные сведения см. в следующих разделах: [Практическое руководство. Скачивание файлов с использованием FTP](how-to-download-files-with-ftp.md), [Практическое руководство. Отправка файлов с использованием FTP](how-to-upload-files-with-ftp.md), [Практическое руководство. Список содержимого каталога с помощью FTP](how-to-list-directory-contents-with-ftp.md).

## <a name="ftp-and-proxies"></a>FTP и прокси-серверы

Если прокси-сервер, заданный свойством <xref:System.Net.FtpWebRequest.Proxy%2A>, является прокси-сервером HTTP, поддерживаются только команды <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory> и <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails>.

## <a name="see-also"></a>См. также

- [Доступ к Интернету через прокси-сервер](accessing-the-internet-through-a-proxy.md)
- [Примеры сетевого программирования](network-programming-samples.md)
- [Использование протоколов приложений](using-application-protocols.md)
