---
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
ms.openlocfilehash: cff6707496c7d9657796deb8bf6fa9165ff295a2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717088"
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
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IALink2](ialink2-interface.md)
- [Интерфейс IALink](ialink-interface.md)
- [API ALink](index.md)
