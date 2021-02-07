---
description: 'Дополнительные сведения о методе: ICorDebugChain:: EnumerateFrames'
title: Метод ICorDebugChain::EnumerateFrames
ms.date: 03/30/2017
api_name:
- ICorDebugChain.EnumerateFrames
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::EnumerateFrames method
helpviewer_keywords:
- EnumerateFrames method [.NET Framework debugging]
- ICorDebugChain::EnumerateFrames method [.NET Framework debugging]
ms.assetid: 9fcefa98-750d-4168-8915-8173a43accf2
topic_type:
- apiref
ms.openlocfilehash: 45bf69760eeccebada743d81e859a19e209b611a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711600"
---
# <a name="icordebugchainenumerateframes-method"></a>Метод ICorDebugChain::EnumerateFrames

Возвращает перечислитель, содержащий все управляемые кадры стека в цепочке, начиная с самого последнего кадра.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ppFrames`  
 заполняет Указатель на адрес объекта ICorDebugFrameEnum, который является перечислителем для кадров стека.  
  
## <a name="remarks"></a>Remarks  

 Цепочка представляет физический стек вызовов для потока.  
  
 `EnumerateFrames`Метод должен вызываться только для управляемых цепочек. API отладки не предоставляет методы для получения кадров, содержащихся в неуправляемых цепочках. Для получения этих сведений отладчик должен использовать другие средства.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
