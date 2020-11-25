---
title: Метод ICorDebugNativeFrame::GetIP
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
- ICorDebugNativeFrame::GetIP method [.NET Framework debugging]
ms.assetid: 99f693f3-d3b9-4fd8-9d09-b8efd03f7b67
topic_type:
- apiref
ms.openlocfilehash: c9c0598f8e7b3e8654124f50663c912f3cd61659
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709312"
---
# <a name="icordebugnativeframegetip-method"></a>Метод ICorDebugNativeFrame::GetIP

Возвращает расположение смещения машинного кода, в котором в данный момент установлен указатель инструкции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32           *pnOffset  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pnOffset`  
 заполняет Указатель на положение смещения в машинном коде.  
  
## <a name="remarks"></a>Комментарии  

 Если кадр стека, представленный этим «ICorDebugNativeFrame», активен, то смещение — это адрес следующей инструкции, которая будет выполнена. Если этот кадр стека неактивен, то смещение является адресом следующей инструкции, которая будет выполнена при повторной активации кадра стека.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел
