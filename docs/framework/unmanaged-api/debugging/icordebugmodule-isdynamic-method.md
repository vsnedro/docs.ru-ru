---
description: 'Дополнительные сведения о методе: ICorDebugModule:: Dynamic'
title: Метод ICorDebugModule::IsDynamic
ms.date: 03/30/2017
api_name:
- ICorDebugModule.IsDynamic
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::IsDynamic
helpviewer_keywords:
- IsDynamic method [.NET Framework debugging]
- ICorDebugModule::IsDynamic method [.NET Framework debugging]
ms.assetid: 5eefe716-5025-4a4c-970c-c823cdc7bb87
topic_type:
- apiref
ms.openlocfilehash: 06ecb7aaffbe73da29bbdbba9446839db54c58c3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660106"
---
# <a name="icordebugmoduleisdynamic-method"></a>Метод ICorDebugModule::IsDynamic

Возвращает значение, указывающее, является ли этот модуль динамическим.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT IsDynamic(  
    [out] BOOL *pDynamic  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pDynamic`  
 [out] `true` значение, если этот модуль является динамическим; в противном случае — `false` .  
  
## <a name="remarks"></a>Remarks  

 Динамический модуль может добавлять новые классы и удалять существующие классы даже после загрузки модуля. Обратные вызовы [ICorDebugManagedCallback:: loadClass](icordebugmanagedcallback-loadclass-method.md) и [ICorDebugManagedCallback:: унлоадкласс](icordebugmanagedcallback-unloadclass-method.md) информируют отладчик о добавлении или удалении класса.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
