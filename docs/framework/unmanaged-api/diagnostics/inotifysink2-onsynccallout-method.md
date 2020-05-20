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
# <a name="inotifysink2onsynccallout-method"></a>Метод INotifySink2::OnSyncCallOut
Вызывается, когда вызывается метод out.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT OnSyncCallOut  
(  
    [in]  CALL_ID  in_CallID,  
    [out, size_is(, *out_pBufferSize)] BYTE**  out_ppBuffer,  
    [out] DWORD*   out_pBufferSize  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `in_CallID`  
 окне Идентификатор выходного вызова. См. раздел [структура CALL_ID](call-id-structure.md).  
  
 `out_ppBuffer`  
 заполняет Буфер вызова.  
  
 `out_pBufferSize`  
 заполняет Размер буфера вызова в байтах.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK, если метод выполнен.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>Дополнительно

- [Интерфейс INotifySink2](inotifysink2-interface.md)
- [Интерфейс INotifySource2](inotifysource2-interface.md)
- [Интерфейс INotifyConnection2](inotifyconnection2-interface.md)
