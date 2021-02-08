---
description: 'Дополнительные сведения: метод IMetaDataImport:: Жетмесодпропс'
title: Метод IMetaDataImport::GetMethodProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMethodProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMethodProps
helpviewer_keywords:
- GetMethodProps method [.NET Framework metadata]
- IMetaDataImport::GetMethodProps method [.NET Framework metadata]
ms.assetid: e0667ef7-1d31-4c89-a2d3-d426f023f8d2
topic_type:
- apiref
ms.openlocfilehash: 5fb344d72378a806e0e71820b55a90998e497916
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99783887"
---
# <a name="imetadataimportgetmethodprops-method"></a>Метод IMetaDataImport::GetMethodProps

Возвращает метаданные, связанные с методом, на который ссылается указанный токен MethodDef.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetMethodProps (  
    [in]  mdMethodDef         mb,  
    [out] mdTypeDef           *pClass,  
    [out] LPWSTR              szMethod,  
    [in]  ULONG               cchMethod,  
    [out] ULONG               *pchMethod,  
    [out] DWORD               *pdwAttr,  
    [out] PCCOR_SIGNATURE     *ppvSigBlob,  
    [out] ULONG               *pcbSigBlob,  
    [out] ULONG               *pulCodeRVA,  
    [out] DWORD               *pdwImplFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `mb`  
 окне Токен MethodDef, представляющий метод, для которого возвращаются метаданные.  
  
 `pClass`  
 заполняет Указатель на маркер TypeDef, представляющий тип, реализующий метод.  
  
 `szMethod`  
 заполняет Указатель на буфер с именем метода.  
  
 `cchMethod`  
 окне Запрошенный размер `szMethod` .  
  
 `pchMethod`  
 заполняет Указатель на размер в расширенных символах `szMethod` , или, в случае усечения, фактическое число расширенных символов в имени метода.  
  
 `pdwAttr`  
 заполняет Указатель на любые флаги, связанные с методом.  
  
 `ppvSigBlob`  
 заполняет Указатель на сигнатуру двоичных метаданных метода.  
  
 `pcbSigBlob`  
 заполняет Указатель на размер в байтах для `ppvSigBlob` .  
  
 `pulCodeRVA`  
 заполняет Указатель на относительный виртуальный адрес метода.  
  
 `pdwImplFlags`  
 заполняет Указатель на любые флаги реализации метода.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)
