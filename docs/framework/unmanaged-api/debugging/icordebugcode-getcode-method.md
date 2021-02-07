---
description: 'Дополнительные сведения о методе ICorDebugCode:: с кодом.'
title: Метод ICorDebugCode::GetCode
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetCode
helpviewer_keywords:
- ICorDebugCode::GetCode method [.NET Framework debugging]
- GetCode method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7137e3d1-1dad-48d8-8c37-16ac816534d3
topic_type:
- apiref
ms.openlocfilehash: 329770fac4f2b375c01dd68e4ea7114e59c609b5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711288"
---
# <a name="icordebugcodegetcode-method"></a>Метод ICorDebugCode::GetCode

Возвращает весь код для указанной функции, отформатированный для дизассемблирования. Этот метод не рекомендуется к использованию в платформа .NET Framework версии 2,0. Вместо этого используйте [ICorDebugCode2:: жеткодечункс](icordebugcode2-getcodechunks-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetCode (  
    [in] ULONG32     startOffset,
    [in] ULONG32     endOffset,  
    [in] ULONG32     cBufferAlloc,  
    [out, size_is(cBufferAlloc),  
        length_is(*pcBufferSize)] BYTE buffer[],  
    [out] ULONG32    *pcBufferSize  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `startOffset`  
 окне Смещение начала функции.  
  
 `endOffset`  
 окне Смещение конца функции.  
  
 `cBufferAlloc`  
 окне Размер `buffer` массива, в который будет возвращен код.  
  
 `buffer`  
 заполняет Массив, в который будет возвращен код.  
  
 `pcBufferSize`  
 заполняет Число возвращаемых байтов.  
  
## <a name="remarks"></a>Remarks  

 Если код функции делится на несколько блоков, они объединяются в порядке возрастания смещения в машинном коде. Границы инструкций не проверяются.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:** 1,1, 1,0  
  
## <a name="see-also"></a>См. также

- [Метод GetCodeChunks](icordebugcode2-getcodechunks-method.md)
