---
description: 'Дополнительные сведения о методе: INotifySource2:: Сетнотифифилтер'
title: Метод INotifySource2::SetNotifyFilter
ms.date: 03/30/2017
api_name:
- INotifySource2.SetNotifyFilter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySource2::SetNotifyFilter
helpviewer_keywords:
- INotifySource2::SetNotifyFilter method [.NET Framework debugging]
- SetNotifyFilter method [.NET Framework debugging]
ms.assetid: 6351fc92-b126-4af6-9bf3-0a8ce92845fc
topic_type:
- apiref
ms.openlocfilehash: 2aaf2a5253f8a9acb67c4b538f109a7a62559d12
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800231"
---
# <a name="inotifysource2setnotifyfilter-method"></a>Метод INotifySource2::SetNotifyFilter

Назначает фильтр уведомлений для использования с этим источником.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetNotifyFilter  
(  
    [in]  NOTIFY_FILTER   in_NotifyFilter,  
    [in]  USER_THREAD*    in_pUserThreadFilter  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `in_NotifyFilter`  
 окне Побитовое сочетание значений перечисления [NOTIFY_FILTER](notify-filter-enumeration.md) , которые указывают обратные вызовы для API отладчика.  
  
 `in_pUserThreadFilter`  
 окне Указатель на структуру [USER_THREAD](user-thread-structure.md) , которая идентифицирует потоки для API отладчика.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** ProtocolNotify2. idl  
  
## <a name="see-also"></a>См. также

- [Интерфейс INotifySource2](inotifysource2-interface.md)
- [Интерфейс INotifyConnection2](inotifyconnection2-interface.md)
- [Интерфейс INotifySink2](inotifysink2-interface.md)
