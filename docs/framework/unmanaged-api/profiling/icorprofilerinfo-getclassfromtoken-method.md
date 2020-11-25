---
title: Метод ICorProfilerInfo::GetClassFromToken
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassFromToken
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassFromToken
helpviewer_keywords:
- ICorProfilerInfo::GetClassFromToken method [.NET Framework profiling]
- GetClassFromToken method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 0afc1197-2a5b-424f-8b82-9cb59a7e00db
topic_type:
- apiref
ms.openlocfilehash: 7d9fe7d6d5c5af32be22ba19b52e7d40033a6eb2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706753"
---
# <a name="icorprofilerinfogetclassfromtoken-method"></a>Метод ICorProfilerInfo::GetClassFromToken

Возвращает идентификатор класса по заданному маркеру метаданных. Этот метод является устаревшим в .NET Framework версии 2,0. Вместо этого используйте [ICorProfilerInfo2:: GetClassFromTokenAndTypeArgs](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetClassFromToken(  
    [in]  ModuleID  moduleId,  
    [in]  mdTypeDef typeDef,  
    [out] ClassID   *pClassId);  
```  
  
## <a name="parameters"></a>Параметры  

 `moduleID`  
 окне Идентификатор модуля, содержащего класс.  
  
 `typeDef`  
 окне `mdTypeDef` Токен метаданных, ссылающийся на класс.  
  
 `cTypeArgs`  
 заполняет Указатель на идентификатор класса.  
  
## <a name="remarks"></a>Комментарии  

 Этот метод устарел; Вместо этого используйте `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` для всех типов.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:** 1,0, 1,1  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
