---
description: 'Дополнительные сведения о методе: IMetaDataImport2:: Жетмесодспекпропс'
title: Метод IMetaDataImport2::GetMethodSpecProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetMethodSpecProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetMethodSpecProps
helpviewer_keywords:
- GetMethodSpecProps method [.NET Framework metadata]
- IMetaDataImport2::GetMethodSpecProps method [.NET Framework metadata]
ms.assetid: 9544b711-e669-4eaf-8630-ee862e5e4489
topic_type:
- apiref
ms.openlocfilehash: 77f3f78905d1f7f44af0e9c7a75746b4e5b6e684
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688654"
---
# <a name="imetadataimport2getmethodspecprops-method"></a>Метод IMetaDataImport2::GetMethodSpecProps

Возвращает сигнатуру метаданных метода, на который ссылается указанный токен MethodSpec.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetMethodSpecProps (  
   [in]  mdMethodSpec     mi,  
   [out] mdToken          *tkParent,  
   [out] PCCOR_SIGNATURE  *ppvSigBlob,
   [out] ULONG            *pcbSigBlob  
);
```  
  
## <a name="parameters"></a>Параметры  

 `mi`  
 окне Токен MethodSpec, представляющий создание экземпляра метода.  
  
 `tkParent`  
 заполняет Указатель на токен MethodDef или Месодреф, представляющий определение метода.  
  
 `ppvSigBlob`  
 заполняет Указатель на сигнатуру двоичных метаданных метода.  
  
 `pcbSigBlob`  
 заполняет Размер (в байтах) `ppvSigBlob` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)
- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
