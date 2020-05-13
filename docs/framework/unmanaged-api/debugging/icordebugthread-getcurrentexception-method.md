---
title: Метод ICorDebugThread::GetCurrentException
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetCurrentException
helpviewer_keywords:
- ICorDebugThread::GetCurrentException method [.NET Framework debugging]
- GetCurrentException method [.NET Framework debugging]
ms.assetid: 331ed465-a195-4359-8584-b82c6098b29b
topic_type:
- apiref
ms.openlocfilehash: 3a4da6f958407c0b704ffb7372a77b7f022fc824
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379769"
---
# <a name="icordebugthreadgetcurrentexception-method"></a>Метод ICorDebugThread::GetCurrentException
Возвращает указатель интерфейса на объект ICorDebugValue, представляющий исключение, которое в данный момент вызывается управляемым кодом.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetCurrentException (  
    [out] ICorDebugValue **ppExceptionObject  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppExceptionObject`  
 заполняет Указатель на адрес `ICorDebugValue` объекта, представляющий исключение, которое в данный момент вызывается управляемым кодом.  
  
## <a name="remarks"></a>Remarks  
 Объект исключения будет существовать с момента возникновения исключения до конца `catch` блока. Вычисление функции, выполняемое методами ICorDebugEval, очистит объект исключения при установке и восстановит его по завершении.  
  
 Исключения могут быть вложенными (например, если исключение создается в фильтре или в вычислении функции), поэтому в одном потоке может быть несколько необработанных исключений. `GetCurrentException`Возвращает последнее исключение.  
  
 Объект и тип исключения могут меняться в течение всего времени существования исключения. Например, после возникновения исключения типа x среда CLR может закончится нехваткой памяти и повысить ее до исключения нехватки памяти.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
