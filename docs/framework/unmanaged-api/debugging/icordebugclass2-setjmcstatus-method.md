---
description: 'Дополнительные сведения о методе: ICorDebugClass2:: Сетжмкстатус'
title: Метод ICorDebugClass2::SetJMCStatus
ms.date: 03/30/2017
api_name:
- ICorDebugClass2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2::SetJMCStatus
helpviewer_keywords:
- ICorDebugClass2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 077e6c7f-f857-480c-bebb-76ee1de4e8fc
topic_type:
- apiref
ms.openlocfilehash: 28859522052fd9587dc3890eb4137929dbdc6763
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711483"
---
# <a name="icordebugclass2setjmcstatus-method"></a>Метод ICorDebugClass2::SetJMCStatus

Для каждого метода класса задает значение, указывающее, является ли метод определяемым пользователем кодом.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `bIsJustMyCode`  
 окне Задайте значение, чтобы `true` указать, что метод является определяемым пользователем кодом; в противном случае задайте для значение `false` .  
  
## <a name="remarks"></a>Remarks  

 Средство "только мой код" (JMC) пропускает код, не определенный пользователем. Определяемый пользователем код должен быть подмножеством отлаживаемого кода.  
  
 `SetJMCStatus` Возвращает значение HRESULT, равное S_FALSE, если не удается задать значение для какого бы то ни было метода, даже если оно успешно задает значение для всех остальных методов.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
