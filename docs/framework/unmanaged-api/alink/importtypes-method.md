---
description: Дополнительные сведения о методе ImportTypes
title: Метод ImportTypes
ms.date: 03/30/2017
api_name:
- IALink.ImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes
helpviewer_keywords:
- ImportTypes method
ms.assetid: 351d4b4c-c939-486d-9471-51914a55f471
topic_type:
- apiref
ms.openlocfilehash: 9a30c735ca2c9ad0f945628c3de1eb1bb56efe2c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662628"
---
# <a name="importtypes-method"></a>Метод ImportTypes

Инициирует импорт типов из каждой области, импортированной с помощью [метода ImportFile](importfile-method.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ImportTypes(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
## <a name="parameters"></a>Параметры  

 `AssemblyID`  
 Идентификатор сборки, в которую необходимо выполнить импорт.  
  
 `FileToken`  
 Идентификатор файла, из которого необходимо выполнить импорт.  
  
 `dwScope`  
 Отсчитываемая от нуля область для импорта.  
  
 `phEnum`  
 Получает обработчики перечислителя для типов в этой области.  
  
 `ppImportScope`  
 При необходимости получает интерфейс [интерфейса IMetaDataImport](../metadata/imetadataimport-interface.md) .  
  
 `pdwCountOfTypes`  
 При необходимости получает число типов в указанной области.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Возвращает S_OK, если метод завершается с ошибкой.  
  
## <a name="requirements"></a>Требования  

 Требуется ALink. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс IALink](ialink-interface.md)
- [Интерфейс IALink2](ialink2-interface.md)
- [API ALink](index.md)
