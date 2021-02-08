---
description: 'Дополнительные сведения: метод IMetaDataImport:: Енумфиелдсвиснаме'
title: Метод IMetaDataImport::EnumFieldsWithName
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumFieldsWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumFieldsWithName
helpviewer_keywords:
- IMetaDataImport::EnumFieldsWithName method [.NET Framework metadata]
- EnumFieldsWithName method [.NET Framework metadata]
ms.assetid: 42145e8d-000f-4d0b-ae43-c08201190fa2
topic_type:
- apiref
ms.openlocfilehash: 88096b2b12a9571eb05d4550e6e26a348e28cfd2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799373"
---
# <a name="imetadataimportenumfieldswithname-method"></a>Метод IMetaDataImport::EnumFieldsWithName

Перечисляет токены FieldDef заданного типа с указанным именем.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumFieldsWithName (  
   [in, out] HCORENUM    *phEnum,
   [in]  mdTypeDef       cl,
   [in]  LPCWSTR         szName,
   [out] mdFieldDef      rFields[],
   [in]  ULONG           cMax,
   [out] ULONG           *pcTokens
);  
```  
  
## <a name="parameters"></a>Параметры  

 `phEnum`  
 [вход, выход] Указатель на перечислитель.  
  
 `cl`  
 окне Токен типа, поля которого необходимо перечислить.  
  
 `szName`  
 окне Имя поля, ограничивающее область перечисления.  
  
 `rFields`  
 заполняет Массив, используемый для хранения маркеров FieldDef.  
  
 `cMax`  
 [in] Максимальный размер массива `rFields`.  
  
 `pcTokens`  
 заполняет Фактическое число токенов FieldDef, возвращаемых в `rFields` .  
  
## <a name="remarks"></a>Remarks  

 В отличие от [IMetaDataImport:: EnumFields](imetadataimport-enumfields-method.md), `EnumFieldsWithName` отменяет все маркеры полей, у которых нет указанного имени.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`EnumFieldsWithName` успешно возвращено.|  
|`S_FALSE`|Нет полей для перечисления. В этом случае значение `pcTokens` равно нулю.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)
