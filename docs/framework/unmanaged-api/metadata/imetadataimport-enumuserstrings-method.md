---
description: 'Дополнительные сведения: метод IMetaDataImport:: Енумусерстрингс'
title: Метод IMetaDataImport::EnumUserStrings
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumUserStrings
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumUserStrings
helpviewer_keywords:
- IMetaDataImport::EnumUserStrings method [.NET Framework metadata]
- EnumUserStrings method [.NET Framework metadata]
ms.assetid: 2b1f1418-4be8-4cdb-b418-b3abccc527a7
topic_type:
- apiref
ms.openlocfilehash: a4ead696f3d924fef9ebfed5c4f1eb97eb13e14e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799321"
---
# <a name="imetadataimportenumuserstrings-method"></a>Метод IMetaDataImport::EnumUserStrings

Перечисляет токены String, представляющие жестко заданные строки в текущей области метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumUserStrings (  
   [in, out]  HCORENUM    *phEnum,  
   [out]  mdString        rStrings[],  
   [in]   ULONG           cMax,  
   [out]  ULONG           *pcStrings  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `phEnum`  
 [вход, выход] Указатель на перечислитель. При первом вызове этого метода это значение должно быть равно NULL.  
  
 `rStrings`  
 заполняет Массив, используемый для хранения токенов строк.  
  
 `cMax`  
 [in] Максимальный размер массива `rStrings`.  
  
 `pcStrings`  
 заполняет Число токенов строк, возвращаемых в `rStrings` .  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`EnumUserStrings` успешно возвращено.|  
|`S_FALSE`|Нет токенов для перечисления. В этом случае значение `pcStrings` равно нулю.|  
  
## <a name="remarks"></a>Remarks  

 Строковые токены создаются методом [IMetaDataEmit::D ефинеусерстринг](imetadataemit-defineuserstring-method.md) . Этот метод предназначен для использования обозревателем метаданных, а не компилятором.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)
