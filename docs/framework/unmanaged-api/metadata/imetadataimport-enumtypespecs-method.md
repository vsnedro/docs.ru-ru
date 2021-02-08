---
description: 'Дополнительные сведения: метод IMetaDataImport:: Енумтипеспекс'
title: Метод IMetaDataImport::EnumTypeSpecs
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeSpecs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeSpecs
helpviewer_keywords:
- EnumTypeSpecs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeSpecs method [.NET Framework metadata]
ms.assetid: 75331c7b-988b-436c-9eb9-a270d37b4f06
topic_type:
- apiref
ms.openlocfilehash: 7446bbf3296ffb6cfa3a20f594b4a7da22acff5c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799347"
---
# <a name="imetadataimportenumtypespecs-method"></a>Метод IMetaDataImport::EnumTypeSpecs

Перечисляет токены TypeSpec, определенные в текущей области метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumTypeSpecs (  
   [in, out] HCORENUM    *phEnum,  
   [out] mdTypeSpec      rTypeSpecs[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTypeSpecs  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `phEnum`  
 [вход, выход] Указатель на перечислитель. При первом вызове этого метода это значение должно быть равно NULL.  
  
 `rTypeSpecs`  
 заполняет Массив, используемый для хранения токенов TypeSpec.  
  
 `cMax`  
 [in] Максимальный размер массива `rTypeSpecs`.  
  
 `pcTypeSpecs`  
 заполняет Число токенов TypeSpec, возвращаемых в `rTypeSpecs` .  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`EnumTypeSpecs` успешно возвращено.|  
|`S_FALSE`|Нет токенов для перечисления. В этом случае значение `pcTypeSpecs` равно нулю.|  
  
## <a name="remarks"></a>Remarks  

 Токены TypeSpec создаются методом [IMetaDataEmit:: жеттокенфромтипеспек](imetadataemit-gettokenfromtypespec-method.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)
