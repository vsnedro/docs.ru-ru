---
description: 'Дополнительные сведения о методе: INotifySink2:: Онсинккаллексит'
title: Метод INotifySink2::OnSyncCallExit
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallExit
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallExit
helpviewer_keywords:
- INotifySink2::OnSyncCallExit method [.NET Framework debugging]
- OnSyncCallExit method [.NET Framework debugging]
ms.assetid: d9d7600e-a8f5-443a-96de-67d26e130f2d
topic_type:
- apiref
ms.openlocfilehash: 2de55c3b7956576049e4ad65b2cb6fbc69fa84af
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800270"
---
# <a name="inotifysink2onsynccallexit-method"></a>Метод INotifySink2::OnSyncCallExit

Вызывается при выходе из вызова.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT OnSyncCallExit  
(  
    [in]  CALL_ID   in_CallID,  
    [out, size_is(, *out_pBufferSize)] BYTE**  out_ppBuffer,  
    [out] DWORD*    out_pBufferSize  
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
  
## <a name="see-also"></a>См. также

- [Интерфейс INotifySink2](inotifysink2-interface.md)
- [Интерфейс INotifySource2](inotifysource2-interface.md)
- [Интерфейс INotifyConnection2](inotifyconnection2-interface.md)
