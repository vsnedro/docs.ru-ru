---
description: 'Дополнительные сведения о методе: ICorProfilerInfo3:: GetRuntimeInformation'
title: Метод ICorProfilerInfo3::GetRuntimeInformation
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetRuntimeInformation Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetRuntimeInformation
helpviewer_keywords:
- GetRuntimeInformation method [.NET Framework profiling]
- ICorProfilerInfo3::GetRuntimeInformation method [.NET Framework profiling]
ms.assetid: 4400fb8c-0407-4791-8557-f011fd2aee51
topic_type:
- apiref
ms.openlocfilehash: f615cc54e12b6f2f6eaa7335353f2f5f6a8ecfce
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646716"
---
# <a name="icorprofilerinfo3getruntimeinformation-method"></a>Метод ICorProfilerInfo3::GetRuntimeInformation

Предоставляет сведения о версии для профилирования среды CLR.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetRuntimeInformation(  
       [out] USHORT *pClrInstanceId,  
       [out] COR_PRF_RUNTIME_TYPE *pRuntimeType,  
       [out] USHORT *pMajorVersion,  
       [out] USHORT *pMinorVersion,  
       [out] USHORT *pBuildNumber,  
       [out] USHORT *pQFEVersion,  
       [in]  ULONG  cchVersionString,  
       [out] ULONG  *pcchVersionString,  
       [out, size_is(cchVersionString), length_is(*pcchVersionString)]  
                   WCHAR  szVersionString[]);  
```  
  
## <a name="parameters"></a>Параметры  

 `pClrInstanceId`  
 заполняет Репрезентативный идентификатор выполняющегося экземпляра среды CLR в процессе. Это то же самое `ClrInstanceID` , что и отчеты о событиях запуска для трассировки событий Windows (ETW).  
  
 `pRuntimeType`  
 заполняет Тип среды выполнения. Этот параметр возвращает `COR_PRF_DESKTOP_CLR` для классической версии среды CLR или `COR_PRF_CORE_CLR` для основной версии среды CLR, используемой в Silverlight.  
  
 `pMajorVersion`  
 заполняет Основной номер версии среды CLR.  
  
 `pMinorVersion`  
 заполняет Дополнительный номер версии среды CLR.  
  
 `pBuildVersion`  
 заполняет Номер версии сборки среды CLR.  
  
 `pQFEVersion`  
 заполняет Номер версии среды CLR, связанной с обновлением программного обеспечения.  
  
 `cchVersionString`  
 окне Длина (в символах) буфера, на который `szVersionString` указывает.  
  
 `pcchVersionString`  
 заполняет Длина в символах `szVersionString` .  
  
 `szVersionString`  
 заполняет Строка версии среды CLR.  
  
## <a name="remarks"></a>Remarks  

 Вы можете передать значение NULL для любого параметра. Однако `pcchVersionString` не может иметь значение null, если `szVersionString` не равно null.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo3](icorprofilerinfo3-interface.md)
- [Профилирующие интерфейсы](profiling-interfaces.md)
- [Профилирование](index.md)
