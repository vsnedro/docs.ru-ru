---
description: 'Дополнительные сведения: метод IMetaDataImport:: EnumTypeDefs'
title: Метод IMetaDataImport::EnumTypeDefs
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeDefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeDefs
helpviewer_keywords:
- EnumTypeDefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeDefs method [.NET Framework metadata]
ms.assetid: 4e508711-da92-4381-aaf8-6803075cdaa2
topic_type:
- apiref
ms.openlocfilehash: 28bd06b70573b780b687da9de0e13e17c29bb39a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99670689"
---
# <a name="imetadataimportenumtypedefs-method"></a>Метод IMetaDataImport::EnumTypeDefs

Перечисляет токены TypeDef, представляющие все типы в текущей области.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,
   [out] ULONG      *pcTypeDefs  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `phEnum`  
 заполняет Указатель на новый перечислитель. При первом вызове этого метода это значение должно быть равно NULL.  
  
 `rTypeDefs`  
 окне Массив, используемый для хранения токенов TypeDef.  
  
 `cMax`  
 [in] Максимальный размер массива `rTypeDefs`.  
  
 `pcTypeDefs`  
 заполняет Число токенов TypeDef, возвращаемых в `rTypeDefs` .  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`EnumTypeDefs` успешно возвращено.|  
|`S_FALSE`|Нет токенов для перечисления. В этом случае значение `pcTypeDefs` равно нулю.|  
  
## <a name="remarks"></a>Remarks  

 Маркер TypeDef представляет тип, например класс или интерфейс, а также любой тип, добавленный с помощью механизма расширяемости.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)
