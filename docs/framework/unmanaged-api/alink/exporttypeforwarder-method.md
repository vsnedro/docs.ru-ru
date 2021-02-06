---
description: Дополнительные сведения о методе ExportTypeForwarder
title: Метод ExportTypeForwarder
ms.date: 03/30/2017
api_name:
- IALink.ExportTypeForwarder
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportTypeForwarder
helpviewer_keywords:
- ExportTypeForwarder method
ms.assetid: 55989fa9-ab43-4f08-8eb6-2eb56fa7ca76
topic_type:
- apiref
ms.openlocfilehash: 59fb74c83f6d30dda87d908353795fb218190022
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637993"
---
# <a name="exporttypeforwarder-method"></a>Метод ExportTypeForwarder

Добавляет сервер пересылки типа в таблицу типов данной сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ExportTypeForwarder(  
    mdAssemblyRef   tkAssemblyRef,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a>Параметры  

 `tkAssemblyRef`  
 Ссылка на сборку, к которой относится перенаправитель типа.  
  
 `pszTypename`  
 Полное имя типа для экспорта.  
  
 `dwFlags`  
 `ComType` Флаги, такие как `tdPublic` или `tdNested` . Это значение может быть передано [методу дефиникспортедтипе](../metadata/imetadataassemblyemit-defineexportedtype-method.md).  
  
 `pType`  
 Получает токен экспортируемого типа. Это необходимо только для выпуска вложенных типов.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Возвращает S_OK, если метод завершается с ошибкой.  
  
## <a name="requirements"></a>Требования  

 Требуется ALink. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс IALink](ialink-interface.md)
- [Интерфейс IALink2](ialink2-interface.md)
- [API ALink](index.md)
