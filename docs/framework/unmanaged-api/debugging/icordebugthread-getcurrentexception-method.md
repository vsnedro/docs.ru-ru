---
description: 'Дополнительные сведения о методе ICorDebugThread:: Жеткуррентексцептион'
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
ms.openlocfilehash: cb241995520f26ca0e35f2b9e3b3187c2a2906a2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659170"
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
  
 Исключения могут быть вложенными (например, если исключение создается в фильтре или в вычислении функции), поэтому в одном потоке может быть несколько необработанных исключений. `GetCurrentException` Возвращает последнее исключение.  
  
 Объект и тип исключения могут меняться в течение всего времени существования исключения. Например, после возникновения исключения типа x среда CLR может закончится нехваткой памяти и повысить ее до исключения нехватки памяти.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
