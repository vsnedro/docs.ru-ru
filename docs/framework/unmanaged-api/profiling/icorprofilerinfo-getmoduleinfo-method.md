---
title: Метод ICorProfilerInfo::GetModuleInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetModuleInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetModuleInfo
helpviewer_keywords:
- GetModuleInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetModuleInfo method [.NET Framework profiling]
ms.assetid: 5a90d16f-7929-4987-8f83-a631becf564d
topic_type:
- apiref
ms.openlocfilehash: 751f2ac44e543fed76c7031791bb57d75ed0fd48
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498106"
---
# <a name="icorprofilerinfogetmoduleinfo-method"></a>Метод ICorProfilerInfo::GetModuleInfo
Возвращает имя файла модуля и идентификатор его родительской сборки для указанного идентификатора модуля.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetModuleInfo(  
    [in]  ModuleID   moduleId,  
    [out] LPCBYTE    *ppBaseLoadAddress,  
    [in]  ULONG      cchName,  
    [out] ULONG      *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
          WCHAR      szName[] ,  
    [out] AssemblyID *pAssemblyId);  
```  
  
## <a name="parameters"></a>Параметры  
 `moduleId`  
 [in] Идентификатор модуля, для которого будут извлекаться сведения.  
  
 `ppBaseLoadAddress`  
 [out] Базовый адрес, по которому модуль был загружен.  
  
 `cchName`  
 [in] Длина буфера возврата `szName` в символах.  
  
 `pcchName`  
 [out] Указатель на общую длину возвращаемого имени файла модуля в символах.  
  
 `szName`  
 [out] Буфер расширенных символов, предоставленный вызывающим объектом. При возврате метода этот буфер содержит имя файла модуля.  
  
 `pAssemblyId`  
 [out] Указатель на идентификатор родительской сборки модуля.  
  
## <a name="remarks"></a>Примечания  
 Для динамических модулей параметр `szName` является пустой строкой, а базовый адрес равен 0 (нулю).  
  
 Несмотря на то, что `GetModuleInfo` метод может вызываться сразу после существования идентификатора модуля, идентификатор родительской сборки будет недоступен до тех пор, пока профилировщик не получит обратный вызов [ICorProfilerCallback:: модулеаттачедтоассембли](icorprofilercallback-moduleattachedtoassembly-method.md) .  
  
 После возврата метода `GetModuleInfo` необходимо убедиться, что буфер `szName` был достаточно велик, чтобы вместить в себя полное имя файла модуля. Для этого сравните значение, на которое указывает параметр `pcchName`, со значением параметра `cchName`. Если параметр `pcchName` указывает на значение, превышающее значение `cchName`, выделите буфер `szName` большего размера, обновите параметр `cchName`, задав новый, больший размер, и вызовите метод `GetModuleInfo` снова.  
  
 Кроме того, сначала можно вызвать метод `GetModuleInfo` с буфером `szName` нулевой длины для получения правильного размера буфера. Затем можно задать размер буфера равным значению, возвращенному в параметре `pcchName`, и вызвать метод `GetModuleInfo` снова.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Профилирующие интерфейсы](profiling-interfaces.md)
- [Профилирование](index.md)
- [Метод GetModuleInfo2](icorprofilerinfo3-getmoduleinfo2-method.md)
