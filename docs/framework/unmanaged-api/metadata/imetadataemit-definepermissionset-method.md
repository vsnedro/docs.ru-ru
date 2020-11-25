---
title: Метод IMetaDataEmit::DefinePermissionSet
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefinePermissionSet
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefinePermissionSet
helpviewer_keywords:
- DefinePermissionSet method [.NET Framework metadata]
- IMetaDataEmit::DefinePermissionSet method [.NET Framework metadata]
ms.assetid: 36cffbf7-82ca-4cf9-bf60-50ab491ac2d9
topic_type:
- apiref
ms.openlocfilehash: 3698525c139ed52b59ca577c598e675b6c26eef4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719519"
---
# <a name="imetadataemitdefinepermissionset-method"></a>Метод IMetaDataEmit::DefinePermissionSet

Создает определение для набора разрешений с указанной сигнатурой метаданных и получает маркер для этого определения набора разрешений.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DefinePermissionSet (  
    [in]  mdToken        tk,
    [in]  DWORD          dwAction,
    [in]  void const     *pvPermission,
    [in]  ULONG          cbPermission,
    [out] mdPermission   *ppm
);  
```  
  
## <a name="parameters"></a>Параметры  

 `tk`  
 окне Объект для декорирования.  
  
 `dwAction`  
 окне Значение [кордеклсекурити](cordeclsecurity-enumeration.md) , указывающее тип используемой декларативной безопасности.  
  
 `pvPermission`  
 окне Большой двоичный объект разрешений.  
  
 `cbPermission`  
 окне Размер (в байтах) `pvPermission` .  
  
 `ppm`  
 заполняет Возвращаемый маркер разрешения.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataEmit](imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](imetadataemit2-interface.md)
