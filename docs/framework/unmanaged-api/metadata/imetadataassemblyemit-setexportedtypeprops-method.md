---
title: Метод IMetaDataAssemblyEmit::SetExportedTypeProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetExportedTypeProps
helpviewer_keywords:
- SetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 1c090153-fd5f-46c7-9cff-39a78d992c8f
topic_type:
- apiref
ms.openlocfilehash: fa4f1f57cb8fe1ca81bbad6438a88bb43c48e7bf
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008083"
---
# <a name="imetadataassemblyemitsetexportedtypeprops-method"></a>Метод IMetaDataAssemblyEmit::SetExportedTypeProps
Изменяет указанную структуру метаданных `ExportedType`.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetExportedTypeProps (  
    [in] mdExportedType   ct,
    [in] mdToken          tkImplementation,  
    [in] mdTypeDef        tkTypeDef,  
    [in] DWORD            dwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ct`  
 окне Токен метаданных, указывающий `ExportedType` структуру метаданных, которую необходимо изменить.  
  
 `tkImplementation`  
 окне Токен типа `File` , `AssemblyRef` или, `ExportedType` который указывает, как этот тип реализуется.  
  
 `tkTypeDef`  
 окне `TypeDef`Токен, на который ссылается файл кода.  
  
 `dwExportedTypeFlags`  
 окне Побитовое сочетание значений, определяющих атрибуты типа.  
  
## <a name="remarks"></a>Примечания  
 Чтобы создать `ExportedType` структуру метаданных, используйте метод [IMetaDataAssemblyEmit::D ефиникспортедтипе](imetadataassemblyemit-defineexportedtype-method.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Интерфейс IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md)
