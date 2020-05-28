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
ms.openlocfilehash: 7318a7ea3eb1ddb047a799e58ebdfd9ce6cd76d1
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007589"
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
  
|Член|Описание|  
|------------|-----------------|  
|`ofRead`|Указывает, что файл следует открывать только для чтения.|  
|`ofWrite`|Указывает, что файл следует открывать для записи.<br /><br /> При использовании флага `ofWrite` во время открытия файла .WINMD также следует передавать флаг `ofNoTransform`.|  
|`ofReadWriteMask`|Маска для чтения и записи.|  
|`ofCopyMemory`|Указывает, что файл следует считывать в память. Метаданным следует создавать свою собственную копию.|  
|`ofCacheImage`|Устаревшее. Этот флаг отклонен.|  
|`ofManifestMetadata`|Устаревшее. Этот флаг отклонен.|  
|`ofReadOnly`|Указывает, что файл должен быть открыт для чтения и `QueryInterface` не может быть выполнен вызов для метода [IMetaDataEmit](imetadataemit-interface.md) .|  
|`ofTakeOwnership`|Указывает, что память была выделена с помощью вызова функции [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) и будет освобождена метаданными.|  
|`ofNoTypeLib`|Устаревшее. Этот флаг отклонен.|  
|`ofNoTransform`|Указывает, что автоматические преобразования из файла .WINMD следует отключить. Другими словами, проекцию типа среды выполнения Windows на тип платформы .NET Framework следует отключить. Дополнительные сведения см. в статьях [Среда выполнения Windows и среда CLR — внутри .NET и среда выполнения Windows](https://docs.microsoft.com/archive/msdn-magazine/2012/windows-8-special-issue/windows-runtime-and-the-clr-underneath-the-hood-with-net-and-the-windows-runtime).|  
|`ofReserved1`|Зарезервировано для внутреннего использования.|  
|`ofReserved2`|Зарезервировано для внутреннего использования.|  
|`ofReserved`|Зарезервировано для внутреннего использования.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Корхдр. h  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Перечисления метаданных](metadata-enumerations.md)
