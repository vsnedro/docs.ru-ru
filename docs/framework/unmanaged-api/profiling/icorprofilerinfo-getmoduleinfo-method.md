---
description: 'Дополнительные сведения о методе ICorProfilerInfo:: GetModuleInfo'
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
ms.openlocfilehash: 003f40e6637490be23e8bf87a6bac8ab76bc50e5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647199"
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
  
## <a name="remarks"></a>Remarks  

 Для динамических модулей параметр `szName` является пустой строкой, а базовый адрес равен 0 (нулю).  
  
 Несмотря на то, что `GetModuleInfo` метод может вызываться сразу после существования идентификатора модуля, идентификатор родительской сборки будет недоступен до тех пор, пока профилировщик не получит обратный вызов [ICorProfilerCallback:: модулеаттачедтоассембли](icorprofilercallback-moduleattachedtoassembly-method.md) .  
  
 После возврата метода `GetModuleInfo` необходимо убедиться, что буфер `szName` был достаточно велик, чтобы вместить в себя полное имя файла модуля. Для этого сравните значение, на которое указывает параметр `pcchName`, со значением параметра `cchName`. Если параметр `pcchName` указывает на значение, превышающее значение `cchName`, выделите буфер `szName` большего размера, обновите параметр `cchName`, задав новый, больший размер, и вызовите метод `GetModuleInfo` снова.  
  
 Кроме того, сначала можно вызвать метод `GetModuleInfo` с буфером `szName` нулевой длины для получения правильного размера буфера. Затем можно задать размер буфера равным значению, возвращенному в параметре `pcchName`, и вызвать метод `GetModuleInfo` снова.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Профилирующие интерфейсы](profiling-interfaces.md)
- [Профилирование](index.md)
- [Метод GetModuleInfo2](icorprofilerinfo3-getmoduleinfo2-method.md)
