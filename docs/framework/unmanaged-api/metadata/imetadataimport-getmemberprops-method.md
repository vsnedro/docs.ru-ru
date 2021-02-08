---
description: 'Дополнительные сведения: метод IMetaDataImport:: Жетмемберпропс'
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
ms.openlocfilehash: 073c8fae06c3df69f0b3152b109417b818637d1c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99783902"
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
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)
