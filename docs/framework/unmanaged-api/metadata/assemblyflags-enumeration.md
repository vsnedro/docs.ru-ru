---
description: Дополнительные сведения о перечислении AssemblyFlags
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
ms.openlocfilehash: 17cc0dec305c21d21693fe8f4f8d82c039f73278
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679008"
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
|`afImplicitExportedTypes`|Указывает, что экспортированные определения типа являются неявными в файлах, составляющих сборку. В платформа .NET Framework версиях 1,0 и 1,1 это значение всегда считается установленным.|  
|`afImplicitResources`|Указывает, что определения ресурсов являются неявными в файлах, составляющих сборку. В платформа .NET Framework 1,0 и 1,1 предполагается, что это значение всегда задано.|  
|`afNonSideBySideAppDomain`|Указывает, что сборка не может выполняться с другими версиями, если они выполняются в одном домене приложения.|  
|`afNonSideBySideProcess`|Указывает, что сборка не может выполняться с другими версиями, если они выполняются в одном процессе.|  
|`afNonSideBySideMachine`|Указывает, что сборка не может выполняться с другими версиями, если они выполняются на одном компьютере.|  
  
## <a name="remarks"></a>Remarks  

 Значения между 0x0010 и 0x0070 (включительно) используются для описания возможностей параллельной совместимости сборки, на которую указывает ссылка. Если ни одно из этих значений не задано, предполагается, что сборка совместима параллельно.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MsCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления метаданных](metadata-enumerations.md)
- [Интерфейс IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md)
