---
title: Метод INotifySink2::OnSyncCallReturn
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallReturn
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallReturn
helpviewer_keywords:
- OnSyncCallReturn method [.NET Framework debugging]
- INotifySink2::OnSyncCallReturn method [.NET Framework debugging]
ms.assetid: c1bda761-6292-4750-a14b-7d5db8f33456
topic_type:
- apiref
ms.openlocfilehash: fe2db3df688f91ec6e1aadd8cc3bb43726e5c30f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719961"
---
# <a name="inotifysink2onsynccallreturn-method"></a><span data-ttu-id="0f28b-102">Метод INotifySink2::OnSyncCallReturn</span><span class="sxs-lookup"><span data-stu-id="0f28b-102">INotifySink2::OnSyncCallReturn Method</span></span>

<span data-ttu-id="0f28b-103">Вызывается при возвращении вызова.</span><span class="sxs-lookup"><span data-stu-id="0f28b-103">Gets invoked when a call returns.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f28b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0f28b-104">Syntax</span></span>  
  
```cpp  
HRESULT OnSyncCallReturn  
(  
    [in]  CALL_ID   in_CallID,  
    [in, size_is(in_BufferSize)] BYTE*  in_pBuffer,  
    [in]  DWORD     in_BufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f28b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0f28b-105">Parameters</span></span>  

 `in_CallID`  
 <span data-ttu-id="0f28b-106">окне Идентификатор возвращаемого вызова.</span><span class="sxs-lookup"><span data-stu-id="0f28b-106">[in] ID of the call being returned from.</span></span> <span data-ttu-id="0f28b-107">См. раздел [структура CALL_ID](call-id-structure.md).</span><span class="sxs-lookup"><span data-stu-id="0f28b-107">See [CALL_ID Structure](call-id-structure.md).</span></span>  
  
 `in_pBuffer`  
 <span data-ttu-id="0f28b-108">окне Буфер вызова.</span><span class="sxs-lookup"><span data-stu-id="0f28b-108">[in] Call buffer.</span></span>  
  
 `in_BufferSize`  
 <span data-ttu-id="0f28b-109">окне Размер буфера вызова в байтах.</span><span class="sxs-lookup"><span data-stu-id="0f28b-109">[in] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0f28b-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0f28b-110">Return Value</span></span>  

 <span data-ttu-id="0f28b-111">S_OK, если метод выполнен.</span><span class="sxs-lookup"><span data-stu-id="0f28b-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f28b-112">Требования</span><span class="sxs-lookup"><span data-stu-id="0f28b-112">Requirements</span></span>  

 <span data-ttu-id="0f28b-113">**Заголовок:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="0f28b-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f28b-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0f28b-114">See also</span></span>

- [<span data-ttu-id="0f28b-115">Интерфейс INotifySink2</span><span class="sxs-lookup"><span data-stu-id="0f28b-115">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="0f28b-116">Интерфейс INotifySource2</span><span class="sxs-lookup"><span data-stu-id="0f28b-116">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="0f28b-117">Интерфейс INotifyConnection2</span><span class="sxs-lookup"><span data-stu-id="0f28b-117">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)
