---
description: 'Дополнительные сведения: метод IMetaDataImport:: Жеткустоматтрибутебинаме'
title: Метод IMetaDataImport::GetCustomAttributeByName
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetCustomAttributeByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetCustomAttributeByName
helpviewer_keywords:
- IMetaDataImport::GetCustomAttributeByName method [.NET Framework metadata]
- GetCustomAttributeByName method [.NET Framework metadata]
ms.assetid: 909aa530-2e3b-4d0a-a38a-a2750e535d7d
topic_type:
- apiref
ms.openlocfilehash: 1a9ca5f7fe13243c01c5dbcb9f49955e9ce05c26
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745493"
---
# <a name="imetadataimportgetcustomattributebyname-method"></a>Метод IMetaDataImport::GetCustomAttributeByName

Возвращает настраиваемый атрибут по его имени и владельцу.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetCustomAttributeByName (  
   [in]  mdToken          tkObj,  
   [in]  LPCWSTR          szName,  
   [out] const void       **ppData,  
   [out] ULONG            *pcbData  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `tkObj`  
 окне Токен метаданных, представляющий объект, которому принадлежит настраиваемый атрибут.  
  
 `szName`  
 окне Имя настраиваемого атрибута.  
  
 `ppData`  
 заполняет Указатель на массив данных, являющийся значением настраиваемого атрибута.  
  
 `pcbData`  
 заполняет Размер в байтах данных, возвращаемых в * `ppData` .  
  
## <a name="remarks"></a>Remarks  

 Допускается определение нескольких пользовательских атрибутов для одного и того же владельца; они даже могут иметь одно и то же имя. Однако `GetCustomAttributeByName` возвращает только один экземпляр. ( `GetCustomAttributeByName` возвращает первый обнаруженный экземпляр.) Чтобы найти все экземпляры настраиваемого атрибута, вызовите метод [IMetaDataImport:: EnumCustomAttributes](imetadataimport-enumcustomattributes-method.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)
