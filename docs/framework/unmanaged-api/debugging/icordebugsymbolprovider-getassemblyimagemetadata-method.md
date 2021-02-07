---
description: 'Дополнительные сведения о методе: метод icordebugsymbolprovider:: GetAssemblyImageMetadata'
title: Метод ICorDebugSymbolProvider::GetAssemblyImageMetadata
ms.date: 03/30/2017
ms.assetid: c3c9de67-b865-4ecf-b887-1f1d0719a0c0
ms.openlocfilehash: 4abe5cc2b2a31f89e6ca4f8fc643f26eac276515
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717190"
---
# <a name="icordebugsymbolprovidergetassemblyimagemetadata-method"></a>Метод ICorDebugSymbolProvider::GetAssemblyImageMetadata

Возвращает метаданные из объединенной сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetAssemblyImageMetadata(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ppMemoryBuffer`  
 заполняет Указатель на адрес объекта [икордебугмеморибуффер](icordebugmemorybuffer-interface.md) , который содержит сведения о размере и адресе метаданных объединенной сборки.  
  
## <a name="remarks"></a>Remarks  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
