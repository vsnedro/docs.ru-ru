---
description: Дополнительные сведения о перечислении CorTokenType
title: Перечисление CorTokenType
ms.date: 03/30/2017
api_name:
- CorTokenType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorTokenType
helpviewer_keywords:
- CorTokenType enumeration [.NET Framework metadata]
ms.assetid: 93c9a369-225f-4eff-9b78-3fbee4902cf1
topic_type:
- apiref
ms.openlocfilehash: 954bddccd8fe20be46080f8843bcf754e0cf1bbb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678410"
---
# <a name="cortokentype-enumeration"></a>Перечисление CorTokenType

Указывает тип маркера метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorTokenType {  
  
    mdtModule                       = 0x00000000,  
    mdtTypeRef                      = 0x01000000,  
    mdtTypeDef                      = 0x02000000,  
    mdtFieldDef                     = 0x04000000,  
    mdtMethodDef                    = 0x06000000,  
    mdtParamDef                     = 0x08000000,  
    mdtInterfaceImpl                = 0x09000000,  
    mdtMemberRef                    = 0x0a000000,  
    mdtCustomAttribute              = 0x0c000000,  
    mdtPermission                   = 0x0e000000,  
    mdtSignature                    = 0x11000000,  
    mdtEvent                        = 0x14000000,  
    mdtProperty                     = 0x17000000,  
    mdtModuleRef                    = 0x1a000000,  
    mdtTypeSpec                     = 0x1b000000,  
    mdtAssembly                     = 0x20000000,  
    mdtAssemblyRef                  = 0x23000000,  
    mdtFile                         = 0x26000000,  
    mdtExportedType                 = 0x27000000,  
    mdtManifestResource             = 0x28000000,  
    mdtGenericParam                 = 0x2a000000,  
    mdtMethodSpec                   = 0x2b000000,  
    mdtGenericParamConstraint       = 0x2c000000,  
    mdtString                       = 0x70000000,  
    mdtName                         = 0x71000000,  
    mdtBaseType                     = 0x72000000  
  
} CorTokenType;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`mdtModule`|`mdModule`Токен.|  
|`mdtTypeRef`|`mdTypeRef`Токен.|  
|`mdtTypeDef`|`mdTypeDef`Токен.|  
|`mdtFieldDef`|`mdFieldDef`Токен.|  
|`mdtMethodDef`|`mdMethodDef`Токен.|  
|`mdtParamDef`|`mdParamDef`Токен.|  
|`mdtInterfaceImpl`|`mdInterfaceImpl`Токен.|  
|`mdtMemberRef`|`mdMemberRef`Токен.|  
|`mdtCustomAttribute`|`mdCustomAttribute`Токен.|  
|`mdtPermission`|`mdPermission`Токен.|  
|`mdtSignature`|`mdSignature`Токен.|  
|`mdtEvent`|`mdEvent`Токен.|  
|`mdtProperty`|`mdProperty`Токен.|  
|`mdtModuleRef`|`mdModuleRef`Токен.|  
|`mdtTypeSpec`|`mdTypeSpec`Токен.|  
|`mdtAssembly`|`mdAssembly`Токен.|  
|`mdtAssemblyRef`|`mdAssemblyRef`Токен.|  
|`mdtFile`|`mdFile`Токен.|  
|`mdtExportedType`|`mdExportedType`Токен.|  
|`mdtManifestResource`|`mdManifestResource`Токен.|  
|`mdtGenericParam`|`mdGenericParam`Токен.|  
|`mdtMethodSpec`|`mdMethodSpec`Токен.|  
|`mdtGenericParamConstraint`|`mdGenericParamConstraint`Токен.|  
|`mdtString`|`mdString`Токен.|  
|`mdtName`|`mdName`Токен.|  
|`mdtBaseType`|Не используется.|  
  
## <a name="remarks"></a>Remarks  

 Каждое значение равно значению верхнего байта в соответствующем маркере метаданных.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Корхдр. h  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления метаданных](metadata-enumerations.md)
