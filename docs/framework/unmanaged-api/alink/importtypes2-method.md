---
description: Дополнительные сведения о методе ImportTypes2
title: Метод ImportTypes2
ms.date: 03/30/2017
api_name:
- IALink2.ImportTypes2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes2
helpviewer_keywords:
- ImportTypes2 method
ms.assetid: 32f3ba58-9695-41e9-ba58-fd19e45ed396
topic_type:
- apiref
ms.openlocfilehash: ca0d174061608f9b4abf524c43023e867e9a9646
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662615"
---
# <a name="importtypes2-method"></a>Метод ImportTypes2

Инициирует импорт типов. Вызовите этот метод, чтобы начать импорт типов из каждой области, импортированной с помощью [метода ImportFile](importfile-method.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ImportTypes2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport2** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
## <a name="parameters"></a>Параметры  

 `AssemblyID`  
 Идентификатор сборки, в которую необходимо выполнить импорт.  
  
 `FileToken`  
 Идентификатор файла для импорта.  
  
 `dwScope`  
 Отсчитываемая от нуля область, из которой производится импорт.  
  
 `phEnum`  
 Получает обработчик перечислителя для типов в заданной области.  
  
 `ppImportScope`  
 При необходимости получает интерфейс интерфейса [IMetaDataImport2](../metadata/imetadataimport2-interface.md) .  
  
 `pdwCountOfTypes`  
 При необходимости получает число типов в указанной области.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Возвращает S_OK, если метод завершается с ошибкой.  
  
## <a name="requirements"></a>Требования  

 Требуется ALink. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс IALink2](ialink2-interface.md)
- [Интерфейс IALink](ialink-interface.md)
- [API ALink](index.md)
