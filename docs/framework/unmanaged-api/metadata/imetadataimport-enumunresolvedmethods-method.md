---
description: 'Дополнительные сведения: метод IMetaDataImport:: Енумунресолведмесодс'
title: Метод IMetaDataImport::EnumUnresolvedMethods
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumUnresolvedMethods
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumUnresolvedMethods
helpviewer_keywords:
- EnumUnresolvedMethods method [.NET Framework metadata]
- IMetaDataImport::EnumUnresolvedMethods method [.NET Framework metadata]
ms.assetid: eb3187d7-74cf-44b1-aeeb-7a8d2b60e3b7
topic_type:
- apiref
ms.openlocfilehash: e894ecdde91a2263783234d73fa50d890a13e413
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799334"
---
# <a name="imetadataimportenumunresolvedmethods-method"></a>Метод IMetaDataImport::EnumUnresolvedMethods

Перечисляет токены MemberDef, представляющие неразрешенные методы в текущей области метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumUnresolvedMethods (  
   [in, out] HCORENUM    *phEnum,  
   [out]     mdToken     rMethods[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `phEnum`  
 [вход, выход] Указатель на перечислитель. При первом вызове этого метода это значение должно быть равно NULL.  
  
 `rMethods`  
 заполняет Массив, используемый для хранения маркеров Мембердеф.  
  
 `cMax`  
 [in] Максимальный размер массива `rMethods`.  
  
 `pcTokens`  
 заполняет Число токенов Мембердеф, возвращаемых в `rMethods` .  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`EnumUnresolvedMethods` успешно возвращено.|  
|`S_FALSE`|Нет токенов для перечисления. В этом случае значение `pcTokens` равно нулю.|  
  
## <a name="remarks"></a>Remarks  

 Неразрешенный метод — это тот, который был объявлен, но не реализован. Метод включается в перечисление, если метод помечен `miForwardRef` , а либо `mdPinvokeImpl` либо `miRuntime` имеет значение 0. Иными словами, неразрешенный метод — это метод класса, который помечен, `miForwardRef` но не реализован в неуправляемом коде (достигается через PInvoke) и не реализуется внутри самой среды выполнения.  
  
 Перечисление исключает все методы, определенные либо в области видимости модуля (Globals), либо в интерфейсах или в абстрактных классах.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)
