---
description: 'Дополнительные сведения о методе: ICorDebugFunction2:: Жетжмкстатус'
title: Метод ICorDebugFunction2::GetJMCStatus
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.GetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::GetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::GetJMCStatus method [.NET Framework debugging]
- GetJMCStatus method [.NET Framework debugging]
ms.assetid: 840a71ed-bf5a-4f5e-8ed6-762222b34493
topic_type:
- apiref
ms.openlocfilehash: 42c72256df57b96a52737f4a0e5e90d6ba5d4e0c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692294"
---
# <a name="icordebugfunction2getjmcstatus-method"></a>Метод ICorDebugFunction2::GetJMCStatus

Возвращает значение, указывающее, помечается ли функция, представленная этим объектом ICorDebugFunction2, как пользовательский код.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetJMCStatus (  
    [out] BOOL   *pbIsJustMyCode  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pbIsJustMyCode`  
 заполняет Указатель на логическое значение, равное `true` , если эта функция помечена как пользовательский код; в противном случае — значение `false` .  
  
## <a name="remarks"></a>Remarks  

 Если функция, представленная этим объектом `ICorDebugFunction2` , не может быть отлажена, `pbIsJustMyCode` всегда будет иметь значение `false` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
