---
title: Перечисление COR_PRF_MODULE_FLAGS
ms.date: 03/30/2017
api_name:
- COR_PRF_MODULE_FLAGS
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_MODULE_FLAGS
helpviewer_keywords:
- COR_PRF_MODULE_FLAGS enumeration [.NET Framework profiling]
ms.assetid: 7bc3a938-0df1-4739-9ff1-89cff454b704
topic_type:
- apiref
ms.openlocfilehash: 12e7faa8d9fee7698de9d9734f522d818f225c84
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500823"
---
# <a name="cor_prf_module_flags-enumeration"></a>Перечисление COR_PRF_MODULE_FLAGS
Указывает свойства модуля.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum  
{  
    COR_PRF_MODULE_DISK             = 0x00000001,  
    COR_PRF_MODULE_NGEN             = 0x00000002,  
    COR_PRF_MODULE_DYNAMIC          = 0x00000004,  
    COR_PRF_MODULE_COLLECTIBLE      = 0x00000008,  
    COR_PRF_MODULE_RESOURCE         = 0x00000010,  
    COR_PRF_MODULE_FLAT_LAYOUT      = 0x00000020,  
    COR_PRF_MODULE_WINDOWS_RUNTIME  = 0x00000040  
}   COR_PRF_MODULE_FLAGS;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|COR_PRF_MODULE_DISK|Модуль загружен с диска.|  
|COR_PRF_MODULE_NGEN|Модуль создан генератором образов в машинном кодах (Ngen. exe).|  
|COR_PRF_MODULE_DYNAMIC|Модуль был создан методами в <xref:System.Reflection.Emit?displayProperty=nameWithType> пространстве имен.|  
|COR_PRF_MODULE_COLLECTIBLE|Время существования модуля управляется сборщиком мусора.|  
|COR_PRF_MODULE_RESOURCE|Модуль не содержит метаданных и используется строго в качестве ресурса. Управляемым эквивалентом этого бита является <xref:System.Reflection.Module.IsResource%2A?displayProperty=nameWithType> метод.|  
|COR_PRF_MODULE_FLAT_LAYOUT|Структура модуля в памяти плоская, но не сопоставлена. Если в модуле установлен этот бит, профилировщики, считывающие информацию непосредственно из заголовка переносимого исполняемого файла (PE), должны быть внимательны при интерпретации относительных виртуальных адресов (RVA) в заголовке.|  
|COR_PRF_MODULE_WINDOWS_RUNTIME|Флаг типа содержимого среда выполнения Windows задается в метаданных для сборки этого модуля. Это происходит для всех модулей метаданных Windows (. winmd).|  
  
## <a name="remarks"></a>Примечания  
 Биты из COR_PRF_MODULE_FLAGS возвращаются профилировщику в `pdwModuleFlags` параметре OUTPUT метода [ICorProfilerInfo3:: GetModuleInfo2](icorprofilerinfo3-getmoduleinfo2-method.md) . Некоторые сочетания двух или более флагов возможны, но не все сочетания возможны.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления профилирования](profiling-enumerations.md)
