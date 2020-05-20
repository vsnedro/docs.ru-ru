---
title: Метод INotifySink2::OnSyncCallOut
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallOut
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallOut
helpviewer_keywords:
- INotifySink2::OnSyncCallOut method [.NET Framework debugging]
- OnSyncCallOut method [.NET Framework debugging]
ms.assetid: 97f15656-8677-4079-8553-a1d8603355d6
topic_type:
- apiref
ms.openlocfilehash: ce0e192a9d7d5abf56a55f844cf886c386f1c563
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441998"
---
# <a name="inotifysink2onsynccallout-method"></a><span data-ttu-id="bfeb0-102">Метод INotifySink2::OnSyncCallOut</span><span class="sxs-lookup"><span data-stu-id="bfeb0-102">INotifySink2::OnSyncCallOut Method</span></span>
<span data-ttu-id="bfeb0-103">Вызывается, когда вызывается метод out.</span><span class="sxs-lookup"><span data-stu-id="bfeb0-103">Gets invoked when a call is out.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfeb0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bfeb0-104">Syntax</span></span>  
  
```cpp  
HRESULT OnSyncCallOut  
(  
    [in]  CALL_ID  in_CallID,  
    [out, size_is(, *out_pBufferSize)] BYTE**  out_ppBuffer,  
    [out] DWORD*   out_pBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bfeb0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bfeb0-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="bfeb0-106">окне Идентификатор выходного вызова. См. раздел [структура CALL_ID](call-id-structure.md).</span><span class="sxs-lookup"><span data-stu-id="bfeb0-106">[in] ID of the call that is out. See [CALL_ID Structure](call-id-structure.md).</span></span>  
  
 `out_ppBuffer`  
 <span data-ttu-id="bfeb0-107">заполняет Буфер вызова.</span><span class="sxs-lookup"><span data-stu-id="bfeb0-107">[out] Call buffer.</span></span>  
  
 `out_pBufferSize`  
 <span data-ttu-id="bfeb0-108">заполняет Размер буфера вызова в байтах.</span><span class="sxs-lookup"><span data-stu-id="bfeb0-108">[out] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bfeb0-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bfeb0-109">Return Value</span></span>  
 <span data-ttu-id="bfeb0-110">S_OK, если метод выполнен.</span><span class="sxs-lookup"><span data-stu-id="bfeb0-110">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfeb0-111">Требования</span><span class="sxs-lookup"><span data-stu-id="bfeb0-111">Requirements</span></span>  
 <span data-ttu-id="bfeb0-112">**Заголовок:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="bfeb0-112">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfeb0-113">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="bfeb0-113">See also</span></span>

- [<span data-ttu-id="bfeb0-114">Интерфейс INotifySink2</span><span class="sxs-lookup"><span data-stu-id="bfeb0-114">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="bfeb0-115">Интерфейс INotifySource2</span><span class="sxs-lookup"><span data-stu-id="bfeb0-115">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="bfeb0-116">Интерфейс INotifyConnection2</span><span class="sxs-lookup"><span data-stu-id="bfeb0-116">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)
