---
title: System.ServiceModel.TxCompletionStatusCompletedForError
ms.date: 03/30/2017
ms.assetid: 8ade4722-a6d5-471c-b960-1cfea4ea2aa9
ms.openlocfilehash: 2bc71d18480fa19be66cbfa1687a7b63eb548309
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601456"
---
# <a name="systemservicemodeltxcompletionstatuscompletedforerror"></a><span data-ttu-id="ec853-102">System.ServiceModel.TxCompletionStatusCompletedForError</span><span class="sxs-lookup"><span data-stu-id="ec853-102">System.ServiceModel.TxCompletionStatusCompletedForError</span></span>
<span data-ttu-id="ec853-103">Заданная транзакция для заданной операции завершена в результате необработанного исключения при выполнении.</span><span class="sxs-lookup"><span data-stu-id="ec853-103">The specified transaction for the specified operation was completed due to an unhandled execution exception.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ec853-104">Описание</span><span class="sxs-lookup"><span data-stu-id="ec853-104">Description</span></span>  
 <span data-ttu-id="ec853-105">Трассируется, если при попытке завершить текущую транзакцию возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="ec853-105">Traced when an error occurs during an attempt to complete the current transaction.</span></span> <span data-ttu-id="ec853-106">Это происходит до того, как вызвавшему объекту отправляется ответ или ошибка.</span><span class="sxs-lookup"><span data-stu-id="ec853-106">This happens before a reply or fault is sent to the caller.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="ec853-107">Диагностика</span><span class="sxs-lookup"><span data-stu-id="ec853-107">Troubleshooting</span></span>  
 <span data-ttu-id="ec853-108">Проверьте трассируемое сообщение на предмет наличия сообщения об исключении и других элементов, с которыми можно произвести какие-либо действия.</span><span class="sxs-lookup"><span data-stu-id="ec853-108">Inspect the traced message for the exception message and any actionable items.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec853-109">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="ec853-109">See also</span></span>

- [<span data-ttu-id="ec853-110">Трассировка</span><span class="sxs-lookup"><span data-stu-id="ec853-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="ec853-111">Использование трассировки для устранения неполадок приложения</span><span class="sxs-lookup"><span data-stu-id="ec853-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="ec853-112">Администрирование и диагностика</span><span class="sxs-lookup"><span data-stu-id="ec853-112">Administration and Diagnostics</span></span>](../index.md)
