---
description: 'Дополнительные сведения: Метод IMetaDataEmit:: SetPermissionSetProps'
title: Метод IMetaDataEmit::SetPermissionSetProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPermissionSetProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPermissionSetProps
helpviewer_keywords:
- SetPermissionSetProps method [.NET Framework metadata]
- IMetaDataEmit::SetPermissionSetProps method [.NET Framework metadata]
ms.assetid: 8eaee971-40bf-45e2-a3d8-6e57674213b6
topic_type:
- apiref
ms.openlocfilehash: 1e2786a21a1024f32328e36878a1a2427af54f51
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99771890"
---
# <a name="imetadataemitsetpermissionsetprops-method"></a>Метод IMetaDataEmit::SetPermissionSetProps

Задает или обновляет функции сигнатуры метаданных набора разрешений, определенного при предыдущем вызове метода [IMetaDataEmit::D ефинепермиссионсет](imetadataemit-definepermissionset-method.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetPermissionSetProps (
    [in]  mdToken         tk,
    [in]  DWORD           dwAction,
    [in]  void const      *pvPermission,
    [in]  ULONG           cbPermission,
    [out] mdPermission    *ppm
);  
```  
  
## <a name="parameters"></a>Параметры  

 `tk`  
 окне Токен метаданных, представляющий объект для декорирования.  
  
 `dwAction`  
 окне Значение [кордеклсекурити](cordeclsecurity-enumeration.md) , указывающее тип используемой декларативной безопасности.  
  
 `pvPermission`  
 окне Большой двоичный объект разрешений.  
  
 `cbPermission`  
 окне Размер (в байтах) `pvPermission` .  
  
 `ppm`  
 заполняет `mdPermission` Токен метаданных, представляющий обновленные разрешения.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataEmit](imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](imetadataemit2-interface.md)
