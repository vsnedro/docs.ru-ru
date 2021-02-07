---
description: 'Дополнительные сведения о методе: ICorDebugProcess2:: Сетунманажедбреакпоинт'
title: Метод ICorDebugProcess2::SetUnmanagedBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.SetUnmanagedBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::SetUnmanagedBreakpoint
helpviewer_keywords:
- ICorDebugProcess2::SetUnmanagedBreakpoint method [.NET Framework debugging]
- SetUnmanagedBreakpoint method [.NET Framework debugging]
ms.assetid: 93829d15-d942-4e2d-b7a4-dfc9d7fb96be
topic_type:
- apiref
ms.openlocfilehash: 7989f0fc9908941513b7d099fde81c79cef82c5b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746546"
---
# <a name="icordebugprocess2setunmanagedbreakpoint-method"></a>Метод ICorDebugProcess2::SetUnmanagedBreakpoint

Задает неуправляемую точку останова в указанном смещении машинного образа.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetUnmanagedBreakpoint (  
    [in]  CORDB_ADDRESS    address,  
    [in]  ULONG32          bufsize,  
    [out, size_is(bufsize), length_is(*bufLen)]
        BYTE               buffer[],  
    [out] ULONG32          *bufLen  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `address`  
 окне `CORDB_ADDRESS` Объект, указывающий смещение машинного образа.  
  
 `bufsize`  
 окне Размер массива в байтах `buffer` .  
  
 `buffer`  
 заполняет Массив, содержащий код операции, который заменяется точкой останова.  
  
 `bufLen`  
 заполняет Указатель на число байтов, возвращенных в `buffer` массиве.  
  
## <a name="remarks"></a>Remarks  

 Если смещение машинного образа находится в среде CLR, точка останова будет пропущена. Это позволяет среде CLR избежать диспетчеризации точки останова по внешнему каналу, когда точка останова задается отладчиком.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
