---
title: System.ServiceModel.Channels.HttpChannelMessageReceiveFailed
ms.date: 03/30/2017
ms.assetid: 9eb311da-fdcc-4dd3-9d85-05b3280dfdda
ms.openlocfilehash: e11b376924ee74e5d0d67da0cac59af41655dc44
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594079"
---
# <a name="systemservicemodelchannelshttpchannelmessagereceivefailed"></a><span data-ttu-id="9f6da-102">System.ServiceModel.Channels.HttpChannelMessageReceiveFailed</span><span class="sxs-lookup"><span data-stu-id="9f6da-102">System.ServiceModel.Channels.HttpChannelMessageReceiveFailed</span></span>
<span data-ttu-id="9f6da-103">Сбой получения сообщения по каналу HTTP.</span><span class="sxs-lookup"><span data-stu-id="9f6da-103">Failed to receive a message over an HTTP channel.</span></span>  
  
## <a name="description"></a><span data-ttu-id="9f6da-104">Описание</span><span class="sxs-lookup"><span data-stu-id="9f6da-104">Description</span></span>  
 <span data-ttu-id="9f6da-105">Данная трассировка может выдаваться в качестве предупреждения или ошибки.</span><span class="sxs-lookup"><span data-stu-id="9f6da-105">This trace can be emitted as a warning or an error.</span></span> <span data-ttu-id="9f6da-106">В обоих случаях трассировка выдается, если при входящем HTTP-запросе не найден совместимый прослушиватель и HTTP-запрос получил отказ.</span><span class="sxs-lookup"><span data-stu-id="9f6da-106">In both cases, the trace is emitted when a compatible listener is not found for an incoming HTTP request and the HTTP request is discarded.</span></span> <span data-ttu-id="9f6da-107">Это может произойти по той причине, что HTTP-команда запроса не была распознана прослушивателем HTTP, либо потому что прослушиватель ожидал передачи данных по адресу, на который был направлен запрос.</span><span class="sxs-lookup"><span data-stu-id="9f6da-107">This could happen because the request’s HTTP verb was not recognized by any HTTP listener, or because no listener was listening on the address the request was targeted for.</span></span> <span data-ttu-id="9f6da-108">Данная трассировка выдается как предупреждение при независимом размещении и как ошибка при размещении службы в IIS.</span><span class="sxs-lookup"><span data-stu-id="9f6da-108">The trace is emitted as a warning in the self-hosted case, and as an error when the service is hosted in IIS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f6da-109">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="9f6da-109">See also</span></span>

- [<span data-ttu-id="9f6da-110">Трассировка</span><span class="sxs-lookup"><span data-stu-id="9f6da-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="9f6da-111">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="9f6da-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="9f6da-112">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="9f6da-112">Administration and Diagnostics</span></span>](../index.md)
