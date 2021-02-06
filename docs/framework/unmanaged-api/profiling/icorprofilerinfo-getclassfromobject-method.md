---
description: 'Дополнительные сведения о методе ICorProfilerInfo:: GetClassFromObject'
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
ms.openlocfilehash: 1c0224137c839d167263eefb17e3ae0b3ac29ef3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647821"
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
  
## <a name="remarks"></a>Remarks  

 Значение NULL `pClassId` указывает, что `objectId` имеет тип, который выгружается.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
