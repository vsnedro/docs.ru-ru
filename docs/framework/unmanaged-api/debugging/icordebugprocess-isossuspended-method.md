---
title: Метод ICorDebugProcess::IsOSSuspended
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.IsOSSuspended
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::IsOSSuspended
helpviewer_keywords:
- IsOSSuspended method [.NET Framework debugging]
- ICorDebugProcess::IsOSSuspended method [.NET Framework debugging]
ms.assetid: 83406cb2-5797-4402-872d-89c9516aefec
topic_type:
- apiref
ms.openlocfilehash: 9452f238bd84c9c185ca8e007acac563474d29df
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212065"
---
# <a name="icordebugprocessisossuspended-method"></a>Метод ICorDebugProcess::IsOSSuspended
Возвращает значение, указывающее, был ли заданный поток приостановлен в результате остановки этого процесса отладчиком.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT IsOSSuspended(  
    [in]  DWORD threadID,  
    [out] BOOL  *pbSuspended);  
```  
  
## <a name="parameters"></a>Параметры  
 `threadID`  
 окне Идентификатор рассматриваемого потока.  
  
 `pbSuspended`  
 заполняет Указатель на логическое значение, равное, `true` если указанный поток был приостановлен; в противном случае `pbSuspended` — * `false` .  
  
## <a name="remarks"></a>Remarks  
 Если указанный поток был приостановлен в результате остановки этого процесса отладчиком, счетчик приостановки Win32 указанного потока увеличивается на единицу. Пользовательский интерфейс отладчика может захотеть использовать эту информацию при отображении счетчика приостановки операционной системы (ОС) для пользователя.  
  
 `IsOSSuspended`Метод имеет смысл только в контексте неуправляемой отладки. Во время управляемой отладки потоки приостанавливаются совместно, а не с приостановленной ОС.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
