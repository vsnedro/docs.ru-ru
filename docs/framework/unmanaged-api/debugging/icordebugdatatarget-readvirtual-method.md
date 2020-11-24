---
title: Метод ICorDebugDataTarget::ReadVirtual
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.ReadVirtual Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::ReadVirtual
helpviewer_keywords:
- ICorDebugDataTarget::ReadVirtual method [.NET Framework debugging]
- ReadVirtual method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: 55e57640-b3d2-413d-b4f4-fbc27fb8e37c
topic_type:
- apiref
ms.openlocfilehash: 8fb0cfc72867653eaff65f3183dacf9191604290
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679732"
---
# <a name="icordebugdatatargetreadvirtual-method"></a>Метод ICorDebugDataTarget::ReadVirtual

Возвращает блок непрерывной памяти, начиная с указанного адреса, и возвращает его в указанном буфере.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ReadVirtual(  
    [in] CORDB_ADDRESS   address,  
    [out, size_is(bytesRequested), length_is(*pBytesRead)]  
          BYTE *     pBuffer,  
    [in]  ULONG32    bytesRequested,  
    [out] ULONG32 *  pBytesRead);  
```  
  
## <a name="parameters"></a>Параметры  

 `address`  
 окне Начальный адрес запрошенной памяти.  
  
 `pbuffer`  
 заполняет Буфер, в котором будет храниться память.  
  
 `bytesRequested`  
 окне Число байтов, получаемых с целевого адреса.  
  
 `pBytesRead`  
 заполняет Число байтов, фактически считанных из целевого адреса. Это может быть меньше `bytesRequested` , чем.  
  
## <a name="remarks"></a>Комментарии  

 Если можно считать первый байт (с указанным начальным адресом), вызов должен вернуть результат (для поддержки эффективного чтения структур данных с самоописывающей длиной, например со строками, завершающимися нулем).  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugDataTarget](icordebugdatatarget-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
