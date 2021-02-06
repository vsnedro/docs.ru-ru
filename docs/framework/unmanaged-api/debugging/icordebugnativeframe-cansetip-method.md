---
description: 'Дополнительные сведения о методе: ICorDebugNativeFrame:: CanSetIP'
title: Метод ICorDebugNativeFrame::CanSetIP
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.CanSetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::CanSetIP
helpviewer_keywords:
- ICorDebugNativeFrame::CanSetIP method [.NET Framework debugging]
- CanSetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 13258ac6-f4e4-4f66-8fc3-f1244417a3c3
topic_type:
- apiref
ms.openlocfilehash: ec8f257b44143332063d7579b62dcc2afe0fccdd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637863"
---
# <a name="icordebugnativeframecansetip-method"></a>Метод ICorDebugNativeFrame::CanSetIP

Возвращает значение HRESULT, указывающее, можно ли задать для указателя инструкций (IP) заданное положение смещения в машинном коде.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32            nOffset  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `nOffset`  
 окне Требуемый параметр для указателя инструкции.  
  
## <a name="remarks"></a>Remarks  

 Используйте `CanSetIP` метод перед вызовом метода [ICorDebugNativeFrame:: SetIP](icordebugnativeframe-setip-method.md) . Если `CanSetIP` возвращает любое значение HRESULT, отличное от S_OK, можно по-прежнему вызывать `ICorDebugNativeFrame::SetIP` , но не существует гарантии того, что отладчик продолжит безопасность и правильное выполнение отлаживаемого кода.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
