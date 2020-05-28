---
title: Перечисление CeeSectionRelocType
ms.date: 03/30/2017
api_name:
- CeeSectionRelocType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CeeSectionRelocType
helpviewer_keywords:
- CeeSectionRelocType enumeration [.NET Framework metadata]
ms.assetid: 124656f6-0dad-4ceb-9043-d3869ab65cde
topic_type:
- apiref
ms.openlocfilehash: 78b30f624bd71234e8f1b56600b3a23d15fdf517
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006039"
---
# <a name="ceesectionreloctype-enumeration"></a>Перечисление CeeSectionRelocType
Предоставляет значения, влияющие на тип `reloc` инструкции, выдаваемой при вызове метода [ICeeGen:: AddSectionReloc](iceegen-addsectionreloc-method.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum  {  
    srRelocAbsolute,  
    srRelocHighLow          = 3,  
    srRelocHighAdj,
    srRelocMapToken,  
    srRelocRelative,  
    srRelocFilePos,  
    srRelocCodeRelative,  
    srRelocIA64Imm64,  
    srRelocDir64,  
    srRelocIA64PcRel25,  
    srRelocIA64PcRel64,    srRelocAbsoluteTagged,    srRelocSentinel,    srNoBaseReloc       = 0x4000,  
    srRelocPtr          = 0x8000,  
    srRelocAbsolutePtr      = srRelocPtr + srRelocAbsolute,  
    srRelocHighLowPtr       = srRelocPtr + srRelocHighLow,  
    srRelocRelativePtr      = srRelocPtr + srRelocRelative,  
    srRelocIA64Imm64Ptr     = srRelocPtr + srRelocIA64Imm64,  
    srRelocDir64Ptr         = srRelocPtr + srRelocDir64  
    } CeeSectionRelocType;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`srRelocAbsolute`|Создает только относительный раздел `reloc` , отправляя в раздел. reloc ничего.|  
|`srRelocHighLow`|Создает `reloc` для расположения, размер которого определяется указателем. Он преобразуется в BASED_HIGHLOW или BASED_DIR64 в зависимости от платформы.|  
|`srRelocHighAdj`|Создает `reloc` для старших 16 бит 32-разрядного числа, где 16 нижних бит включены в следующее слово в таблице. reloc.|  
|`srRelocMapToken`|Создает перемещение карт маркеров, отправляя в раздел. reloc значение Nothing.|  
|`srRelocRelative`|Указывает, что значением является адресная привязка относительных адресов.|  
|`srRelocFilePos`|Создает только относительный раздел `reloc` , отправляя в раздел. reloc ничего. Это `reloc` относится к расположению файла в разделе, а не к виртуальному адресу раздела.|  
|`srRelocCodeRelative`|Указывает адресную привязку адреса, относительную для кода.|  
|`srRelocIA64Imm64`|Создает `reloc` для 64-разрядного адреса в инструкции ia64 `movl` .|  
|`srRelocDir64`|Создает `reloc` для 64-разрядного адреса.|  
|`srRelocIA64PcRel25`|Создание `reloc` для 25-разрядного адреса, относительного для ПК, в `br.call` инструкции IA64.|  
|`srRelocIA64PcRel64`|Создает `reloc` для 64-разрядного адреса, относительный для ПК, в `brl.call` инструкции IA64.|  
|`srRelocAbsoluteTagged`|Формирует 30-разрядный раздел относительно `reloc` значений указателей с тегами.|  
|`srRelocSentinel`|Значение Sentinel, которое помогает гарантировать, что все дополнения к этому перечислению отражаются в `reloc` массиве внутренних имен.|  
|`srNoBaseReloc`|Указывает, что не следует создавать базу `reloc` .|  
|`srRelocPtr`|Значение, указывающее, что предварительная адресная привязка содержимого памяти является указателем, а не смещением раздела.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Перечисления метаданных](metadata-enumerations.md)
- [Интерфейс ICeeGen](iceegen-interface.md)
- [Метод AddSectionReloc](iceegen-addsectionreloc-method.md)
