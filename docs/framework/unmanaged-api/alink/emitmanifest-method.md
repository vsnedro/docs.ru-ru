---
description: Дополнительные сведения о методе Емитманифест
title: Метод EmitManifest
ms.date: 03/30/2017
api_name:
- EmitManifest
- IALink.EmitManifest
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitManifest
helpviewer_keywords:
- EmitManifest method
ms.assetid: fdebc1f3-b62e-4d9e-b775-8ccaa8ecb250
topic_type:
- apiref
ms.openlocfilehash: 770631864c030c067feb0b02d2f00c36076aa44c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638279"
---
# <a name="emitmanifest-method"></a>Метод EmitManifest

Выдает окончательный манифест. Вызовите этот метод после импорта всех остальных файлов и настройки всех параметров. Не вызывайте этот метод для непривязанных модулей.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EmitManifest(  
    mdAssembly   AssemblyID,  
    DWORD*       pdwReserveSize,  
    mdAssembly*  ptkManifest  
) PURE;  
```  
  
## <a name="parameters"></a>Параметры  

 `AssemblyID`  
 Идентификатор сборки.  
  
 `pdwReserveSize`  
 Получает размер для резервирования в файле сборки, полученный из [функции StrongNameSignatureSize](../strong-naming/strongnamesignaturesize-function.md).  
  
 `ptkManifest`  
 При необходимости получает маркер манифеста сборки.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Возвращает S_OK, если метод завершается с ошибкой.  
  
## <a name="requirements"></a>Требования  

 Требуется ALink. h.  
  
## <a name="see-also"></a>См. также

- [Интерфейс IALink](ialink-interface.md)
- [Интерфейс IALink2](ialink2-interface.md)
- [API ALink](index.md)
