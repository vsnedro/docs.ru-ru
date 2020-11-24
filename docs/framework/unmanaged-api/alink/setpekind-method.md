---
title: Метод SetPEKind
ms.date: 03/30/2017
api_name:
- IALink2.SetPEKind
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetPEKind
helpviewer_keywords:
- SetPEKind method
ms.assetid: 050e77ee-3014-45c0-9e29-2ebe29347b0d
topic_type:
- apiref
ms.openlocfilehash: be8a11cbf70e2c6f19ace67648b124515c1fb3c3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680044"
---
# <a name="setpekind-method"></a>Метод SetPEKind

Определяет тип переносимого исполняемого файла, который зависит от компьютера или компьютера.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;
```  
  
## <a name="parameters"></a>Параметры  

 `AssemblyID`  
 Идентификатор сборки.  
  
 `FileToken`  
 Токен файла, для которого задается тип PE. Может иметь значение NULL `AssemblyID` , если не указывает на непривязанный netmodule.  
  
 `dwPEKind`  
 Тип PE, как указано в [перечислении CorPEKind](../metadata/corpekind-enumeration.md).  
  
 `dwMachine`  
 Архитектура целевого компьютера, как указано в заголовке NT.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Возвращает S_OK, если метод завершается с ошибкой.  
  
## <a name="requirements"></a>Требования  

 Требуется ALink. h.  
  
## <a name="see-also"></a>См. также раздел

- [Метод GetPEKind](../metadata/imetadataimport2-getpekind-method.md)
- [Интерфейс IALink2](ialink2-interface.md)
- [Интерфейс IALink](ialink-interface.md)
- [API ALink](index.md)
