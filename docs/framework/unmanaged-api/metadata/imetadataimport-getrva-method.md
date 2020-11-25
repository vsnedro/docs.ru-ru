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
ms.openlocfilehash: b4e7209c357f21a3f0de5770b483b673d5a5570b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729217"
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
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)
