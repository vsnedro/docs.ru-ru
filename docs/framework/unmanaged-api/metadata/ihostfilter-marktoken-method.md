---
title: Метод IHostFilter::MarkToken
ms.date: 03/30/2017
api_name:
- IHostFilter.MarkToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostFilter::MarkToken
helpviewer_keywords:
- MarkToken method, IHostFilter interface [.NET Framework metadata]
- IHostFilter::MarkToken method [.NET Framework metadata]
ms.assetid: d7061343-d0a3-4fd5-b312-61974f98bd62
topic_type:
- apiref
ms.openlocfilehash: 11529ce896f265f2b200fa6e511d4b913e9147c8
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008226"
---
# <a name="ihostfiltermarktoken-method"></a>Метод IHostFilter::MarkToken
Указывает, что заданный маркер метаданных будет обработан.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT MarkToken (  
    [in]  mdToken         tk  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `tk`  
 окне Токен метаданных для обработки.  
  
## <a name="remarks"></a>Примечания  
 Как правило, требуется обработка маркера, если он находится в области действия метаданных. `MarkToken`Метод передается в обработчик метаданных с помощью метода [IMetaDataEmit:: сесандлер](imetadataemit-sethandler-method.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Интерфейсы метаданных](metadata-interfaces.md)
- [Интерфейс IHostFilter](ihostfilter-interface.md)
