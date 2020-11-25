---
title: Метод INotifyConnection2::RegisterNotifySource
ms.date: 03/30/2017
api_name:
- INotifyConnection2.RegisterNotifySource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifyConnection2::RegisterNotifySource
helpviewer_keywords:
- INotifyConnection2::RegisterNotifySource method [.NET Framework debugging]
- RegisterNotifySource method [.NET Framework debugging]
ms.assetid: 2632da80-6e4b-4429-8dee-b382745a5f81
topic_type:
- apiref
ms.openlocfilehash: 1286dd970e437af0a8b607ed050ab4838f73a41f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720052"
---
# <a name="inotifyconnection2registernotifysource-method"></a>Метод INotifyConnection2::RegisterNotifySource

Устанавливает указанный источник уведомления.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT RegisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource,  
    [out] INotifySink2**   out_ppNotifySink  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `in_pNotifySource`  
 окне Указывает объект, который будет использоваться в качестве источника уведомления.  
  
 `out_ppNotifySink`  
 заполняет Получает объект, который будет использоваться в качестве приемника уведомлений.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс INotifyConnection2](inotifyconnection2-interface.md)
- [Интерфейс INotifySource2](inotifysource2-interface.md)
- [Интерфейс INotifySink2](inotifysink2-interface.md)
- [Метод UnregisterNotifySource](inotifyconnection2-unregisternotifysource-method.md)
