---
description: Дополнительные сведения о методе ImportFile
title: Метод ImportFile
ms.date: 03/30/2017
api_name:
- IALink.ImportFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFile
helpviewer_keywords:
- ImportFile method
ms.assetid: bcbe321f-b83a-4e9a-9f10-8d913e244dc9
topic_type:
- apiref
ms.openlocfilehash: 82c9c7de7cd739ee205dc3695ea651643d01ea3a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99718165"
---
# <a name="importfile-method"></a>Метод ImportFile

Импортирует сборки и непривязанные модули.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ImportFile(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a>Параметры  

 `pszFilename`  
 Полное имя импортируемого файла.  
  
 `pszTargetName`  
 Необязательное имя выходного файла, которое можно использовать для переименования файла, так как он связан с сборкой.  
  
 `fSmartImport`  
 Если значение равно TRUE, используется ImportTypes, в противном случае импорт должен выполняться вручную.  
  
 `pImportToken`  
 Указатель на маркер, где будет храниться уникальный идентификатор файла. Файл может быть сборкой или файлом.  
  
 `ppAssemblyScope`  
 Получает указатель на [интерфейс IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md). Может иметь значение NULL, если файл не является сборкой.  
  
 `pdwCountOfScopes`  
 Указатель на число импортированных файлов и (или) областей.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Возвращает S_OK, если метод завершается с ошибкой.  
  
## <a name="requirements"></a>Требования  

 Требуется ALink. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс IALink](ialink-interface.md)
- [Интерфейс IALink2](ialink2-interface.md)
- [API ALink](index.md)
