---
description: 'Дополнительные сведения о методе: IMetaDataAssemblyImport:: EnumAssemblyRefs'
title: Метод IMetaDataAssemblyImport::EnumAssemblyRefs
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumAssemblyRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs method [.NET Framework metadata]
- EnumAssemblyRefs method [.NET Framework metadata]
ms.assetid: 8844d0dd-730e-4592-8a7b-c1462d312c70
topic_type:
- apiref
ms.openlocfilehash: fc1d74d79edc21c6d3d13c80510440333d083801
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671065"
---
# <a name="imetadataassemblyimportenumassemblyrefs-method"></a>Метод IMetaDataAssemblyImport::EnumAssemblyRefs

Перечисляет `mdAssemblyRef` экземпляры, определенные в манифесте сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumAssemblyRefs (  
    [in, out] HCORENUM        *phEnum,
    [out]     mdAssemblyRef   rAssemblyRefs[],
    [in]      ULONG           cMax,
    [out]     ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `phEnum`  
 [вход, выход] Указатель на перечислитель. Это значение должно быть null, если `EnumAssemblyRefs` метод вызывается в первый раз.  
  
 `rAssemblyRefs`  
 заполняет Перечисление `mdAssemblyRef` токенов метаданных.  
  
 `cMax`  
 окне Максимальное число токенов, которые могут быть помещены в `rAssemblyRefs` массив.  
  
 `pcTokens`  
 заполняет Количество маркеров, которые в действительности помещаются в `rAssemblyRefs` .  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`EnumAssemblyRefs` успешно возвращено.|  
|`S_FALSE`|Нет токенов для перечисления. В этом случае `pcTokens` имеет значение 0.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataAssemblyImport](imetadataassemblyimport-interface.md)
