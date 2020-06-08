---
title: Метод ICorProfilerInfo2::GetContextStaticAddress
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetContextStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetContextStaticAddress
helpviewer_keywords:
- GetContextStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetContextStaticAddress method [.NET Framework profiling]
ms.assetid: 2b374116-0972-416a-8cf5-79213129be9a
topic_type:
- apiref
ms.openlocfilehash: 7550caaa7cb4d7ed77dc36ecf0ce0e0cbc541db7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84497066"
---
# <a name="icorprofilerinfo2getcontextstaticaddress-method"></a>Метод ICorProfilerInfo2::GetContextStaticAddress
Возвращает адрес для указанного статического поля контекста, которое находится в области заданного контекста.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetContextStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] ContextID contextId,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a>Параметры  
 `classId`  
 окне Идентификатор класса, содержащего запрошенное статическое поле контекста.  
  
 `fieldToken`  
 окне Токен метаданных для запрошенного статического поля контекста.  
  
 `contextId`  
 окне Идентификатор контекста, который является областью для запрошенного статического поля контекста.  
  
 `ppAddress`  
 заполняет Указатель на адрес статического поля в заданном контексте.  
  
## <a name="remarks"></a>Примечания  
 `GetContextStaticAddress`Метод может вернуть одно из следующих данных:  
  
- CORPROF_E_DATAINCOMPLETE HRESULT, если заданному статическому полю не назначен адрес в указанном контексте.  
  
- Адреса объектов, которые могут находиться в куче сборки мусора. Эти адреса могут стать недействительными после сборки мусора, поэтому после сборки мусора профилировщики не должны считать, что они являются допустимыми.  
  
 Перед завершением конструктора класса класса возвратит `GetContextStaticAddress` CORPROF_E_DATAINCOMPLETE для всех его статических полей, хотя некоторые статические поля уже могут быть инициализированы и корневыми объектами сборки мусора.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Интерфейс ICorProfilerInfo2](icorprofilerinfo2-interface.md)
