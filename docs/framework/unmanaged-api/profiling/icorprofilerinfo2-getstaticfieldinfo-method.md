---
title: Метод ICorProfilerInfo2::GetStaticFieldInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetStaticFieldInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetStaticFieldInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetStaticFieldInfo method [.NET Framework profiling]
- GetStaticFieldInfo method [.NET Framework profiling]
ms.assetid: fc663e76-e23f-49a8-bdd5-52cdf1a3b2b3
topic_type:
- apiref
ms.openlocfilehash: ff84bdfb8bbd5331fb94eed766f09137adf9e62c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703847"
---
# <a name="icorprofilerinfo2getstaticfieldinfo-method"></a>Метод ICorProfilerInfo2::GetStaticFieldInfo

Возвращает значение, указывающее тип статического объекта, который применяется к указанному полю.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetStaticFieldInfo (  
    [in] ClassID               classId,  
    [in] mdFieldDef            fieldToken,  
    [out] COR_PRF_STATIC_TYPE  *pFieldInfo);  
```  
  
## <a name="parameters"></a>Параметры  

 `classId`  
 окне Идентификатор класса, в котором определено статическое поле.  
  
 `fieldToken`  
 окне Маркер метаданных для статического поля.  
  
 `pFieldInfo`  
 заполняет Указатель на значение перечисления [COR_PRF_STATIC_TYPE](cor-prf-static-type-enumeration.md) , указывающее, является ли указанное поле статическим, и, если это так, тип статического, применяемого к полю.  
  
## <a name="remarks"></a>Комментарии  

 Эти сведения можно использовать для определения функции, вызываемой для получения адреса статического поля.  
  
 Код профилировщика должен по-прежнему проверять метаданные для статического поля, чтобы убедиться, что он действительно имеет адрес. Статические литералы (константы) существуют только в метаданных и не имеют адреса.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Интерфейс ICorProfilerInfo2](icorprofilerinfo2-interface.md)
