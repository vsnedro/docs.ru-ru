---
description: Дополнительные сведения о методе AddFile2
title: Метод AddFile2
ms.date: 03/30/2017
api_name:
- AddFile2
- IALink2.AddFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile2
helpviewer_keywords:
- AddFile2 method
ms.assetid: 03bc49bf-a89b-4fb6-a88d-97482e061195
topic_type:
- apiref
ms.openlocfilehash: d53527ecf7e8b3a99a11ea99512fbc812125de3e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638617"
---
# <a name="addfile2-method"></a>Метод AddFile2

Добавляет файлы в сборку. Также можно использовать для создания непривязанных модулей.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT AddFile2(  
    mdAssembly AssemblyID,  
    LPCWSTR pszFilename,  
    DWORD dwFlags,  
    IMetaDataEmit2* pEmitter,  
    mdFile* pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a>Параметры  

 `AssemblyID`  
 Идентификатор сборки, в которую добавляется файл.  
  
 `pszFilename`  
 Имя добавляемого файла.  
  
 `dwFlags`  
 `FileDef`Флаги com+, такие как `ffContainsNoMetaData` и `ffWriteable` . `dwFlags` передается [методу дефинефиле](../metadata/imetadataassemblyemit-definefile-method.md).  
  
 `pEmitter`  
 Интерфейс для интерфейса интерфейса [IMetaDataEmit2](../metadata/imetadataemit2-interface.md) .  
  
 `pFileToken`  
 Получает идентификатор добавляемого файла.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Возвращает S_OK, если метод завершается с ошибкой.  
  
## <a name="requirements"></a>Требования  

 Требуется ALink. h.  
  
## <a name="see-also"></a>См. также

- [Интерфейс IALink2](ialink2-interface.md)
- [Интерфейс IALink](ialink-interface.md)
- [API ALink](index.md)
