---
description: 'Дополнительные сведения о методе: ICorDebugEval:: Abort'
title: Метод ICorDebugEval::Abort
ms.date: 03/30/2017
api_name:
- ICorDebugEval.Abort
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::Abort
helpviewer_keywords:
- Abort method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::Abort method [.NET Framework debugging]
ms.assetid: 7070b6d0-f2e0-44ff-b124-0944cd807e69
topic_type:
- apiref
ms.openlocfilehash: d61cb0d696a8a134d992bc8dbbfdb61103ef469f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99694322"
---
# <a name="icordebugevalabort-method"></a>Метод ICorDebugEval::Abort

Прерывает вычисление, которое данный объект ICorDebugEval сейчас выполняет.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Abort ();  
```  
  
## <a name="remarks"></a>Remarks  

 Если оценка является вложенной и не является самой последней, `Abort` метод может завершиться ошибкой.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
