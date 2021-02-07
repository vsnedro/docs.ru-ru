---
description: Дополнительные сведения о методе init
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
ms.openlocfilehash: 531e05a09cbecbfb67c8c004d1e4ba1deb7e59a0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662563"
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
  
## <a name="see-also"></a>См. также

- [Интерфейс IALink](ialink-interface.md)
- [Интерфейс IALink2](ialink2-interface.md)
- [API ALink](index.md)
