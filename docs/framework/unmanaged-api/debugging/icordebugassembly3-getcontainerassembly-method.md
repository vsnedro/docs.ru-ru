---
title: Метод ICorDebugAssembly3::GetContainerAssembly
ms.date: 03/30/2017
ms.assetid: f5fddeb6-b82e-4ebb-b432-849ce8513c77
ms.openlocfilehash: 068a08d70f2443edfe0970ec1ffb8cba9953c6b9
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894849"
---
# <a name="icordebugassembly3getcontainerassembly-method"></a>Метод ICorDebugAssembly3::GetContainerAssembly
Возвращает контейнерную сборку этого объекта `ICorDebugAssembly3`.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetContainerAssembly(  
    ICorDebugAssembly **ppAssembly  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppAssembly`  
 Указатель на адрес объекта ICorDebugAssembly, который представляет сборку контейнера, или **значение NULL** , если вызов метода завершается ошибкой.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `S_OK`значение, если вызов метода выполнен. `S_FALSE`в противном случае `ppAssembly` , и имеет **значение NULL**.  
  
## <a name="remarks"></a>Remarks  
 Если эта сборка была объединена с другими сборками внутри одиночной контейнерной сборки, этот метод возвращает контейнерную сборку. Дополнительные сведения и терминология см. в разделе [ICorDebugProcess6:: EnableVirtualModuleSplitting](icordebugprocess6-enablevirtualmodulesplitting-method.md) .  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugAssembly3](icordebugassembly3-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
