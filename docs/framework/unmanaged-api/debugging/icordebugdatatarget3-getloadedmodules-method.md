---
title: Метод ICorDebugDataTarget3::GetLoadedModules
ms.date: 03/30/2017
ms.assetid: 9a48c05b-1949-416e-933c-52549b6fcf5e
ms.openlocfilehash: efbada02b7a24e0a7ed613b86b8a4a1a0b5b051a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713757"
---
# <a name="icordebugdatatarget3getloadedmodules-method"></a>Метод ICorDebugDataTarget3::GetLoadedModules

Возвращает список модулей, загруженных на данный момент.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetLoadedModules(  
   [in] ULONG32 cRequestedModules,  
   [out] ULONG32 *pcFetchedModules,  
   [out, size_is(cRequestedModules), length_is(*pcFetchedModules)] ICorDebugLoadedModule *pLoadedModules[]  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `cRequestedModules`  
 [in] Число модулей, для которых запрашиваются сведения.  
  
 `pcFetchedModules`  
 [out] Указатель на число модулей, о которых возвращаются сведения.  
  
 `pLoadedModules`  
 заполняет Указатель на массив объектов [икордебуглоадедмодуле](icordebugloadedmodule-interface.md) , которые предоставляют сведения о загруженных модулях.  
  
## <a name="remarks"></a>Комментарии  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugDataTarget3](icordebugdatatarget3-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
