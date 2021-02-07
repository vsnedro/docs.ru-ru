---
description: 'Дополнительные сведения: метод IMetaDataImport:: Енуммемберрефс'
title: Метод IMetaDataImport::EnumMemberRefs
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMemberRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMemberRefs
helpviewer_keywords:
- EnumMemberRefs method [.NET Framework metadata]
- IMetaDataImport::EnumMemberRefs method [.NET Framework metadata]
ms.assetid: e97c97a6-6e4f-41f5-9af1-9b3cf3bdbd6b
topic_type:
- apiref
ms.openlocfilehash: 0c9b10342f73ae5b604ac25b6ff8ccec58deb5ab
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99670948"
---
# <a name="imetadataimportenummemberrefs-method"></a>Метод IMetaDataImport::EnumMemberRefs

Перечисляет токены MemberRef, представляющие члены указанного типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumMemberRefs (  
   [in, out] HCORENUM    *phEnum,
   [in]   mdToken        tkParent,
   [out]  mdMemberRef    rMemberRefs[],
   [in]   ULONG          cMax,
   [out]  ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `phEnum`  
 [вход, выход] Указатель на перечислитель.  
  
 `tkParent`  
 окне Токен TypeDef, TypeRef, MethodDef или ModuleRef для типа, элементы которого необходимо перечислить.  
  
 `rMemberRefs`  
 заполняет Массив, используемый для хранения токенов MemberRef.  
  
 `cMax`  
 [in] Максимальный размер массива `rMemberRefs`.  
  
 `pcTokens`  
 заполняет Фактическое число токенов MemberRef, возвращаемых в `rMemberRefs` .  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`EnumMemberRefs` успешно возвращено.|  
|`S_FALSE`|Отсутствуют токены MemberRef для перечисления. В этом случае значение `pcTokens` равно нулю.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)
