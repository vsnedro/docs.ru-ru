---
description: 'Дополнительные сведения о методе ICorDebugThread:: Креативал'
title: Метод ICorDebugThread::CreateEval
ms.date: 03/30/2017
api_name:
- ICorDebugThread.CreateEval
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::CreateEval
helpviewer_keywords:
- CreateEval method [.NET Framework debugging]
- ICorDebugThread::CreateEval method [.NET Framework debugging]
ms.assetid: 36605067-33d3-4579-9c72-fb0e551ab0f1
topic_type:
- apiref
ms.openlocfilehash: a789840e099a14b584e5713bee12f5c4b0717fe7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659391"
---
# <a name="icordebugthreadcreateeval-method"></a>Метод ICorDebugThread::CreateEval

Создает объект ICorDebugEval, который собирает и предоставляет функциональные возможности этого ICorDebugThread.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CreateEval (  
    [out] ICorDebugEval   **ppEval  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ppEval`  
 заполняет Указатель на адрес `ICorDebugEval` объекта, который собирает и предоставляет функциональные возможности этого потока.  
  
## <a name="remarks"></a>Remarks  

 Объект вычисления перед выполнением вычислений выдаст новую цепочку в потоке. Это прерывает вычисления, выполняемые в данный момент в потоке до завершения оценки.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
