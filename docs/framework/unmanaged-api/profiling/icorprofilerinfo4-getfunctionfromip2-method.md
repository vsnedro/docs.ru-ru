---
description: 'Дополнительные сведения о методе: метод icorprofilerinfo4:: GetFunctionFromIP2'
title: Метод ICorProfilerInfo4::GetFunctionFromIP2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetFunctionFromIP2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetFunctionFromIP2
helpviewer_keywords:
- ICorProfilerInfo4::GetFunctionFromIP2 method [.NET Framework profiling]
- GetFunctionFromIP2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 46ff70f4-13e9-40a0-802a-0a40abcfc6a0
topic_type:
- apiref
ms.openlocfilehash: f6abda7c9e7d4abcc0f0b256d6a7785cea205d7a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99686808"
---
# <a name="icorprofilerinfo4getfunctionfromip2-method"></a>Метод ICorProfilerInfo4::GetFunctionFromIP2

Сопоставляет указатель инструкции управляемого кода с JIT-повторно скомпилированной версией функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetFunctionFromIP2(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId,  
    [out] ReJITID *pReJitId);  
```  
  
## <a name="parameters"></a>Параметры  

 `ip`  
 окне Указатель инструкции в управляемом коде.  
  
 `pFunctionId`  
 заполняет Идентификатор функции.  
  
 `pReJitId`  
 заполняет Удостоверение JIT-повторно скомпилированной версии функции.  
  
## <a name="remarks"></a>Remarks  

 `GetFunctionFromIP2` функция похожа на `GetFunctionFromIP` , за исключением того, что он получает JIT-перекомпилированный идентификатор вместо идентификатора функции функции, которая содержит указанный IP-адрес.  
  
> [!NOTE]
> `GetFunctionFromIP2` может запустить сборку мусора, тогда как это `GetFunctionFromIP` не будет.  Дополнительные сведения см. в разделе [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md).  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
