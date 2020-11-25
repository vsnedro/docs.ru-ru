---
title: Перечисление CorFileMapping
ms.date: 03/30/2017
api_name:
- CorFileMapping
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFileMapping
helpviewer_keywords:
- CorFileMapping enumeration [.NET Framework metadata]
ms.assetid: 3ca41592-b8da-475a-8032-a15627730003
topic_type:
- apiref
ms.openlocfilehash: 63e27a62e176a92b03c10b59a55d9da3192918f4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726121"
---
# <a name="corfilemapping-enumeration"></a>Перечисление CorFileMapping

Содержит значения, описывающие тип сопоставления файлов, возвращаемого при вызове метода [иметадатаинфо:: GetFileMapping](imetadatainfo-getfilemapping-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorFileMapping {  
  
    fmFlat                  =   0x0000,  
    fmExecutableImage       =   0x0001  
  
} CorFileMapping;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`fmFlat`|Файл сопоставляется как файл данных. То есть `SEC_IMAGE` флаг не был передан функции Microsoft Win32 `CreateFileMapping` .|  
|`fmExecutableImage`|Файл сопоставляется для выполнения с помощью `LoadLibrary` функции или `CreateFileMapping` функции с `SEC_IMAGE` флагом.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Корхдр. h  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Перечисления метаданных](metadata-enumerations.md)
- [Метод GetFileMapping](imetadatainfo-getfilemapping-method.md)
