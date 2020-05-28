---
title: Метод IMetaDataDispenser::DefineScope
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.DefineScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::DefineScope
helpviewer_keywords:
- DefineScope method [.NET Framework metadata]
- IMetaDataDispenser::DefineScope method [.NET Framework metadata]
ms.assetid: af28db02-29af-45ac-aec6-8d6c6123c2ff
topic_type:
- apiref
ms.openlocfilehash: 021ef8de602d6dd928f49e69e36f8d4a61425745
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008369"
---
# <a name="imetadatadispenserdefinescope-method"></a>Метод IMetaDataDispenser::DefineScope
Создает новую область в памяти, в которой можно создавать новые метаданные.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DefineScope (  
    [in]  REFCLSID    rclsid,  
    [in]  DWORD       dwCreateFlags,  
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `rclsid`  
 окне Идентификатор CLSID версии создаваемых структур метаданных. Это значение должно быть CLSID_CorMetaDataRuntime для .NET Framework версии 2,0.  
  
 `dwCreateFlags`  
 окне Флаги, указывающие параметры. Для .NET Framework 2,0 это значение должно быть равно нулю.  
  
 `riid`  
 окне Идентификатор IID требуемого интерфейса метаданных, который должен быть возвращен; вызывающий объект будет использовать интерфейс для создания новых метаданных.  
  
 Значение `riid` должно указывать один из интерфейсов "Emit". Допустимые значения: IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit или IID_IMetaDataEmit2.  
  
 `ppIUnk`  
 заполняет Указатель на возвращаемый интерфейс.  
  
## <a name="remarks"></a>Примечания  
 `DefineScope`создает набор таблиц метаданных в памяти, создает уникальный идентификатор GUID (идентификатор версии модуля или MVID) для метаданных и создает запись в таблице Module для выдаваемой единицы компиляции.  
  
 Вы можете прикрепить атрибуты к области метаданных в целом с помощью метода [IMetaDataEmit:: сетмодулепропс](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) или [IMetaDataEmit::D ефинекустоматтрибуте](imetadataemit-definecustomattribute-method.md) , в зависимости от ситуации.  
  
## <a name="requirements"></a>Требования  
 **Платформа:** См. раздел [требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Интерфейс IMetaDataDispenser](imetadatadispenser-interface.md)
- [Интерфейс IMetaDataDispenserEx](imetadatadispenserex-interface.md)
- [Интерфейс IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md)
- [Интерфейс IMetaDataEmit](imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](imetadataemit2-interface.md)
