---
title: Метод ICorProfilerInfo2::GetStringLayout
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetStringLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetStringLayout
helpviewer_keywords:
- GetStringLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetStringLayout method [.NET Framework profiling]
ms.assetid: 43189651-a535-4803-a1d1-f1c427ace2ca
topic_type:
- apiref
ms.openlocfilehash: d141a78a953d4e0ab922535ad2363c79f2e18ecd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727046"
---
# <a name="icorprofilerinfo2getstringlayout-method"></a>Метод ICorProfilerInfo2::GetStringLayout

Получает сведения о структуре строкового объекта. Этот метод является устаревшим в .NET Framework 4 и заменяется методом [ICorProfilerInfo3:: GetStringLayout2](icorprofilerinfo3-getstringlayout2-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetStringLayout(  
    [out] ULONG *pBufferLengthOffset,  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
## <a name="parameters"></a>Параметры  

 `pBufferLengthOffset`  
 заполняет Указатель на смещение расположения относительно `ObjectID` указателя, в котором хранится длина строки. Длина хранится в виде `DWORD` .  
  
> [!NOTE]
> Этот параметр возвращает длину самой строки, а не длину буфера. Длина буфера больше недоступна.  
  
 `PStringLengthOffset`  
 заполняет Указатель на смещение расположения относительно `ObjectID` указателя, в котором хранится длина строки. Длина хранится в виде `DWORD` .  
  
 `pBufferOffset`  
 заполняет Указатель на смещение буфера относительно указателя, в `ObjectID` котором хранится строка расширенных символов.  
  
## <a name="remarks"></a>Комментарии  

 `GetStringLayout`Метод получает смещения, относящиеся к `ObjectID` указателю, для расположений, в которых хранятся следующие значения:  
  
- Длина буфера строки.  
  
- Длина самой строки.  
  
- Буфер, содержащий фактическую строку расширенных символов.  
  
 Строки могут завершаться нулем.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Интерфейс ICorProfilerInfo2](icorprofilerinfo2-interface.md)
