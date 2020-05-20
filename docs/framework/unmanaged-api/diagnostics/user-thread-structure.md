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
ms.openlocfilehash: 5144feab742bc5dac36563d701d81a699d0bb2f3
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609447"
---
# <a name="user_thread-structure"></a><span data-ttu-id="22c01-102">Структура USER_THREAD</span><span class="sxs-lookup"><span data-stu-id="22c01-102">USER_THREAD Structure</span></span>
<span data-ttu-id="22c01-103">Предоставляет сведения отладчику о потоке.</span><span class="sxs-lookup"><span data-stu-id="22c01-103">Provides information to a debugger about a thread.</span></span> <span data-ttu-id="22c01-104">Дополнительные сведения см. в описании метода [INotifySource2:: сетнотифифилтер](inotifysource2-setnotifyfilter-method.md) .</span><span class="sxs-lookup"><span data-stu-id="22c01-104">For more information, see the [INotifySource2::SetNotifyFilter](inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22c01-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="22c01-105">Syntax</span></span>  
  
```cpp  
typedef struct tagUSER_THREAD  
{  
    BYTE    *pSidBuffer;  
    DWORD   dwSidLen;  
    DWORD   dwTid;  
} USER_THREAD;  
```  
  
## <a name="members"></a><span data-ttu-id="22c01-106">Участники</span><span class="sxs-lookup"><span data-stu-id="22c01-106">Members</span></span>  
  
|<span data-ttu-id="22c01-107">Член</span><span class="sxs-lookup"><span data-stu-id="22c01-107">Member</span></span>|<span data-ttu-id="22c01-108">Описание</span><span class="sxs-lookup"><span data-stu-id="22c01-108">Description</span></span>|  
|------------|-----------------|  
|`pSidBuffer`|<span data-ttu-id="22c01-109">Адрес буфера потока.</span><span class="sxs-lookup"><span data-stu-id="22c01-109">Address of thread buffer.</span></span>|  
|`dwSidLen`|<span data-ttu-id="22c01-110">Длина буфера потока в байтах.</span><span class="sxs-lookup"><span data-stu-id="22c01-110">Length of thread buffer, in bytes.</span></span>|  
|`dwTid`|<span data-ttu-id="22c01-111">Идентификатор потока.</span><span class="sxs-lookup"><span data-stu-id="22c01-111">Thread ID.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="22c01-112">Требования</span><span class="sxs-lookup"><span data-stu-id="22c01-112">Requirements</span></span>  
 <span data-ttu-id="22c01-113">**Заголовок:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="22c01-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22c01-114">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="22c01-114">See also</span></span>

- [<span data-ttu-id="22c01-115">Метод SetNotifyFilter</span><span class="sxs-lookup"><span data-stu-id="22c01-115">SetNotifyFilter Method</span></span>](inotifysource2-setnotifyfilter-method.md)
- [<span data-ttu-id="22c01-116">Структуры хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="22c01-116">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)
