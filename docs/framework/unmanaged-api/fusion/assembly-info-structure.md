---
description: 'Дополнительные сведения: структура ASSEMBLY_INFO'
title: Структура ASSEMBLY_INFO
ms.date: 03/30/2017
api_name:
- ASSEMBLY_INFO
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASSEMBLY_INFO
helpviewer_keywords:
- ASSEMBLY_INFO structure [.NET Framework fusion]
ms.assetid: b3cbb47c-457f-4083-8895-49562ca99ab8
topic_type:
- apiref
ms.openlocfilehash: c28d9abf13769197b62705d51bbcf4f099616bbc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761291"
---
# <a name="assembly_info-structure"></a>Структура ASSEMBLY_INFO

Содержит сведения о сборке, зарегистрированной в глобальном кэше сборок.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct _ASSEMBLY_INFO {  
    ULONG           cbAssemblyInfo;  
    DWORD           dwAssemblyFlags;  
    ULARGE_INTEGER  uliAssemblySizeInKB;  
    LPWSTR          pszCurrentAssemblyPathBuf;  
    ULONG           cchBuf;  
} ASSEMBLY_INFO;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`cbAssemblyInfo`|Размер структуры в байтах. Это поле зарезервировано для будущего расширения.|  
|`dwAssemblyFlags`|Флаги, указывающие сведения об установке сборки. Поддерживаются следующие значения.<br /><br /> — Значение ASSEMBLYINFO_FLAG_INSTALLED, указывающее, что сборка установлена. Текущая версия платформа .NET Framework всегда задает `dwAssemblyFlags` это значение.<br />— Значение ASSEMBLYINFO_FLAG_PAYLOADRESIDENT, указывающее, что сборка является резидентной полезной нагрузкой. Текущая версия платформа .NET Framework никогда не задает `dwAssemblyFlags` это значение.|  
|`uliAssemblySizeInKB`|Общий размер файлов, содержащихся в сборке, в килобайтах.|  
|`pszCurrentAssemblyPathBuf`|Указатель на строковый буфер, содержащий текущий путь к файлу манифеста. Путь должен заканчиваться нулевым символом.|  
|`cchBuf`|Количество расширенных символов, включая знак завершения null, `pszCurrentAssemblyPathBuf` содержащий.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Fusion. h  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры Fusion](fusion-structures.md)
- [Глобальный кэш сборок](../../app-domains/gac.md)
