---
description: 'Дополнительные сведения: метод IMetaDataImport:: EnumCustomAttributes'
title: Метод IMetaDataImport::EnumCustomAttributes
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumCustomAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method [.NET Framework metadata]
- IMetaDataImport::EnumCustomAttributes method [.NET Framework metadata]
ms.assetid: 798513a0-68b1-4d04-bc5b-782a4445ea68
topic_type:
- apiref
ms.openlocfilehash: 1c55ea4b72483e5dc30425172b95be7f77e8a62a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99677591"
---
# <a name="imetadataimportenumcustomattributes-method"></a>Метод IMetaDataImport::EnumCustomAttributes

Перечисляет токены определения пользовательских атрибутов, связанные с указанным типом или членом.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumCustomAttributes (
   [in, out] HCORENUM      *phEnum,  
   [in]  mdToken            tk,
   [in]  mdToken            tkType,
   [out] mdCustomAttribute  rCustomAttributes[],
   [in]  ULONG              cMax,  
   [out, optional] ULONG   *pcCustomAttributes  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `phEnum`  
 [вход, выход] Указатель на возвращаемый перечислитель.  
  
 `tk`  
 окне Токен для области перечисления или ноль для всех настраиваемых атрибутов.  
  
 `tkType`  
 окне Токен для конструктора типа атрибутов для перечисления или `null` для всех типов.  
  
 `rCustomAttributes`  
 заполняет Массив токенов настраиваемых атрибутов.  
  
 `cMax`  
 [in] Максимальный размер массива `rCustomAttributes`.  
  
 `pcCustomAttributes`  
 [out, необязательно] Фактическое число значений токена, возвращаемых в `rCustomAttributes` .  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`EnumCustomAttributes` успешно возвращено.|  
|`S_FALSE`|Нет настраиваемых атрибутов для перечисления. В этом случае значение `pcCustomAttributes` равно нулю.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)
