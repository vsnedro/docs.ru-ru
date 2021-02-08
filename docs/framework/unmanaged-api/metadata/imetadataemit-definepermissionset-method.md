---
description: 'Дополнительные сведения: IMetaDataEmit::D метод Ефинепермиссионсет'
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
ms.openlocfilehash: f5c3f1466217713cb3970c805079d8f65fd429c0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784084"
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
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataEmit](imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](imetadataemit2-interface.md)
