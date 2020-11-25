---
title: Структура USER_THREAD
ms.date: 03/30/2017
api_name:
- USER_THREAD
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- USER_THREAD
helpviewer_keywords:
- USER_THREAD structure [.NET Framework debugging]
ms.assetid: a57c7d71-c4b0-41f9-a964-0c5ee84a3124
topic_type:
- apiref
ms.openlocfilehash: 409651aa69e957418ad46f61e1bd57add0eb10a6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722899"
---
# <a name="user_thread-structure"></a><span data-ttu-id="afbca-102">Структура USER_THREAD</span><span class="sxs-lookup"><span data-stu-id="afbca-102">USER_THREAD Structure</span></span>

<span data-ttu-id="afbca-103">Предоставляет сведения отладчику о потоке.</span><span class="sxs-lookup"><span data-stu-id="afbca-103">Provides information to a debugger about a thread.</span></span> <span data-ttu-id="afbca-104">Дополнительные сведения см. в описании метода [INotifySource2:: сетнотифифилтер](inotifysource2-setnotifyfilter-method.md) .</span><span class="sxs-lookup"><span data-stu-id="afbca-104">For more information, see the [INotifySource2::SetNotifyFilter](inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afbca-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="afbca-105">Syntax</span></span>  
  
```cpp  
typedef struct tagUSER_THREAD  
{  
    BYTE    *pSidBuffer;  
    DWORD   dwSidLen;  
    DWORD   dwTid;  
} USER_THREAD;  
```  
  
## <a name="members"></a><span data-ttu-id="afbca-106">Члены</span><span class="sxs-lookup"><span data-stu-id="afbca-106">Members</span></span>  
  
|<span data-ttu-id="afbca-107">Член</span><span class="sxs-lookup"><span data-stu-id="afbca-107">Member</span></span>|<span data-ttu-id="afbca-108">Описание</span><span class="sxs-lookup"><span data-stu-id="afbca-108">Description</span></span>|  
|------------|-----------------|  
|`pSidBuffer`|<span data-ttu-id="afbca-109">Адрес буфера потока.</span><span class="sxs-lookup"><span data-stu-id="afbca-109">Address of thread buffer.</span></span>|  
|`dwSidLen`|<span data-ttu-id="afbca-110">Длина буфера потока в байтах.</span><span class="sxs-lookup"><span data-stu-id="afbca-110">Length of thread buffer, in bytes.</span></span>|  
|`dwTid`|<span data-ttu-id="afbca-111">Идентификатор потока.</span><span class="sxs-lookup"><span data-stu-id="afbca-111">Thread ID.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="afbca-112">Требования</span><span class="sxs-lookup"><span data-stu-id="afbca-112">Requirements</span></span>  

 <span data-ttu-id="afbca-113">**Заголовок:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="afbca-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afbca-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="afbca-114">See also</span></span>

- [<span data-ttu-id="afbca-115">Метод SetNotifyFilter</span><span class="sxs-lookup"><span data-stu-id="afbca-115">SetNotifyFilter Method</span></span>](inotifysource2-setnotifyfilter-method.md)
- [<span data-ttu-id="afbca-116">Структуры хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="afbca-116">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)
