---
title: Метод ICorDebugMergedAssemblyRecord::GetVersion
ms.date: 03/30/2017
ms.assetid: c6858b06-ae26-4312-b325-ea6025016675
ms.openlocfilehash: 7352a77fc8f41124d7e6c78a3dfc6ccd6d3a94aa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710510"
---
# <a name="icordebugmergedassemblyrecordgetversion-method"></a>Метод ICorDebugMergedAssemblyRecord::GetVersion

Возвращает сведения о версии сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetVersion(  
   [out] USHORT *pMajor,
   [out] USHORT *pMinor,
   [out] USHORT *pBuild,
   [out] USHORT *pRevision  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pMajor`  
 [out] Указатель на основной номер версии.  
  
 `pMinor`  
 [out] Указатель на дополнительный номер версии.  
  
 `pBuild`  
 [out] Указатель на номер сборки.  
  
 `pRevision`  
 [out] Указатель на номер редакции.  
  
## <a name="remarks"></a>Комментарии  

 Сведения о версии сборки см в разделе, посвященном классу <xref:System.Version>.  
  
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
