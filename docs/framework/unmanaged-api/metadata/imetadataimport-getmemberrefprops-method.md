---
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
ms.openlocfilehash: 3237b67f8f711e9ef213d6fc66f1513c534fbdeb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733208"
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
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)
