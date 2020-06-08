---
title: Метод ICorProfilerInfo3::GetStringLayout2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetStringLayout2 Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetStringLayout2
helpviewer_keywords:
- ICorProfilerInfo3::GetStringLayout2 method [.NET Framework profiling]
- GetStringLayout2 method [.NET Framework profiling]
ms.assetid: 1a268496-ee51-4d84-8700-ee56fd0c499d
topic_type:
- apiref
ms.openlocfilehash: 51d5b2f2ee17cc177e3b0ddc7d2e0b82fd70063d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496377"
---
# <a name="icorprofilerinfo3getstringlayout2-method"></a>Метод ICorProfilerInfo3::GetStringLayout2
Получает сведения о структуре строкового объекта. Этот метод заменяет метод [ICorProfilerInfo2:: GetStringLayout](icorprofilerinfo2-getstringlayout-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetStringLayout2(  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a>Параметры  
 `pStringLengthOffset`  
 заполняет Указатель на смещение расположения относительно `ObjectID` указателя, в котором хранится длина строки. Длина хранится в виде `DWORD` .  
  
 `pBufferOffset`  
 заполняет Указатель на смещение буфера относительно `ObjectID` указателя, в котором хранится строка расширенных символов.  
  
## <a name="remarks"></a>Примечания  
 Строки могут завершаться или не заканчиваться нулем.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerInfo3](icorprofilerinfo3-interface.md)
- [Профилирующие интерфейсы](profiling-interfaces.md)
