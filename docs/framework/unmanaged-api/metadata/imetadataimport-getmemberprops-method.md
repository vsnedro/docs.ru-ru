---
title: Метод IMetaDataImport::GetMemberProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMemberProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMemberProps
helpviewer_keywords:
- IMetaDataImport::GetMemberProps method [.NET Framework metadata]
- GetMemberProps method [.NET Framework metadata]
ms.assetid: 42790918-4142-4938-b8f4-a56979a55846
topic_type:
- apiref
ms.openlocfilehash: f01d65a339c77e6af3e768c620f17ef0190c1e58
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733228"
---
# <a name="imetadataimportgetmemberprops-method"></a>Метод IMetaDataImport::GetMemberProps

Возвращает сведения, хранящиеся в метаданных для указанного определения элемента, включая имя, двоичную подпись и относительный виртуальный адрес элемента, <xref:System.Type> на который ссылается указанный токен метаданных. Это простой вспомогательный метод: Если *МБ* является MethodDef, то вызывается **жетмесодпропс** . Если *МБ* является FieldDef, вызывается **жетфиелдпропс** . Дополнительные сведения см. в этих других методах.
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetMemberProps (  
   [in]  mdToken           mb,
   [out] mdTypeDef         *pClass,  
   [out] LPWSTR            szMember,
   [in]  ULONG             cchMember,
   [out] ULONG             *pchMember,
   [out] DWORD             *pdwAttr,  
   [out] PCCOR_SIGNATURE   *ppvSigBlob,
   [out] ULONG             *pcbSigBlob,
   [out] ULONG             *pulCodeRVA,
   [out] DWORD             *pdwImplFlags,
   [out] DWORD             *pdwCPlusTypeFlag,
   [out] UVCP_CONSTANT     *ppValue,  
   [out] ULONG             *pcchValue  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `mb`  
 окне Токен, ссылающийся на элемент, для которого необходимо получить связанные метаданные.  
  
 `pClass`  
 заполняет Указатель на маркер метаданных, представляющий класс члена.  
  
 `szMember`  
 заполняет Имя элемента.  
  
 `cchMember`  
 окне Размер в расширенных символах `szMember` буфера.  
  
 `pchMember`  
 заполняет Размер в расширенных символах возвращаемого имени.  
  
 `pdwAttr`  
 заполняет Все значения флагов, примененные к элементу.  
  
 `ppvSigBlob`  
 заполняет Указатель на сигнатуру двоичных метаданных элемента.  
  
 `pcbSigBlob`  
 заполняет Размер в байтах для `ppvSigBlob` .  
  
 `pulCodeRVA`  
 заполняет Указатель на относительный виртуальный адрес элемента.  
  
 `pdwImplFlags`  
 заполняет Любые флаги реализации метода, связанные с элементом.  
  
 `pdwCPlusTypeFlag`  
 заполняет Флаг, помечающий <xref:System.ValueType> . Это одно из `ELEMENT_TYPE_*` значений.
  
 `ppValue`  
 заполняет Константное строковое значение, возвращаемое этим элементом.  
  
 `pcchValue`  
 заполняет Размер в символах `ppValue` или нуль, если не содержит `ppValue` строку.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)
