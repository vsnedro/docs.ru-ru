---
title: Метод IMetaDataAssemblyEmit::SetManifestResourceProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetManifestResourceProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetManifestResourceProps
helpviewer_keywords:
- SetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetManifestResourceProps method [.NET Framework metadata]
ms.assetid: ef77efd1-849c-4e51-ba92-7ee3d2bf0339
topic_type:
- apiref
ms.openlocfilehash: c46a3bc34ba7efa760e50416e9a6c39779727813
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708932"
---
# <a name="imetadataassemblyemitsetmanifestresourceprops-method"></a>Метод IMetaDataAssemblyEmit::SetManifestResourceProps

Изменяет указанную структуру метаданных `ManifestResource`.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetManifestResourceProps (  
    [in] mdManifestResource  mr,  
    [in] mdToken             tkImplementation,
    [in] DWORD               dwOffset,  
    [in] DWORD               dwResourceFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `mr`  
 окне Токен, указывающий `ManifestResource` структуру метаданных для изменения.  
  
 `tkImplementation`  
 окне Токен типа `File` или `AssemblyRef` , который сопоставляется с поставщиком ресурсов.  
  
 `dwOffset`  
 окне Смещение в начале ресурса в файле.  
  
 `dwResourceFlags`  
 окне Побитовое сочетание значений флагов, задающих атрибуты ресурса.  
  
## <a name="remarks"></a>Комментарии  

 Чтобы создать `ManifestResource` структуру метаданных, используйте метод [IMetaDataAssemblyEmit::D ефинеманифестресаурце](imetadataassemblyemit-definemanifestresource-method.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md)
