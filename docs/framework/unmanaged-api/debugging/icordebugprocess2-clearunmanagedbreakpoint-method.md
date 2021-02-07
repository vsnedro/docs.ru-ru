---
description: 'Дополнительные сведения о методе: ICorDebugProcess2:: Клеарунманажедбреакпоинт'
title: Метод ICorDebugProcess2::ClearUnmanagedBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.ClearUnmanagedBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::ClearUnmanagedBreakpoint
helpviewer_keywords:
- ClearUnmanagedBreakpoint method [.NET Framework debugging]
- ICorDebugProcess2::ClearUnmanagedBreakpoint method [.NET Framework debugging]
ms.assetid: 12ed0fff-7f0e-4d7a-bb70-b3376371f36c
topic_type:
- apiref
ms.openlocfilehash: fba31a479e9bac525109e14c02995e78918d4c17
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746637"
---
# <a name="icordebugprocess2clearunmanagedbreakpoint-method"></a>Метод ICorDebugProcess2::ClearUnmanagedBreakpoint

Удаляет ранее установленную точку останова по указанному адресу.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ClearUnmanagedBreakpoint (  
    [in] CORDB_ADDRESS   address  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `address`  
 окне `CORDB_ADDRESS` Значение типа, указывающее адрес, по которому была задана точка останова.  
  
## <a name="remarks"></a>Remarks  

 Указанная точка останова была ранее задана предыдущим вызовом метода [ICorDebugProcess2:: сетунманажедбреакпоинт](icordebugprocess2-setunmanagedbreakpoint-method.md).  
  
 `ClearUnmanagedBreakpoint`Метод может быть вызван во время выполнения отлаживаемого процесса.  
  
 `ClearUnmanagedBreakpoint`Метод возвращает код ошибки, если отладчик присоединен в режиме «только управляемый» или если в указанном адресе не существует точки останова.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
