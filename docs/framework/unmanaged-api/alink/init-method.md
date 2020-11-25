---
title: Метод Init
ms.date: 03/30/2017
api_name:
- IALink.Init
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- Init
helpviewer_keywords:
- Init method
ms.assetid: e48b5c64-049f-4f93-ad87-d07ae9cd5845
topic_type:
- apiref
ms.openlocfilehash: 25a1c29ab94a785304b83d5b1bcb2d7176742a68
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726022"
---
# <a name="init-method"></a>Метод Init

Подготавливает объекты, реализующие [интерфейс иалинк](ialink-interface.md) для использования.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
## <a name="parameters"></a>Параметры  

 `pDispenser`  
 Указатель [интерфейса IMetaDataDispenserEx](../metadata/imetadatadispenserex-interface.md) на распределитель метаданных.  
  
 `pErrorHandler`  
 Указатель [интерфейса IMetaDataError](../metadata/imetadataerror-interface.md) на необязательный интерфейс обработки ошибок.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Возвращает S_OK, если метод завершается с ошибкой.  
  
## <a name="requirements"></a>Требования  

 Требуется ALink. h  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IALink](ialink-interface.md)
- [Интерфейс IALink2](ialink2-interface.md)
- [API ALink](index.md)
