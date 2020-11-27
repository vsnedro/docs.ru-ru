---
title: System.ServiceModel.Channels.HttpsClientCertificateNotPresent
ms.date: 03/30/2017
ms.assetid: b13ef1b6-e340-401d-93ca-2710c3842205
ms.openlocfilehash: 9ec25138130311f8cdd9af8fb32a3e80fb33ed68
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96258092"
---
# <a name="systemservicemodelchannelshttpsclientcertificatenotpresent"></a><span data-ttu-id="d411f-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span><span class="sxs-lookup"><span data-stu-id="d411f-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span></span>

<span data-ttu-id="d411f-103">Требуется сертификат клиента.</span><span class="sxs-lookup"><span data-stu-id="d411f-103">Client certificate is required.</span></span> <span data-ttu-id="d411f-104">В запросе не было найдено ни одного сертификата.</span><span class="sxs-lookup"><span data-stu-id="d411f-104">No certificate was found in the request.</span></span>  
  
## <a name="description"></a><span data-ttu-id="d411f-105">Описание</span><span class="sxs-lookup"><span data-stu-id="d411f-105">Description</span></span>  

 <span data-ttu-id="d411f-106">Эта трассировка показывает, что прослушиватель HTTPS получил запрос HTTPS, который не был связан с сертификатом клиента.</span><span class="sxs-lookup"><span data-stu-id="d411f-106">This trace indicates that the HTTPS listener received an HTTPS request that was not associated with a client certificate.</span></span> <span data-ttu-id="d411f-107">Так как прослушиватель был настроен на требование сертификатов клиента от всех запросов HTTPS, прослушивателю не удалось проверить подлинность клиента.</span><span class="sxs-lookup"><span data-stu-id="d411f-107">Since the listener was configured to require client certificates on all HTTPS requests, the listener failed to validate the client’s authenticity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d411f-108">См. также</span><span class="sxs-lookup"><span data-stu-id="d411f-108">See also</span></span>

- [<span data-ttu-id="d411f-109">Трассировка</span><span class="sxs-lookup"><span data-stu-id="d411f-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="d411f-110">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="d411f-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="d411f-111">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="d411f-111">Administration and Diagnostics</span></span>](../index.md)
