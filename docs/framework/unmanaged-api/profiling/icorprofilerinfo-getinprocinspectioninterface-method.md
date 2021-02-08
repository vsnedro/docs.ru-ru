---
description: 'Дополнительные сведения о методе ICorProfilerInfo:: ЖетинпроЦинспектионинтерфаце'
title: Метод ICorProfilerInfo::GetInprocInspectionInterface
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetInprocInspectionInterface
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetInprocInspectionInterface
helpviewer_keywords:
- GetInprocInspectionInterface method [.NET Framework profiling]
- ICorProfilerInfo::GetInprocInspectionInterface method [.NET Framework profiling]
ms.assetid: 22a92d1d-8849-4af6-8304-ecc53dd1d289
topic_type:
- apiref
ms.openlocfilehash: 5b7ce053f0a64afd5d702a4eb59c1712f4b26e9e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781471"
---
# <a name="icorprofilerinfogetinprocinspectioninterface-method"></a>Метод ICorProfilerInfo::GetInprocInspectionInterface

Возвращает объект, к которому можно выполнить запрос для интерфейса "ICorDebugProcess". Этот метод является устаревшим в платформа .NET Framework версии 2,0.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetInprocInspectionInterface(  
    [out] IUnknown **ppicd);  
```  
  
## <a name="parameters"></a>Параметры  

 `ppicd`  
 [выходной](/cpp/atl/iunknown) объект, к которому можно запросить `ICorDebugProcess` интерфейс.  
  
## <a name="remarks"></a>Remarks  

 API отладки среды CLR поддерживал ограниченную внутрипроцессную отладку в платформа .NET Framework версии 1,0. В процессе отладки с помощью профилировщика можно использовать части проверки для API отладки. В результате отзывов клиентов внутрипроцессный процесс отладки был удален из платформа .NET Framework в версии 2,0 и заменен набором функциональных возможностей, которые более подробно описаны в API профилирования.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версия платформа .NET Framework:** 1,0  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
