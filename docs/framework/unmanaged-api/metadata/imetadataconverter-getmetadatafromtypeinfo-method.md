---
title: Метод IMetaDataConverter::GetMetaDataFromTypeInfo
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetMetaDataFromTypeInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetMetaDataFromTypeInfo
helpviewer_keywords:
- GetMetaDataFromTypeInfo method [.NET Framework metadata]
- IMetaDataConverter::GetMetaDataFromTypeInfo method [.NET Framework metadata]
ms.assetid: d44484bb-23a3-49c3-9e46-69d0d9ab4f0f
topic_type:
- apiref
ms.openlocfilehash: 1f45310bc65bc8614033182a81db451b79bcf97f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714722"
---
# <a name="imetadataconvertergetmetadatafromtypeinfo-method"></a>Метод IMetaDataConverter::GetMetaDataFromTypeInfo

Возвращает указатель на экземпляр [IMetaDataImport](imetadataimport-interface.md) , представляющий сигнатуру метаданных библиотеки типов, на которую ссылается указанный `ITypeInfo` экземпляр.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetMetaDataFromTypeInfo (  
    [in]  ITypeInfo         *pITI,  
    [out] IMetaDataImport   **ppMDI  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pITI`  
 окне Указатель на `ITypeInfo` объект, который ссылается на библиотеку типов.  
  
 `ppMDI`  
 заполняет Указатель на расположение, которое получает адрес `IMetaDataImport` экземпляра, представляющий подпись метаданных.  
  
## <a name="requirements"></a>Требования  

 **Платформа:** См. раздел [требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataEmit](imetadataemit-interface.md)
- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
