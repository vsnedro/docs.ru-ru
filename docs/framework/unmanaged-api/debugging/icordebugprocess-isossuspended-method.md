---
description: 'Дополнительные сведения о методе: ICorDebugProcess:: IsOSSuspended'
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
ms.openlocfilehash: aa5e438418330d9fee51fcdb56a617421df06904
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746775"
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
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
