---
description: 'Дополнительные сведения: метод IMetaDataImport:: GetPermissionSetProps'
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
ms.openlocfilehash: 9dc10b7bf531b6eec389334d80cf6a1cece20ee9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789194"
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
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Security.PermissionSet>
- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)
