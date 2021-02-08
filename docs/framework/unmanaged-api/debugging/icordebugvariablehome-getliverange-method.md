---
description: 'Дополнительные сведения о методе: IcorDebugVariableHome:: Жетливеранже'
title: 'Метод IcorDebugVariableHome:: Жетливеранже'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetLiveRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetLiveRange
helpviewer_keywords:
- ICorDebugVariableHome::GetLiveRange method [.NET Framework debugging]
- GetLiveRange method, ICorDebugVariableFrame interface [.NET Framework debugging]
ms.assetid: 87277e1a-1595-4729-9e25-d1c3ac18ce5f
topic_type:
- apiref
ms.openlocfilehash: daa53a164c7660826d44285ce21ecea1b649a727
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800842"
---
# <a name="icordebugvariablehomegetliverange-method"></a>Метод IcorDebugVariableHome:: Жетливеранже

Возвращает собственный диапазон, в котором эта переменная находится в режиме реального времени.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetLiveRange(  
    [out] ULONG32* pStartOffset,  
    [out] ULONG32 *pEndOffset  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pStartOffset`  
 заполняет Логическое смещение, при котором переменная впервые находится в режиме реального времени.  
  
 `pEndOffset`  
 заполняет Логическое смещение сразу после точки, в которой переменная была последней динамической.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugVariableHome](icordebugvariablehome-interface.md)
