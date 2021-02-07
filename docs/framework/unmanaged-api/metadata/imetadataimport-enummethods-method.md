---
description: 'Дополнительные сведения: метод IMetaDataImport:: Enummethods-'
title: Метод IMetaDataImport::EnumMethods
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethods
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethods
helpviewer_keywords:
- IMetaDataImport::EnumMethods method [.NET Framework metadata]
- EnumMethods method [.NET Framework metadata]
ms.assetid: 8cc3b0c3-d97d-4f71-9e7d-ef2a92b4959a
topic_type:
- apiref
ms.openlocfilehash: 4fce3593d088a8d401335869eb49e598ac4c3fd2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99670683"
---
# <a name="imetadataimportenummethods-method"></a>Метод IMetaDataImport::EnumMethods

Перечисляет токены MethodDef, представляющие методы указанного типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumMethods (  
   [in, out] HCORENUM   *phEnum,
   [in]  mdTypeDef      cl,
   [out] mdMethodDef    rMethods[],
   [in]  ULONG          cMax,
   [out] ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `phEnum`  
 [вход, выход] Указатель на перечислитель. При первом вызове этого метода это значение должно быть равно NULL.  
  
 `cl`  
 окне Токен TypeDef, представляющий тип с методами для перечисления.  
  
 `rMethods`  
 заполняет Массив для хранения токенов MethodDef.  
  
 `cMax`  
 окне Максимальный размер `rMethods` массива MethodDef.  
  
 `pcTokens`  
 заполняет Число токенов MethodDef, возвращаемых в `rMethods` .  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`EnumMethods` успешно возвращено.|  
|`S_FALSE`|Отсутствуют токены MethodDef для перечисления. В этом случае значение `pcTokens` равно нулю.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)
