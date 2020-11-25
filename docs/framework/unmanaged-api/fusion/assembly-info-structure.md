---
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
ms.openlocfilehash: 520a24ced6e897d926ce68ef5973ab7083731b9d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717634"
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
|`dwAssemblyFlags`|Флаги, указывающие сведения об установке сборки. Поддерживаются следующие значения.<br /><br /> — Значение ASSEMBLYINFO_FLAG_INSTALLED, указывающее, что сборка установлена. Текущая версия .NET Framework всегда задает `dwAssemblyFlags` это значение.<br />— Значение ASSEMBLYINFO_FLAG_PAYLOADRESIDENT, указывающее, что сборка является резидентной полезной нагрузкой. Текущая версия .NET Framework никогда не задает `dwAssemblyFlags` это значение.|  
|`uliAssemblySizeInKB`|Общий размер файлов, содержащихся в сборке, в килобайтах.|  
|`pszCurrentAssemblyPathBuf`|Указатель на строковый буфер, содержащий текущий путь к файлу манифеста. Путь должен заканчиваться нулевым символом.|  
|`cchBuf`|Количество расширенных символов, включая знак завершения null, `pszCurrentAssemblyPathBuf` содержащий.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Fusion. h  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Структуры Fusion](fusion-structures.md)
- [Глобальный кэш сборок](../../app-domains/gac.md)
