---
title: Перечисление AssemblyFlags
ms.date: 03/30/2017
api_name:
- AssemblyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyFlags
helpviewer_keywords:
- AssemblyFlags enumeration [.NET Framework metadata]
ms.assetid: 40f9bd9e-16ec-447e-81b0-168c875e9866
topic_type:
- apiref
ms.openlocfilehash: 561b4d68a574a2859286fb5f2e2d950518a9d29d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732785"
---
# <a name="assemblyflags-enumeration"></a>Перечисление AssemblyFlags

Содержит значения, описывающие функции времени выполнения сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum {  
    afImplicitExportedTypes = 0x0001,  
    afImplicitResources = 0x0002,  
    afNonSideBySideAppDomain = 0x0010,  
    afNonSideBySideProcess = 0x0020,  
    afNonSideBySideMachine = 0x0030  
} AssemblyFlags;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`afImplicitExportedTypes`|Указывает, что экспортированные определения типа являются неявными в файлах, составляющих сборку. В .NET Framework версиях 1,0 и 1,1 это значение всегда считается установленным.|  
|`afImplicitResources`|Указывает, что определения ресурсов являются неявными в файлах, составляющих сборку. В .NET Framework 1,0 и 1,1 предполагается, что это значение всегда задано.|  
|`afNonSideBySideAppDomain`|Указывает, что сборка не может выполняться с другими версиями, если они выполняются в одном домене приложения.|  
|`afNonSideBySideProcess`|Указывает, что сборка не может выполняться с другими версиями, если они выполняются в одном процессе.|  
|`afNonSideBySideMachine`|Указывает, что сборка не может выполняться с другими версиями, если они выполняются на одном компьютере.|  
  
## <a name="remarks"></a>Комментарии  

 Значения между 0x0010 и 0x0070 (включительно) используются для описания возможностей параллельной совместимости сборки, на которую указывает ссылка. Если ни одно из этих значений не задано, предполагается, что сборка совместима параллельно.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MsCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Перечисления метаданных](metadata-enumerations.md)
- [Интерфейс IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md)
