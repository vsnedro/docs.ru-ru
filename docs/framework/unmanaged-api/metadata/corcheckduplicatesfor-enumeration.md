---
description: Дополнительные сведения о перечислении Корчеккдупликатесфор
title: Перечисление CorCheckDuplicatesFor
ms.date: 03/30/2017
api_name:
- CorCheckDuplicatesFor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCheckDuplicatesFor
helpviewer_keywords:
- CorCheckDuplicatesFor enumeration [.NET Framework metadata]
ms.assetid: d8ec8d3c-70f7-4cc6-9957-68068fd8f49c
topic_type:
- apiref
ms.openlocfilehash: 5649fc6bc66dd282b64fb5064e302a9f77420cd6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678439"
---
# <a name="corcheckduplicatesfor-enumeration"></a>Перечисление CorCheckDuplicatesFor

Указывает маркеры метаданных, которые будут проверяться на наличие дубликатов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorCheckDuplicatesFor {  
  
    MDDupAll                    = 0xffffffff,  
    MDDupENC                    = MDDupAll,  
    MDNoDupChecks               = 0x00000000,  
    MDDupTypeDef                = 0x00000001,  
    MDDupInterfaceImpl          = 0x00000002,  
    MDDupMethodDef              = 0x00000004,  
    MDDupTypeRef                = 0x00000008,  
    MDDupMemberRef              = 0x00000010,  
    MDDupCustomAttribute        = 0x00000020,  
    MDDupParamDef               = 0x00000040,  
    MDDupPermission             = 0x00000080,  
    MDDupProperty               = 0x00000100,  
    MDDupEvent                  = 0x00000200,  
    MDDupFieldDef               = 0x00000400,  
    MDDupSignature              = 0x00000800,  
    MDDupModuleRef              = 0x00001000,  
    MDDupTypeSpec               = 0x00002000,  
    MDDupImplMap                = 0x00004000,  
    MDDupAssemblyRef            = 0x00008000,  
    MDDupFile                   = 0x00010000,  
    MDDupExportedType           = 0x00020000,  
    MDDupManifestResource       = 0x00040000,  
    MDDupGenericParam           = 0x00080000,  
    MDDupMethodSpec             = 0x00100000,  
    MDDupGenericParamConstraint = 0x00200000,  
  
    MDDupAssembly               = 0x10000000,  
  
    MDDupDefault =
        MDNoDupChecks | MDDupTypeRef | MDDupMemberRef |
        MDDupSignature | MDDupTypeSpec | MDDupMethodSpec  
  
} CorCheckDuplicatesFor;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`MDDupAll`|Проверьте все маркеры метаданных на наличие дубликатов.|  
|`MDDupENC`|Не используется.|  
|`MDNoDupChecks`|Не проверяйте маркеры метаданных для дубликатов.|  
|`MDDupTypeDef`|Проверьте наличие дубликатов `mdTypeDef` токенов.|  
|`MDDupInterfaceImpl`|Проверьте наличие дубликатов `mdInterfaceImpl` токенов.|  
|`MDDupMethodDef`|Проверьте наличие дубликатов `mdMethodDef` токенов.|  
|`MDDupTypeRef`|Проверьте наличие дубликатов `mdTypeRef` токенов.|  
|`MDDupMemberRef`|Проверьте наличие дубликатов `mdMemberRef` токенов.|  
|`MDDupCustomAttribute`|Проверьте наличие дубликатов `mdCustomAttribute` токенов.|  
|`MDDupParamDef`|Проверьте наличие дубликатов `mdParamDef` токенов.|  
|`MDDupPermission`|Проверьте наличие дубликатов `mdPermission` токенов.|  
|`MDDupProperty`|Проверьте наличие дубликатов `mdProperty` токенов.|  
|`MDDupEvent`|Проверьте наличие дубликатов `mdEvent` токенов.|  
|`MDDupFieldDef`|Проверьте наличие дубликатов `mdFieldDef` токенов.|  
|`MDDupSignature`|Проверьте наличие дубликатов `mdSignature` токенов.|  
|`MDDupModuleRef`|Проверьте наличие дубликатов `mdModuleRef` токенов.|  
|`MDDupTypeSpec`|Проверьте наличие дубликатов `mdTypeSpec` токенов.|  
|`MDDupImplMap`|Проверьте наличие дубликатов `mdImplMap` токенов.|  
|`MDDupAssemblyRef`|Проверьте наличие дубликатов `mdAssemblyRef` токенов.|  
|`MDDupFile`|Проверьте наличие дубликатов `mdFile` токенов.|  
|`MDDupExportedType`|Проверьте наличие дубликатов `mdExportedType` токенов.|  
|`MDDupManifestResource`|Проверьте наличие дубликатов `mdManifestResource` токенов.|  
|`MDDupGenericParam`|Проверьте наличие дубликатов `mdGenericParam` токенов.|  
|`MDDupMethodSpec`|Проверьте наличие дубликатов `mdMethodSpec` токенов.|  
|`MDDupGenericParamConstraint`|Проверьте наличие дубликатов `mdGenericParamConstraint` токенов.|  
|`MDDupAssembly`|Проверьте наличие дубликатов `mdAssembly` токенов.|  
|`MDDupDefault`|Проверьте наличие дубликатов `mdMemberRef` `mdTypeRef` `mdSignature` токенов,,, `mdTypeSpec` и `mdMethodSpec` .|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Корхдр. h  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления метаданных](metadata-enumerations.md)
