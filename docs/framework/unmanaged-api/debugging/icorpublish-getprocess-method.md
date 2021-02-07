---
description: 'Дополнительные сведения о методе: ICorPublish:: onprocess'
title: Метод ICorPublish::GetProcess
ms.date: 03/30/2017
api_name:
- ICorPublish.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::GetProcess
helpviewer_keywords:
- ICorPublish::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorPublish interface [.NET Framework debugging]
ms.assetid: c5143805-2eb7-45b8-85ed-c8fb34df1084
topic_type:
- apiref
ms.openlocfilehash: d288a772274618cc99b63a68b37e84e543957b44
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721987"
---
# <a name="icorpublishgetprocess-method"></a>Метод ICorPublish::GetProcess

Возвращает экземпляр [ICorPublishProcess](icorpublishprocess-interface.md) , представляющий процесс с указанным идентификатором.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetProcess(  
    [in] unsigned              pid,
    [out] ICorPublishProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pid`  
 окне Идентификатор процесса.  
  
 `ppProcess`  
 заполняет Указатель на адрес `ICorPublishProcess` экземпляра, который представляет процесс.  
  
## <a name="remarks"></a>Remarks  

 `GetProcess` завершается ошибкой, если процесс не существует или не является управляемым процессом, который может быть отлажен текущим пользователем.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Корпуб. idl, Корпуб. h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorPublish](icorpublish-interface.md)
