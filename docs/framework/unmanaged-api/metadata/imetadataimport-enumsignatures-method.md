---
title: Метод IMetaDataImport::EnumSignatures
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumSignatures
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumSignatures
helpviewer_keywords:
- EnumSignatures method [.NET Framework metadata]
- IMetaDataImport::EnumSignatures method [.NET Framework metadata]
ms.assetid: d0d65060-6f90-42a2-95cf-6ffb04352996
topic_type:
- apiref
ms.openlocfilehash: 652ebf1be6a58e08da27aaed5b2e84a8f2aee98a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503774"
---
# <a name="imetadataimportenumsignatures-method"></a>Метод IMetaDataImport::EnumSignatures
Перечисляет токены Signature, представляющие отдельные подписи в текущей области.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumSignatures (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdSignature  rSignatures[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcSignatures  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `phEnum`  
 [вход, выход] Указатель на перечислитель. При первом вызове этого метода это значение должно быть равно NULL.  
  
 `rSignatures`  
 заполняет Массив, используемый для хранения маркеров подписи.  
  
 `cMax`  
 [in] Максимальный размер массива `rSignatures`.  
  
 `pcSignatures`  
 заполняет Число маркеров подписи, возвращаемых в `rSignatures` .  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`EnumSignatures`успешно возвращено.|  
|`S_FALSE`|Нет токенов для перечисления. В этом случае значение `pcSignatures` равно нулю.|  
  
## <a name="remarks"></a>Примечания  
 Маркеры подписи создаются методом [IMetaDataEmit:: жеттокенфромсиг](imetadataemit-gettokenfromsig-method.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)
