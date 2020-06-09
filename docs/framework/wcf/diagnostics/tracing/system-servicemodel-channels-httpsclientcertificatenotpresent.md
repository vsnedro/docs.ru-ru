---
title: System.ServiceModel.Channels.HttpsClientCertificateNotPresent
ms.date: 03/30/2017
ms.assetid: b13ef1b6-e340-401d-93ca-2710c3842205
ms.openlocfilehash: 3e3bedca7a46f147ee3d9e143cea7e57095c99d1
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602048"
---
# <a name="systemservicemodelchannelshttpsclientcertificatenotpresent"></a><span data-ttu-id="f72e2-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span><span class="sxs-lookup"><span data-stu-id="f72e2-102">System.ServiceModel.Channels.HttpsClientCertificateNotPresent</span></span>
<span data-ttu-id="f72e2-103">Требуется сертификат клиента.</span><span class="sxs-lookup"><span data-stu-id="f72e2-103">Client certificate is required.</span></span> <span data-ttu-id="f72e2-104">В запросе не было найдено ни одного сертификата.</span><span class="sxs-lookup"><span data-stu-id="f72e2-104">No certificate was found in the request.</span></span>  
  
## <a name="description"></a><span data-ttu-id="f72e2-105">Описание</span><span class="sxs-lookup"><span data-stu-id="f72e2-105">Description</span></span>  
 <span data-ttu-id="f72e2-106">Эта трассировка показывает, что прослушиватель HTTPS получил запрос HTTPS, который не был связан с сертификатом клиента.</span><span class="sxs-lookup"><span data-stu-id="f72e2-106">This trace indicates that the HTTPS listener received an HTTPS request that was not associated with a client certificate.</span></span> <span data-ttu-id="f72e2-107">Так как прослушиватель был настроен на требование сертификатов клиента от всех запросов HTTPS, прослушивателю не удалось проверить подлинность клиента.</span><span class="sxs-lookup"><span data-stu-id="f72e2-107">Since the listener was configured to require client certificates on all HTTPS requests, the listener failed to validate the client’s authenticity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f72e2-108">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="f72e2-108">See also</span></span>

- [<span data-ttu-id="f72e2-109">Трассировка</span><span class="sxs-lookup"><span data-stu-id="f72e2-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="f72e2-110">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="f72e2-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="f72e2-111">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="f72e2-111">Administration and Diagnostics</span></span>](../index.md)
