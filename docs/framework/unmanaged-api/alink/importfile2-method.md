---
title: Метод ImportFile2
ms.date: 03/30/2017
api_name:
- IALink.ImportFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFile2
helpviewer_keywords:
- ImportFile2 method
ms.assetid: 9a6be861-c260-4a35-acea-3372ea515a0f
topic_type:
- apiref
ms.openlocfilehash: d02bc53676dd5afb0222a1ea366a8f2bd1f94f62
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705232"
---
# <a name="importfile2-method"></a>Метод ImportFile2

Импортирует сборки и непривязанные модули. Этот метод похож на [Метод ImportFile](importfile-method.md), но работает даже в том случае, если импортируемый файл не существует на диске.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ImportFile2(  
    LPCWSTR         pszFilename,  
    LPCWSTR         pszTargetName,  
    IMetaDataAssemblyImport* pAssemblyScopeIn,  
    BOOL            fSmartImport,  
    mdToken*        pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD*          pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a>Параметры  

 `pszFilename`  
 Имя импортируемого файла.  
  
 `pszTargetName`  
 Необязательное имя выходного файла, которое можно использовать для переименования файла, так как он связан с сборкой.  
  
 `pAssemblyScopeIn`  
 Необязательный интерфейс интерфейса [IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) с областью действия.  
  
 `fSmartImport`  
 Если значение равно TRUE, используется ImportTypes, в противном случае импорт должен выполняться вручную.  
  
 `pImportToken`  
 Получает идентификатор для файла или сборки.  
  
 `ppAssemblyScope`  
 Получает интерфейс [интерфейса IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) . Значение NULL, если файл не является сборкой.  
  
 `pdwCountOfScopes`  
 Получает найденные файлы и/или импортированные области.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Возвращает S_OK, если метод завершается с ошибкой.  
  
## <a name="requirements"></a>Требования  

 Требуется ALink. h.  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IALink](ialink-interface.md)
- [Интерфейс IALink2](ialink2-interface.md)
- [API ALink](index.md)
