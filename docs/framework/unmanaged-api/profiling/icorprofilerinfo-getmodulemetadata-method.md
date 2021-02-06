---
description: 'Дополнительные сведения о методе ICorProfilerInfo:: Жетмодулеметадата'
title: Метод ICorProfilerInfo::GetModuleMetaData
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetModuleMetaData
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetModuleMetaData
helpviewer_keywords:
- GetModuleMetaData method [.NET Framework profiling]
- ICorProfilerInfo::GetModuleMetaData method [.NET Framework profiling]
ms.assetid: 7a439d92-348a-44dd-b60f-cad7cba56379
topic_type:
- apiref
ms.openlocfilehash: ff0fb0563b041fcb3cf63438874724c8236d6081
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647184"
---
# <a name="icorprofilerinfogetmodulemetadata-method"></a>Метод ICorProfilerInfo::GetModuleMetaData

Возвращает экземпляр интерфейса метаданных, сопоставляемый с указанным модулем.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetModuleMetaData(  
    [in]  ModuleID moduleId,  
    [in]  DWORD    dwOpenFlags,  
    [in]  REFIID   riid,  
    [out] IUnknown **ppOut);  
```  
  
## <a name="parameters"></a>Параметры  

 `moduleId`  
 окне Идентификатор модуля, с которым будет сопоставлен экземпляр интерфейса.  
  
 `dwOpenFlags`  
 окне Значение перечисления [коропенфлагс](../metadata/coropenflags-enumeration.md) , указывающее режим открытия файлов манифеста. Допустимы только `ofRead` `ofWrite` биты и `ofNoTransform` .  
  
 `riid`  
 окне Идентификатор ссылки (GUID) интерфейса метаданных, экземпляр которого будет извлечен. Список интерфейсов см. в разделе [интерфейсы метаданных](../metadata/metadata-interfaces.md) .  
  
 `ppOut`  
 заполняет Указатель на адрес экземпляра интерфейса метаданных.  
  
## <a name="remarks"></a>Remarks  

 Можно запросить открытие метаданных в режиме чтения/записи, но это приведет к более медленному выполнению метаданных программы, так как изменения метаданных не могут быть оптимизированы по мере их постановки в компилятор.  
  
 Некоторые модули (например, модули ресурсов) не имеют метаданных. В этих случаях `GetModuleMetaData` возвращает значение HRESULT, равное S_FALSE, и значение NULL в * `ppOut` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
