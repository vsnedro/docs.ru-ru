---
title: Метод ICorDebugDataTarget2::GetImageFromPointer
ms.date: 03/30/2017
ms.assetid: 939cabe1-b647-4090-b662-eeec23c6c58d
ms.openlocfilehash: 41385fe915733f052af67c82d984c8b9d853c579
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713825"
---
# <a name="icordebugdatatarget2getimagefrompointer-method"></a>Метод ICorDebugDataTarget2::GetImageFromPointer

Возвращает базовый адрес и размер модуля из адреса в этом модуле.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetImageFromPointer(  
   [in] CORDB_ADDRESS addr,
   [out] CORDB_ADDRESS *pImageBase,
   [out] ULONG32 *pSize  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `addr`  
 Значение [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) , представляющее адрес в модуле.  
  
 `pImageBase`  
 заполняет Значение [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) , представляющее базовый адрес модуля.  
  
 `pSize`  
 Указатель на размер модуля.  
  
## <a name="remarks"></a>Комментарии  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugDataTarget2](icordebugdatatarget2-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
