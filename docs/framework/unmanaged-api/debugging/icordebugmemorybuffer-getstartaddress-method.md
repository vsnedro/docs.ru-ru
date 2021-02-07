---
description: 'Дополнительные сведения о методе: Икордебугмеморибуффер:: Жетстартаддресс'
title: Метод ICorDebugMemoryBuffer::GetStartAddress
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
ms.openlocfilehash: 46720d70b8a1019e712b577b24dec5d4c3d5a31d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722715"
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
  
## <a name="remarks"></a>Remarks  
  
> [!WARNING]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
