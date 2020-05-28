---
title: Перечисление CorAttributeTargets
ms.date: 03/30/2017
api_name:
- CorAttributeTargets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorAttributeTargets
helpviewer_keywords:
- CorAttributeTargets enumeration [.NET Framework metadata]
ms.assetid: 694c0fa0-7011-41a9-9dfd-f0e16ea574b5
topic_type:
- apiref
ms.openlocfilehash: f1836f26af99f91ab1765107573f6b067edd5e95
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007927"
---
# <a name="corattributetargets-enumeration"></a>Перечисление CorAttributeTargets
Задает элементы приложения, в которых допустимо применять аргумент.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorAttributeTargets  
{  
    catAssembly            = 0x0001,  
    catModule              = 0x0002,  
    catClass               = 0x0004,  
    catStruct              = 0x0008,  
    catEnum                = 0x0010,  
    catConstructor         = 0x0020,  
    catMethod              = 0x0040,  
    catProperty            = 0x0080,  
    catField               = 0x0100,  
    catEvent               = 0x0200,  
    catInterface           = 0x0400,  
    catParameter           = 0x0800,  
    catDelegate            = 0x1000,  
    catGenericParameter    = 0x4000,  
  
    catAll                 =
        catAssembly | catModule | catClass | catStruct |
        catEnum | catConstructor | catMethod | catProperty |
        catField | catEvent | catInterface | catParameter |
        catDelegate | catGenericParameter,  
  
    catClassMembers        =
        catClass | catStruct | catEnum | catConstructor |
        catMethod | catProperty | catField | catEvent |
        catDelegate | catInterface  
  
} CorAttributeTargets;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`catAssembly`|Атрибут может быть применен к сборке.|  
|`catModule`|Атрибут может применяться к переносимому исполняемому модулю (DLL или exe).|  
|`catClass`|Атрибут может быть применен к классу.|  
|`catStruct`|Атрибут может быть применен к структуре, т.е. может являться типом значения.|  
|`catEnum`|Атрибут может быть применен к перечислению.|  
|`catConstructor`|Атрибут может быть применен к конструктору.|  
|`catMethod`|Атрибут может быть применен к методу.|  
|`catProperty`|Атрибут может быть применен к свойству.|  
|`catField`|Атрибут может быть применен к полю.|  
|`catEvent`|Атрибут может быть применен к событию.|  
|`catInterface`|Атрибут может быть применен к интерфейсу.|  
|`catParameter`|Атрибут может быть применен к параметру.|  
|`catDelegate`|Атрибут может быть применен к делегату.|  
|`catGenericParameter`|Атрибут может быть применен к универсальному параметру.|  
|`catAll`|Атрибут может быть применен к любому элементу приложения.|  
|`catClassMembers`|Атрибут может применяться к члену класса.|  
  
## <a name="remarks"></a>Примечания  
 `CorAttributeTargets`Значения перечисления можно комбинировать с помощью битовой операции OR для получения предпочтительного сочетания.  
  
 Объект `CorAttributeTargets` параллельно управляет <xref:System.AttributeTargets?displayProperty=nameWithType> перечислением.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Корхдр. h  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Перечисления метаданных](metadata-enumerations.md)
