---
description: Дополнительные сведения о методе Експортнестедтипефорвардер
title: Метод ExportNestedTypeForwarder
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedTypeForwarder
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedTypeForwarder
helpviewer_keywords:
- ExportNestedTypeForwarder method
ms.assetid: 886ea6c5-6b26-4b88-8bf6-448d6d191950
topic_type:
- apiref
ms.openlocfilehash: fd791e3fea76338f191fcf924d56720d257d2e8b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638110"
---
# <a name="exportnestedtypeforwarder-method"></a>Метод ExportNestedTypeForwarder

Добавляет сервер пересылки типа для вложенного типа в таблицу типов данной сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ExportNestedTypeForwarder(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    mdExportedType  ParentType,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a>Параметры  

 `AssemblyID`  
 Идентификатор сборки, из которой необходимо выполнить экспорт.  
  
 `FileToken`  
 Маркер файла или идентификатор сборки файла, который определяет тип.  
  
 `TypeToken`  
 Токен для типа.  
  
 `ParentType`  
 Токен родительского типа.  
  
 `pszTypename`  
 Полное имя типа для экспорта.  
  
 `dwFlags`  
 `ComType` Флаги, такие как `tdPublic` или `tdNested` .  
  
 `pType`  
 Получает маркер типа экспорта. Это необходимо только для выпуска вложенных типов.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Возвращает S_OK, если метод завершается с ошибкой.  
  
## <a name="requirements"></a>Требования  

 Требуется ALink. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс IALink](ialink-interface.md)
- [Интерфейс IALink2](ialink2-interface.md)
- [API ALink](index.md)
