---
description: 'Дополнительные сведения о: структура OSINFO'
title: Структура OSINFO
ms.date: 03/30/2017
api_name:
- OSINFO
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- OSINFO
helpviewer_keywords:
- OSINFO structure [.NET Framework metadata]
ms.assetid: fac7b480-7adb-4450-a5e9-690fed81ffae
topic_type:
- apiref
ms.openlocfilehash: 5027ef5cf4137aa1e781134b325407e1251fdd31
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799113"
---
# <a name="osinfo-structure"></a>Структура OSINFO

Содержит сведения об операционной системе для сборки или модуля.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct {  
    DWORD   dwOSPlatformId;  
    DWORD   dwOSMajorVersion;
    DWORD   dwOSMinorVersion;
} OSINFO;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`dwOSPlatformId`|Одно из значений идентификатора, определяемое функцией платформы Microsoft Windows `GetVersionEx` . Поддерживаются следующие значения.<br /><br /> -VER_PLATFORM_WIN32s или символ 0x0000, чтобы указать Microsoft Windows 3,1.<br />-VER_PLATFORM_WIN32_WINDOWS или 0x0001, чтобы указать для Windows 95, Windows 98 или операционных систем по убыванию.<br />-VER_PLATFORM_WIN32_NT или 0x0002, чтобы указать Windows NT или операционные системы в обратном порядке.|  
|`dwOSMajorVersion`|Основной номер версии операционной системы или значение NULL для указания любой версии.|  
|`dwOSMinorVersion`|Дополнительный номер версии операционной системы или значение NULL для указания любой версии.|  
  
## <a name="remarks"></a>Remarks  

 `OSINFO` основывается на `OSVERSIONINFOEX` структуре, используемой в вызовах функции платформы Microsoft Windows `GetVersionEx` . Эта структура используется структурой ASSEMBLYMETADATA для указания поддержки операционной системы.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры метаданных](metadata-structures.md)
- [Интерфейс IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md)
