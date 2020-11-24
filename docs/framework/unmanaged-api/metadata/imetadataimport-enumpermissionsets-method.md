---
title: Метод IMetaDataImport::EnumPermissionSets
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumPermissionSets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumPermissionSets
helpviewer_keywords:
- EnumPermissionSets method [.NET Framework metadata]
- IMetaDataImport::EnumPermissionSets method [.NET Framework metadata]
ms.assetid: 347d7e5c-c90f-45ad-bd1e-2c7912b0b19c
topic_type:
- apiref
ms.openlocfilehash: eef2c733f96d74e3353a940cc90f1a631cf48a36
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690529"
---
# <a name="imetadataimportenumpermissionsets-method"></a>Метод IMetaDataImport::EnumPermissionSets

Перечисляет разрешения для объектов в указанной области метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumPermissionSets  
   [in, out] HCORENUM      *phEnum,
   [in]      mdToken       tk,
   [in]      DWORD         dwActions,  
   [out]     mdPermission  rPermission[],  
   [in]      ULONG         cMax,  
   [out]     ULONG         *pcTokens  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `phEnum`  
 [вход, выход] Указатель на перечислитель. При первом вызове этого метода это значение должно быть равно NULL.  
  
 `tk`  
 окне Токен метаданных, ограничивающий область поиска, или значение NULL для поиска по самой широкой области.  
  
 `dwActions`  
 окне Флаги, представляющие <xref:System.Security.Permissions.SecurityAction> значения, которые необходимо включить в `rPermission` , или ноль, чтобы вернуть все действия.  
  
 `rPermission`  
 заполняет Массив, используемый для хранения маркеров разрешений.  
  
 `cMax`  
 [in] Максимальный размер массива `rPermission`.  
  
 `pcTokens`  
 заполняет Число маркеров разрешений, возвращаемых в `rPermission` .  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`EnumPermissionSets` успешно возвращено.|  
|`S_FALSE`|Нет токенов для перечисления. В этом случае значение `pcTokens` равно нулю.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)
