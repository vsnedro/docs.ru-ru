---
title: Метод ICorDebugMemoryBuffer::GetStartAddress
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
ms.openlocfilehash: f76bf1479db987e4956d8b876f67d629d927f956
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710768"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a>Метод ICorDebugMemoryBuffer::GetStartAddress

Возвращает начальный адрес буфера памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `address`  
 [out] Указатель на начальный адрес буфера памяти.  
  
## <a name="remarks"></a>Комментарии  
  
> [!WARNING]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
