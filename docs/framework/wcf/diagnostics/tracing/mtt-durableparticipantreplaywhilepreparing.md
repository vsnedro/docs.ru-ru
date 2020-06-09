---
title: Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
ms.date: 03/30/2017
ms.assetid: 10ef3876-6f8e-4d4e-8444-f47847b64795
ms.openlocfilehash: 31fb8d466c76c7490aa80dfcab089332af4036a2
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84589136"
---
# <a name="microsofttransactionstransactionbridgedurableparticipantreplaywhilepreparing"></a><span data-ttu-id="2017e-102">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span><span class="sxs-lookup"><span data-stu-id="2017e-102">Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing</span></span>
<span data-ttu-id="2017e-103">Служба протокола WS-AT получила ответное сообщение от постоянного участника, который не ответил на подготовительное сообщение.</span><span class="sxs-lookup"><span data-stu-id="2017e-103">The WS-AT protocol service received a Replay message from a durable participant, which did not respond to Prepare.</span></span> <span data-ttu-id="2017e-104">Поэтому транзакция была прервана.</span><span class="sxs-lookup"><span data-stu-id="2017e-104">Consequently, the transaction was aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="2017e-105">Описание</span><span class="sxs-lookup"><span data-stu-id="2017e-105">Description</span></span>  
 <span data-ttu-id="2017e-106">Трассируется, если ответное сообщение получается, пока постоянный участник находится в состоянии подготовки.</span><span class="sxs-lookup"><span data-stu-id="2017e-106">Traced if a Replay message is received while a Durable participant is still Preparing.</span></span> <span data-ttu-id="2017e-107">Это недопустимое сообщение для данного состояния, поэтому транзакция прерывается.</span><span class="sxs-lookup"><span data-stu-id="2017e-107">This is an illegal message for this state and the transaction is going to be aborted.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="2017e-108">Диагностика</span><span class="sxs-lookup"><span data-stu-id="2017e-108">Troubleshooting</span></span>

<span data-ttu-id="2017e-109">Получение этой ошибки может означать, что устойчивый участник (включая подчиненный Трансактионманажерс) был восстановлен после сбоя; Тем не менее, результат транзакции не известен и запрашивает свое состояние.</span><span class="sxs-lookup"><span data-stu-id="2017e-109">Receiving this error can indicate that a Durable participant (including Subordinate TransactionManagers) has recovered from failure; however, it is unsure of the transaction outcome and requests its status.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2017e-110">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="2017e-110">See also</span></span>

- [<span data-ttu-id="2017e-111">Трассировка</span><span class="sxs-lookup"><span data-stu-id="2017e-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="2017e-112">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="2017e-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="2017e-113">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="2017e-113">Administration and Diagnostics</span></span>](../index.md)
