---
description: 'Дополнительные сведения о методе: ICorProfilerInfo2:: Жетсреадстатикаддресс'
title: Метод ICorProfilerInfo2::GetThreadStaticAddress
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetThreadStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetThreadStaticAddress
helpviewer_keywords:
- GetThreadStaticAddress method [.NET Framework profiling]
- ICorProfilerInfo2::GetThreadStaticAddress method [.NET Framework profiling]
ms.assetid: 8e7dbf14-98a2-4384-a950-58a7640e59df
topic_type:
- apiref
ms.openlocfilehash: bab4190f3751967031806dccbea2fdf6add73f6e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647058"
---
# <a name="icorprofilerinfo2getthreadstaticaddress-method"></a>Метод ICorProfilerInfo2::GetThreadStaticAddress

Возвращает адрес указанного статического поля потока, который находится в области заданного потока.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetThreadStaticAddress(  
    [in] ClassID     classId,  
    [in] mdFieldDef  fieldToken,  
    [in] ThreadID    threadId,  
    [out] void       **ppAddress);  
```  
  
## <a name="parameters"></a>Параметры  

 `classId`  
 окне Идентификатор класса, содержащего запрошенное статическое поле потока.  
  
 `fieldToken`  
 окне Токен метаданных для запрошенного статического поля потока.  
  
 `threadId`  
 окне Идентификатор потока, который является областью для запрошенного статического поля.  
  
 `ppAddress`  
 заполняет Указатель на адрес статического поля, находящихся в указанном потоке.  
  
## <a name="remarks"></a>Remarks  

 `GetThreadStaticAddress`Метод может вернуть одно из следующих данных:  
  
- CORPROF_E_DATAINCOMPLETE HRESULT, если заданному статическому полю не назначен адрес в указанном контексте.  
  
- Адреса объектов, которые могут находиться в куче сборки мусора. Эти адреса могут стать недействительными после сборки мусора, поэтому после завершения профилирования сборщиком мусора не следует считать, что они являются допустимыми.  
  
 Перед завершением конструктора класса класса возвратит `GetThreadStaticAddress` CORPROF_E_DATAINCOMPLETE для всех его статических полей, хотя некоторые статические поля уже могут быть инициализированы и корневыми объектами сборки мусора.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Интерфейс ICorProfilerInfo2](icorprofilerinfo2-interface.md)
