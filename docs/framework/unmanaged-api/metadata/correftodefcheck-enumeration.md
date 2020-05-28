---
title: Перечисление CorRefToDefCheck
ms.date: 03/30/2017
api_name:
- CorRefToDefCheck
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRefToDefCheck
helpviewer_keywords:
- CorRefToDefCheck enumeration [.NET Framework metadata]
ms.assetid: f9a80f1a-55af-4459-b095-8441aae16119
topic_type:
- apiref
ms.openlocfilehash: ce6f5993b9c1aeb63e121b3567ee468cea1c9318
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007524"
---
# <a name="correftodefcheck-enumeration"></a>Перечисление CorRefToDefCheck
Задает флаги для элемента управления, на который ссылаются элементы, преобразуемые в их определения для оптимизации кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorRefToDefCheck {  
    MDRefToDefDefault           = 0x00000003,  
    MDRefToDefAll               = 0xffffffff,  
    MDRefToDefNone              = 0x00000000,  
    MDTypeRefToDef              = 0x00000001,  
    MDMemberRefToDef            = 0x00000002  
} CorRefToDefCheck;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`MDRefToDefDefault`|Указывает, что ссылки на типы и ссылки на элементы должны быть преобразованы в определения. Это значение по умолчанию ( `MDTypeRefToDef` &#124; `MDMemberRefToDef` ).|  
|`MDRefToDefAll`|Указывает, что все элементы, на которые указывают ссылки, должны быть преобразованы в определения.|  
|`MDRefToDefNone`|Указывает, что не нужно преобразовывать элементы, на которые имеются ссылки, в определения.|  
|`MDTypeRefToDef`|Указывает, что только ссылки на типы должны быть преобразованы в определения типов.|  
|`MDMemberRefToDef`|Указывает, что только ссылки на элементы должны быть преобразованы в определения. То есть ссылки на элементы должны быть преобразованы в определения методов или определения полей.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Корхдр. h  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Перечисления метаданных](metadata-enumerations.md)
