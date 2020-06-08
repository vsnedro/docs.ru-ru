---
title: Метод IMetaDataImport::GetRVA
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetRVA
helpviewer_keywords:
- GetRVA method [.NET Framework metadata]
- IMetaDataImport::GetRVA method [.NET Framework metadata]
ms.assetid: ea422217-988b-4acd-b2db-c55357938275
topic_type:
- apiref
ms.openlocfilehash: 58ab9ee9381fce4d7af1910df6c8d3bb813bcf13
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490897"
---
# <a name="imetadataimportgetrva-method"></a>Метод IMetaDataImport::GetRVA
Возвращает относительный виртуальный адрес (RVA) и флаги реализации метода или поля, представленного указанным токеном.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetRVA (  
   [in]  mdToken     tk,
   [out] ULONG       *pulCodeRVA,
   [out]  DWORD      *pdwImplFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `tk`  
 окне Токен метаданных MethodDef или FieldDef, представляющий объект кода, для которого возвращается RVA. Если токен является FieldDef, поле должно быть глобальной переменной.  
  
 `pulCodeRVA`  
 заполняет Указатель на относительный виртуальный адрес объекта кода, представленного токеном.  
  
 `pdwImplFlags`  
 заполняет Указатель на флаги реализации для метода. Это значение является битовой маской из перечисления [кормесодимпл](cormethodimpl-enumeration.md) . Значение `pdwImplFlags` допустимо только в том случае `tk` , если является токеном MethodDef.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)
