---
description: 'Дополнительные сведения о методе: INotifySink2:: OnSyncCallEnter'
title: Метод INotifySink2::OnSyncCallEnter
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallEnter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallEnter
helpviewer_keywords:
- INotifySink2::OnSyncCallEnter method [.NET Framework debugging]
- OnSyncCallEnter method [.NET Framework debugging]
ms.assetid: e33265be-c25d-4145-ad02-c3e89d6f26c1
topic_type:
- apiref
ms.openlocfilehash: e7537b16ec8ea8d92ad92498c1bfdac5a9de6475
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800283"
---
# <a name="inotifysink2onsynccallenter-method"></a>Метод INotifySink2::OnSyncCallEnter

Вызывается при вводе вызова.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT OnSyncCallEnter  
(  
    [in]  CALL_ID   in_CallID,  
    [in, size_is(in_BufferSize)] BYTE*  in_pBuffer,  
    [in]  DWORD     in_BufferSize  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `in_CallID`  
 окне Идентификатор вводимых вызовов. См. раздел [структура CALL_ID](call-id-structure.md).  
  
 `in_pBuffer`  
 окне Буфер вызова.  
  
 `in_BufferSize`  
 окне Размер буфера вызова в байтах.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>См. также

- [Интерфейс INotifySink2](inotifysink2-interface.md)
- [Интерфейс INotifySource2](inotifysource2-interface.md)
- [Интерфейс INotifyConnection2](inotifyconnection2-interface.md)
