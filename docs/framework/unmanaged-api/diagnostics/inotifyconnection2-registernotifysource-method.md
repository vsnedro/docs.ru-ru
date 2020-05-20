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
ms.openlocfilehash: b7fa777466e2c7edd7b3110dd91e776785c63c58
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442076"
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
  
## <a name="see-also"></a>Дополнительно

- [Интерфейс INotifyConnection2](inotifyconnection2-interface.md)
- [Интерфейс INotifySource2](inotifysource2-interface.md)
- [Интерфейс INotifySink2](inotifysink2-interface.md)
- [Метод UnregisterNotifySource](inotifyconnection2-unregisternotifysource-method.md)
