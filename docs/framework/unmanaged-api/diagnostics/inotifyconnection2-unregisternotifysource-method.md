---
title: Метод INotifyConnection2::UnregisterNotifySource
ms.date: 03/30/2017
api_name:
- INotifyConnection2.UnregisterNotifySource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifyConnection2::UnregisterNotifySource
helpviewer_keywords:
- INotifyConnection2::UnregisterNotifySource method [.NET Framework debugging]
- UnregisterNotifySource method [.NET Framework debugging]
ms.assetid: 2fc6c715-646f-41fd-9c12-c59b40575269
topic_type:
- apiref
ms.openlocfilehash: 9d0fcdcd4fe1561f7565586e3327c6d3d7e0fe0a
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442050"
---
# <a name="inotifyconnection2unregisternotifysource-method"></a>Метод INotifyConnection2::UnregisterNotifySource
Удаляет указанный объект источника уведомления из соединения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT UnregisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `in_pNotifySource`  
 окне Отменяется регистрация объекта уведомления.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK, если метод выполнен.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>Дополнительно

- [Интерфейс INotifyConnection2](inotifyconnection2-interface.md)
- [Интерфейс INotifySource2](inotifysource2-interface.md)
- [Интерфейс INotifySink2](inotifysink2-interface.md)
- [Метод RegisterNotifySource](inotifyconnection2-registernotifysource-method.md)
