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
ms.openlocfilehash: ff1dabcfc366607639cd98be4392f8dd59dc83a1
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442011"
---
# <a name="inotifysink2onsynccallreturn-method"></a>Метод INotifySink2::OnSyncCallReturn
Вызывается при возвращении вызова.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT OnSyncCallReturn  
(  
    [in]  CALL_ID   in_CallID,  
    [in, size_is(in_BufferSize)] BYTE*  in_pBuffer,  
    [in]  DWORD     in_BufferSize  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `in_CallID`  
 окне Идентификатор возвращаемого вызова. См. раздел [структура CALL_ID](call-id-structure.md).  
  
 `in_pBuffer`  
 окне Буфер вызова.  
  
 `in_BufferSize`  
 окне Размер буфера вызова в байтах.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK, если метод выполнен.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>Дополнительно

- [Интерфейс INotifySink2](inotifysink2-interface.md)
- [Интерфейс INotifySource2](inotifysource2-interface.md)
- [Интерфейс INotifyConnection2](inotifyconnection2-interface.md)
