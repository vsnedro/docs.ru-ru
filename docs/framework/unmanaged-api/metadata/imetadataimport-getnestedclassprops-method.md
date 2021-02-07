---
description: 'Дополнительные сведения: метод IMetaDataImport:: Жетнестедкласспропс'
title: Метод IMetaDataImport::GetNestedClassProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNestedClassProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNestedClassProps
helpviewer_keywords:
- GetNestedClassProps method [.NET Framework metadata]
- IMetaDataImport::GetNestedClassProps method [.NET Framework metadata]
ms.assetid: 704d19f1-bdef-4745-af8c-6476eb246fb3
topic_type:
- apiref
ms.openlocfilehash: 5fd812bf9b7725d520b14284db400bb50e82c25b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99677542"
---
# <a name="imetadataimportgetnestedclassprops-method"></a>Метод IMetaDataImport::GetNestedClassProps

Возвращает маркер TypeDef для родителя <xref:System.Type> указанного вложенного типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetNestedClassProps (  
   [in]   mdTypeDef      tdNestedClass,  
   [out]  mdTypeDef      *ptdEnclosingClass  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `tdNestedClass`  
 окне Токен TypeDef, представляющий объект, <xref:System.Type> для которого возвращается маркер родительского класса.  
  
 `ptdEnclosingClass`  
 заполняет Указатель на маркер TypeDef для <xref:System.Type> , `tdNestedClass` вложенный в.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)
