---
title: Перечисление CorOpenFlags
ms.date: 03/30/2017
api_name:
- CorOpenFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorOpenFlags
helpviewer_keywords:
- CorOpenFlags enumeration [.NET Framework metadata]
ms.assetid: e27a83b5-2698-4996-9032-1e0fed8b91ca
topic_type:
- apiref
ms.openlocfilehash: e474cac6437413565a1ebddfa88c3e228fe59d41
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556353"
---
# <a name="coropenflags-enumeration"></a>Перечисление CorOpenFlags
Содержит значения флага, которые управляют поведением метаданных при открытии файлов манифеста.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorOpenFlags  
{  
    ofRead              =   0x00000000,  
    ofWrite             =   0x00000001,  
    ofReadWriteMask     =   0x00000001,  
    ofCopyMemory        =   0x00000002,  
    ofCacheImage        =   0x00000004,  
    ofManifestMetadata  =   0x00000008,  
    ofReadOnly          =   0x00000010,  
    ofTakeOwnership     =   0x00000020,  
    ofCacheImage        =   0x00000004,  
    ofNoTypeLib         =   0x00000080,  
    ofNoTransform       =   0x00001000,  
    ofReserved1         =   0x00000100,  
    ofReserved2         =   0x00000200,  
    ofReserved          =   0xffffff40  
} CorOpenFlags;  
```  
  
## <a name="members"></a>Участники  
  
|Участник|Описание|  
|------------|-----------------|  
|`ofRead`|Указывает, что файл следует открывать только для чтения.|  
|`ofWrite`|Указывает, что файл следует открывать для записи.<br /><br /> При использовании флага `ofWrite` во время открытия файла .WINMD также следует передавать флаг `ofNoTransform`.|  
|`ofReadWriteMask`|Маска для чтения и записи.|  
|`ofCopyMemory`|Указывает, что файл следует считывать в память. Метаданным следует создавать свою собственную копию.|  
|`ofCacheImage`|Является устаревшей. Этот флаг отклонен.|  
|`ofManifestMetadata`|Является устаревшей. Этот флаг отклонен.|  
|`ofReadOnly`|Указывает, что файл должен быть открыт для чтения и `QueryInterface` не может быть выполнен вызов для метода [IMetaDataEmit](imetadataemit-interface.md) .|  
|`ofTakeOwnership`|Указывает, что память была выделена с помощью вызова функции [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) и будет освобождена метаданными.|  
|`ofNoTypeLib`|Является устаревшей. Этот флаг отклонен.|  
|`ofNoTransform`|Указывает, что автоматические преобразования из файла .WINMD следует отключить. Другими словами, проекцию типа среды выполнения Windows на тип платформы .NET Framework следует отключить. Дополнительные сведения см. в статьях [Среда выполнения Windows и среда CLR — внутри .NET и среда выполнения Windows](/archive/msdn-magazine/2012/windows-8-special-issue/windows-runtime-and-the-clr-underneath-the-hood-with-net-and-the-windows-runtime).|  
|`ofReserved1`|Зарезервировано для внутреннего использования.|  
|`ofReserved2`|Зарезервировано для внутреннего использования.|  
|`ofReserved`|Зарезервировано для внутреннего использования.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Корхдр. h  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления метаданных](metadata-enumerations.md)
