---
title: Метод ICorProfilerInfo::GetClassFromObject
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassFromObject
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassFromObject
helpviewer_keywords:
- GetClassFromObject method [.NET Framework profiling]
- ICorProfilerInfo::GetClassFromObject method [.NET Framework profiling]
ms.assetid: b97493fb-713e-49d5-a73e-5688b2ad0700
topic_type:
- apiref
ms.openlocfilehash: 5a7edc6045969861679d1b80c0563e99f48932cf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680253"
---
# <a name="icorprofilerinfogetclassfromobject-method"></a>Метод ICorProfilerInfo::GetClassFromObject

Возвращает `ClassID` объект объекта, учитывая его свойство `ObjectID` .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetClassFromObject(  
    [in]  ObjectID objectId,  
    [out] ClassID *pClassId);  
```  
  
## <a name="parameters"></a>Параметры  

 `objectId`  
 окне Идентификатор объекта, для которого необходимо получить объект `ClassID` .  
  
 `pClassId`  
 заполняет Указатель на возвращаемый объект `ClassID` .  
  
## <a name="remarks"></a>Комментарии  

 Значение NULL `pClassId` указывает, что `objectId` имеет тип, который выгружается.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
