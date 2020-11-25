---
title: Метод ICorDebugILFrame::GetIP
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::GetIP method [.NET Framework debugging]
ms.assetid: 18217ba1-1776-4297-a3b9-f77e64b0fead
topic_type:
- apiref
ms.openlocfilehash: 314d2a06c8e246a42b315690dc9fe4b507db285a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703178"
---
# <a name="icordebugilframegetip-method"></a>Метод ICorDebugILFrame::GetIP

Возвращает значение указателя инструкции и битовое значение сочетания, которое описывает, как было получено значение указателя инструкции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32               *pnOffset,
    [out] CorDebugMappingResult *pMappingResult  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pnOffset`  
 заполняет Значение указателя инструкции.  
  
 `pMappingResult`  
 заполняет Указатель на побитовую комбинацию значений перечисления Кордебугмаппингресулт, описывающих, как было получено значение указателя инструкции.  
  
## <a name="remarks"></a>Комментарии  

 Значение указателя инструкции является смещением кадра стека в коде MSIL для функции. Если кадр стека активен, то этот адрес является следующей инструкцией для выполнения. Если кадр стека неактивен, этот адрес является следующей инструкцией для выполнения при повторной активации кадра стека.  
  
 Если этот кадр является JIT-скомпилированным кадром, то значение указателя инструкции будет определяться в обратном направлении от фактического указателя инструкций в машинном виде, поэтому значение может быть только приблизительным.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
