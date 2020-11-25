---
title: Метод ICorDebugMergedAssemblyRecord::GetIndex
ms.date: 03/30/2017
ms.assetid: 98701444-b9bc-4978-9548-89ac3394147d
ms.openlocfilehash: 3056d22f5ddc1b11b79ee072aba68ce3ad40e8da
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710640"
---
# <a name="icordebugmergedassemblyrecordgetindex-method"></a>Метод ICorDebugMergedAssemblyRecord::GetIndex

Возвращает индекс префикса сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetIndex(  
   [out] ULONG32 *pIndex  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pIndex`  
 [out] Указатель на индекс префикса.  
  
## <a name="remarks"></a>Комментарии  

 Индекс префикса используется для предотвращения конфликтов имен в типе объединенных метаданных.  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugMergedAssemblyRecord](icordebugmergedassemblyrecord-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
