---
description: 'Дополнительные сведения: метод IMetaDataImport:: GetMethodSemantics'
title: Метод IMetaDataImport::GetMethodSemantics
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMethodSemantics
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMethodSemantics
helpviewer_keywords:
- GetMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::GetMethodSemantics method [.NET Framework metadata]
ms.assetid: 5e018eaa-d60e-4a0b-a2c5-8c36bd09d905
topic_type:
- apiref
ms.openlocfilehash: 2b17e2ffaeef3a451850ce2cc9c4861d68df3a81
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99783863"
---
# <a name="imetadataimportgetmethodsemantics-method"></a>Метод IMetaDataImport::GetMethodSemantics

Получает флаги, указывающие связь между методом, на который ссылается указанный токен MethodDef, и связанным свойством и событием, на которые ссылается указанный токен Евентпроп.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetMethodSemantics (  
   [in]  mdMethodDef   mb,  
   [in]  mdToken       tkEventProp,  
   [out] DWORD         *pdwSemanticsFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `mb`  
 окне Токен MethodDef, представляющий метод, для которого необходимо получить сведения о семантической роли.  
  
 `tkEventProp`  
 окне Токен, представляющий парное свойство и событие, для которого необходимо получить роль метода.  
  
 `pdwSemanticsFlags`  
 заполняет Указатель на соответствующие флаги семантики. Это значение является битовой маской из перечисления [кормесодсемантиксаттр](cormethodsemanticsattr-enumeration.md) .  
  
## <a name="remarks"></a>Remarks  

 Метод [IMetaDataEmit::D ефинепроперти](imetadataemit-defineproperty-method.md) задает флаги семантики метода.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)
