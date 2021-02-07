---
description: Дополнительные сведения о методе Сетассемблифиле
title: Метод SetAssemblyFile
ms.date: 03/30/2017
api_name:
- IALink.SetAssemblyFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyFile
helpviewer_keywords:
- SetAssemblyFile method
ms.assetid: 3a912787-f139-43ca-a841-8bbda3107ecf
topic_type:
- apiref
ms.openlocfilehash: 943e0600b9781aeaf45cc26e39bd8a8b33a783c2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662498"
---
# <a name="setassemblyfile-method"></a>Метод SetAssemblyFile

Присваивает имя сборки, которая должна быть построена. Не предназначен для использования при создании непривязанных модулей.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetAssemblyFile(  
    LPCWSTR pszFilename,  
    IMetaDataEmit* pEmitter,  
    AssemblyFlags afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a>Параметры  

 `pszFilename`  
 Полное имя файла манифеста.  
  
 `pEmitter`  
 Указатель на интерфейс [интерфейса IMetaDataEmit](../metadata/imetadataemit-interface.md) .  
  
 `afFlags`  
 Флаги, определенные в [перечислении AssemblyFlags](../metadata/assemblyflags-enumeration.md).  
  
 `pAssemblyID`  
 Указатель на идентификатор результирующей сборки.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Возвращает S_OK, если метод завершается с ошибкой.  
  
## <a name="requirements"></a>Требования  

 Требуется ALink. h.  
  
## <a name="see-also"></a>См. также

- [Интерфейс IALink](ialink-interface.md)
- [Интерфейс IALink2](ialink2-interface.md)
- [API ALink](index.md)
