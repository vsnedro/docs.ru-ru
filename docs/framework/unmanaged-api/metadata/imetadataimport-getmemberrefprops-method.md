---
description: 'Дополнительные сведения: метод IMetaDataImport:: GetMemberRefProps'
title: Метод IMetaDataImport::GetMemberRefProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMemberRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMemberRefProps
helpviewer_keywords:
- GetMemberRefProps method [.NET Framework metadata]
- IMetaDataImport::GetMemberRefProps method [.NET Framework metadata]
ms.assetid: 0ea73055-ece0-4151-a094-414c88ef8941
topic_type:
- apiref
ms.openlocfilehash: b441f39d95c9af1e18d34a1a4d86d6cea33508c9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99783886"
---
# <a name="imetadataimportgetmemberrefprops-method"></a>Метод IMetaDataImport::GetMemberRefProps

Возвращает метаданные, связанные с членом, на который ссылается указанный токен.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetMemberRefProps (  
   [in]  mdMemberRef       mr,
   [out] mdToken           *ptk,
   [out] LPWSTR            szMember,
   [in]  ULONG             cchMember,
   [out] ULONG             *pchMember,
   [out] PCCOR_SIGNATURE   *ppvSigBlob,
   [out] ULONG             *pbSig
);  
```  
  
## <a name="parameters"></a>Параметры  

 `mr`  
 окне Токен MemberRef, для которого возвращаются связанные метаданные.  
  
 `ptk`  
 заполняет TypeDef или TypeRef, или TypeSpec-токен, представляющий класс, объявляющий член, или токен ModuleRef, представляющий класс Module, объявляющий элемент, или MethodDef, представляющий элемент.  
  
 `szMember`  
 заполняет Строковый буфер для имени члена.  
  
 `cchMember`  
 окне Запрошенный размер в расширенных символах `szMember` .  
  
 `pchMember`  
 заполняет Возвращаемый размер в расширенных символах `szMember` .  
  
 `ppvSibBlob`  
 заполняет Указатель на сигнатуру двоичных метаданных для элемента.  
  
 `pbSig`  
 заполняет Размер в байтах для `ppvSigBlob` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)
