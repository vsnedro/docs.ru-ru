---
title: Метод IMetaDataImport::GetPermissionSetProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPermissionSetProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPermissionSetProps
helpviewer_keywords:
- GetPermissionSetProps method [.NET Framework metadata]
- IMetaDataImport::GetPermissionSetProps method [.NET Framework metadata]
ms.assetid: 9855f0e4-12c0-4d3d-ab5d-d6bc52d25eae
topic_type:
- apiref
ms.openlocfilehash: 89c45c049ebadf9e1f16bef8d2626b4e2a17fb70
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729256"
---
# <a name="imetadataimportgetpermissionsetprops-method"></a>Метод IMetaDataImport::GetPermissionSetProps

Возвращает метаданные, связанные с <xref:System.Security.PermissionSet?displayProperty=nameWithType> объектом, представленным указанным маркером разрешений.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetPermissionSetProps (  
   [in]  mdPermission      pm,  
   [out] DWORD             *pdwAction,
   [out] void const        **ppvPermission,
   [out] ULONG             *pcbPermission  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pm`  
 окне Маркер метаданных разрешения, представляющий набор разрешений, для которого необходимо получить свойства метаданных.  
  
 `pdwAction`  
 заполняет Указатель на набор разрешений.  
  
 `ppvPermission`  
 заполняет Указатель на сигнатуру двоичных метаданных набора разрешений.  
  
 `pcbPermission`  
 заполняет Размер в байтах для `ppvPermission` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Security.PermissionSet>
- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)
