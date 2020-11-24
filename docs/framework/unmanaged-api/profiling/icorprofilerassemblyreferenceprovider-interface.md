---
title: Интерфейс ICorProfilerAssemblyReferenceProvider
ms.date: 03/30/2017
api_name:
- ICorProfilerAssemblyReferenceProvider
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 17205116-66e1-4acc-8f01-532fb3867028
topic_type:
- apiref
ms.openlocfilehash: 2cee012be2665f5a7212600ec11e401b18160d8b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95691400"
---
# <a name="icorprofilerassemblyreferenceprovider-interface"></a>Интерфейс ICorProfilerAssemblyReferenceProvider

[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]  
  
 Позволяет профилировщику информировать среду CLR о ссылках на сборки, которые профилировщик добавит в обратный вызов [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)|Сообщает CLR о сборке, которую профилировщик планирует добавить в обратный вызов [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .|  
  
## <a name="remarks"></a>Комментарии  

 Среда CLR передает профилировщику `ICorProfilerAssemblyReferenceProvider` объект интерфейса в обратном вызове [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) . Это позволяет профилировщику информировать среду CLR о ссылках на сборки, которые профилировщик планирует добавить позднее в параметре [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md). callback. В результате повышается точность обхода замыкания ссылки на сборку среды CLR и его алгоритмов, определяющих возможность совместного доступа к сборкам.  
  
 Этот интерфейс можно использовать только в обратном вызове [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) , который передает этот объект интерфейса профилировщику.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Профилирующие интерфейсы](profiling-interfaces.md)
