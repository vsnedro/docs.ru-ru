---
description: 'Дополнительные сведения: метод IMetaDataImport:: EnumEvents'
title: Метод IMetaDataImport::EnumEvents
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumEvents
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumEvents
helpviewer_keywords:
- IMetaDataImport::EnumEvents method [.NET Framework metadata]
- EnumEvents method [.NET Framework metadata]
ms.assetid: e1efedcb-3dd7-42ae-a399-21c24728aec5
topic_type:
- apiref
ms.openlocfilehash: e944c15a19314b315e01493836ce078fccc917eb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799412"
---
# <a name="imetadataimportenumevents-method"></a>Метод IMetaDataImport::EnumEvents

Перечисляет токены определений событий для указанного токена TypeDef.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumEvents (
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   td,
   [out]     mdEvent     rEvents[],
   [in]      ULONG       cMax,  
   [out]    ULONG        *pcEvents  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `phEnum`  
 [вход, выход] Указатель на перечислитель.  
  
 `td`  
 окне Токен TypeDef, определения событий которого должны быть перечислены.  
  
 `rEvents`  
 заполняет Массив возвращаемых событий.  
  
 `cMax`  
 [in] Максимальный размер массива `rEvents`.  
  
 `pcEvents`  
 заполняет Фактическое число событий, возвращаемых в `rEvents` .  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`EnumEvents` успешно возвращено.|  
|`S_FALSE`|Нет событий для перечисления. В этом случае значение `pcEvents` равно нулю.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)
