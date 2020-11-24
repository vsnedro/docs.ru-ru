---
title: Перечисление CorPEKind
ms.date: 03/30/2017
api_name:
- CorPEKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPEKind
helpviewer_keywords:
- CorPEKind enumeration [.NET Framework metadata]
ms.assetid: 22dc6dea-b1b9-4982-a730-a022d586b117
topic_type:
- apiref
ms.openlocfilehash: 001be0c5e8897bacf76d2a044fb9400768473052
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673544"
---
# <a name="corpekind-enumeration"></a>Перечисление CorPEKind

Содержит значения, описывающие переносимый исполняемый файл (PE), возвращенный при вызове [IMetaDataImport2:: GetPEKind](imetadataimport2-getpekind-method.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorPEKind {  
  
    peNot           = 0x00000000,  
    peILonly        = 0x00000001,  
    pe32BitRequired = 0x00000002,  
    pe32Plus        = 0x00000004,  
    pe32Unmanaged   = 0x00000008,  
    pe32BitPreferred= 0x00000010  
  
} CorPEKind;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`peNot`|Указывает, что этот файл не является PE-файлом.|  
|`peILOnly`|Указывает, что этот PE файл содержит только управляемый код.|  
|`pe32BitRequired`|Указывает, что этот PE файл выполняет вызовы Win32.|  
|`pe32Plus`|Указывает, что этот PE-файл выполняется на 64-разрядной платформе.|  
|`pe32Unmanaged`|Указывает, что этот PE-файл является машинным кодом.|  
|pe32BitPreferred|Указывает, что этот PE-файл является нейтральным к платформе и предпочитает загрузку в 32-разрядной среде.|  
  
## <a name="remarks"></a>Комментарии  

 Эти значения можно использовать в побитовых сочетаниях.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Корхдр. h  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Перечисления метаданных](metadata-enumerations.md)
