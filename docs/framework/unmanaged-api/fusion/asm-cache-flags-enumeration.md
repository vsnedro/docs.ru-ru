---
description: 'Дополнительные сведения: перечисление ASM_CACHE_FLAGS'
title: Перечисление ASM_CACHE_FLAGS
ms.date: 03/30/2017
api_name:
- ASM_CACHE_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASM_CACHE_FLAGS
helpviewer_keywords:
- ASM_CACHE_FLAGS enumeration [.NET Framework fusion]
ms.assetid: 82e9a7da-321b-48b8-b239-52eaffda6be8
topic_type:
- apiref
ms.openlocfilehash: 866f61d2960074495ed036e3a8e89ebceec74e87
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761438"
---
# <a name="asm_cache_flags-enumeration"></a>Перечисление ASM_CACHE_FLAGS

Указывает источник сборки, представленной [IAssemblyCacheItem](iassemblycacheitem-interface.md) в глобальном кэше сборок.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum {  
    ASM_CACHE_ZAP       = 0x01,  
    ASM_CACHE_GAC       = 0x02,  
    ASM_CACHE_DOWNLOAD  = 0x04,  
    ASM_CACHE_ROOT      = 0x08,  
    ASM_CACHE_ROOT_EX   = 0x80  
} ASM_CACHE_FLAGS;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`ASM_CACHE_ZAP`|Перечисляет кэш предварительно скомпилированных сборок с помощью Ngen.exe.|  
|`ASM_CACHE_GAC`|Перечисляет глобальный кэш сборок.|  
|`ASM_CACHE_DOWNLOAD`|Перечисляет сборки, скачанные по запросу или теневые копии.|  
|`ASM_CACHE_ROOT`|Указывает, что функция [жеткачепас](getcachepath-function.md) должна возвращать путь к глобальному кэшу сборок для общеязыковой среды выполнения (CLR) версии 2,0. Имеет смысл только в контексте вызова [жеткачепас](getcachepath-function.md).|  
|`ASM_CACHE_ROOT_EX`|Указывает, что функция [жеткачепас](getcachepath-function.md) должна возвращать путь к глобальному кэшу сборок для CLR версии 4. Имеет смысл только в контексте вызова [жеткачепас](getcachepath-function.md).|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Fusion. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Функция GetCachePath](getcachepath-function.md)
- [Интерфейс IAssemblyCacheItem](iassemblycacheitem-interface.md)
- [Перечисления Fusion](fusion-enumerations.md)
