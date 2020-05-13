---
title: Метод ICorDebugProcess::IsTransitionStub
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.IsTransitionStub
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::IsTransitionStub
helpviewer_keywords:
- ICorDebugProcess::IsTransitionStub method [.NET Framework debugging]
- IsTransitionStub method [.NET Framework debugging]
ms.assetid: f7653317-7e48-4163-be03-f50f1a4b0f70
topic_type:
- apiref
ms.openlocfilehash: ab2121605f974fdf3f9053214a4d29d8b0dd72db
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83211449"
---
# <a name="icordebugprocessistransitionstub-method"></a>Метод ICorDebugProcess::IsTransitionStub
Возвращает значение, указывающее, находится ли адрес в заглушке, что приведет к переходу в управляемый код.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT IsTransitionStub(  
    [in]  CORDB_ADDRESS address,  
    [out] BOOL *pbTransitionStub);  
```  
  
## <a name="parameters"></a>Параметры  
 `address`  
 окне `CORDB_ADDRESS`Значение, указывающее рассматриваемый адрес.  
  
 `pbTransitionStub`  
 заполняет Указатель на логическое значение, равное, `true` если указанный адрес находится внутри заглушки, которая приведет к переходу в управляемый код; в противном случае `pbTransitionStub` — * `false` .  
  
## <a name="remarks"></a>Remarks  
 `IsTransitionStub`Метод может использоваться неуправляемым кодом пошагового выполнения, чтобы решить, когда следует возвращать контроль пошагового выполнения в управляемое средство Организации.  
  
 Вы также можете идентифицировать заглушки перехода, просмотрев информацию в переносимом исполняемом файле (PE).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
