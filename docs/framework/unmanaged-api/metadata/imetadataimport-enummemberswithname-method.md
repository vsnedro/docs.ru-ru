---
description: 'Дополнительные сведения: метод IMetaDataImport:: EnumMembersWithName'
title: Метод IMetaDataImport::EnumMembersWithName
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMembersWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMembersWithName
helpviewer_keywords:
- IMetaDataImport::EnumMembersWithName method [.NET Framework metadata]
- EnumMembersWithName method [.NET Framework metadata]
ms.assetid: 7c9e9120-3104-42f0-86ce-19a025f20dcc
topic_type:
- apiref
ms.openlocfilehash: bb6d8f0769029dccaf1f52dd211c67d47bf32a73
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99670766"
---
# <a name="imetadataimportenummemberswithname-method"></a>Метод IMetaDataImport::EnumMembersWithName

Перечисляет токены MemberDef, представляющие члены указанного типа с заданным именем.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumMembersWithName (  
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   cl,
   [in]      LPCWSTR     szName,
   [out]     mdToken     rMembers[],
   [in]      ULONG       cMax,
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `phEnum`  
 [вход, выход] Указатель на перечислитель.  
  
 `cl`  
 окне Токен TypeDef, представляющий тип с элементами для перечисления.  
  
 `szName`  
 окне Имя элемента, ограничивающее область действия перечислителя.  
  
 `rMembers`  
 заполняет Массив, используемый для хранения маркеров Мембердеф.  
  
 `cMax`  
 [in] Максимальный размер массива `rMembers`.  
  
 `pcTokens`  
 заполняет Фактическое число токенов Мембердеф, возвращаемых в `rMembers` .  
  
## <a name="remarks"></a>Remarks  

 Этот метод перечисляет поля и методы, но не свойства или события. В отличие от [IMetaDataImport:: EnumMembers](imetadataimport-enummembers-method.md), `EnumMembersWithName` отменяет все маркеры полей и элементов, у которых нет указанного имени.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`EnumTypeDefs` успешно возвращено.|  
|`S_FALSE`|Нет токенов Мембердеф для перечисления. В этом случае значение `pcTokens` равно нулю.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)
