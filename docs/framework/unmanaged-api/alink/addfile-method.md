---
description: Дополнительные сведения о методе AddFile
title: Метод AddFile
ms.date: 03/30/2017
api_name:
- IALink.AddFile
- AddFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile
helpviewer_keywords:
- AddFile method
ms.assetid: 9e707abb-f905-4568-9356-12aa21d1b11c
topic_type:
- apiref
ms.openlocfilehash: 5e1253587298b2c1559c72dced43ec70dc169090
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638630"
---
# <a name="addfile-method"></a>Метод AddFile

Добавляет файлы в сборку. Также можно использовать для создания непривязанных модулей.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a>Параметры  

 `AssemblyID`  
 Уникальный идентификатор сборки, подлежащая дополну.  
  
 `pszFilename`  
 Полное имя добавляемого файла.  
  
 `dwFlags`  
 COM+ Филедеф флаги, такие как `ffContainsNoMetaData` и `ffWriteable` . `dwFlags` передается [методу дефинефиле](../metadata/imetadataassemblyemit-definefile-method.md).  
  
 `pEmitter`  
 Интерфейс [IMetaDataEmit](../metadata/imetadataemit-interface.md) , используемый для выдачи метаданных при необходимости.  
  
 `pFileToken`  
 Указатель на место, где будет храниться уникальный идентификатор добавленного файла.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Возвращает S_OK, если метод завершается с ошибкой.  
  
## <a name="requirements"></a>Требования  

 Требуется ALink. h.  
  
## <a name="see-also"></a>См. также

- [Интерфейс IALink](ialink-interface.md)
- [Интерфейс IALink2](ialink2-interface.md)
- [API ALink](index.md)
