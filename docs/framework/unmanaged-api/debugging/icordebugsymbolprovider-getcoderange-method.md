---
title: Метод ICorDebugSymbolProvider::GetCodeRange
ms.date: 03/30/2017
ms.assetid: 49a2451f-d250-4e73-aa96-9ff49d9f11c6
ms.openlocfilehash: a9c1a4a625196d7430e365916cc7c2b67bf94127
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83376094"
---
# <a name="icordebugsymbolprovidergetcoderange-method"></a>Метод ICorDebugSymbolProvider::GetCodeRange
Получает начальный адрес метода и размер для указанного относительного виртуального адреса (RVA) в методе.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetCodeRange(  
   [in] ULONG32 codeRva,
   [out] ULONG32* pCodeStartAddress,
   [out] ULONG32* pCodeSize  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `codeRva`  
 [in] Относительный виртуальный адрес (RVA) в методе.  
  
 `pCodeStartAddress`  
 [out] Указатель на начальный адрес метода.  
  
 `pCodeSize`  
 Указатель на размер кода метода (число байтов кода метода).  
  
## <a name="remarks"></a>Remarks  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
