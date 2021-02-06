---
description: Дополнительные сведения о методе Емитассембликустоматтрибуте
title: Метод EmitAssemblyCustomAttribute
ms.date: 03/30/2017
api_name:
- IALink.EmitAssemblyCustomAttribute
- EmitAssemblyCustomAttribute
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitAssemblyCustomAttribute
helpviewer_keywords:
- EmitAssemblyCustomAttribute method
ms.assetid: b72f5409-79af-4fa7-90a7-7630eec170f1
topic_type:
- apiref
ms.openlocfilehash: c91eb563c14b442a22db8f328287c10e5cc9a63c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638331"
---
# <a name="emitassemblycustomattribute-method"></a>Метод EmitAssemblyCustomAttribute

Вызовите метод, чтобы установить настраиваемые атрибуты уровня сборки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EmitAssemblyCustomAttribute(  
    mdAssembly   AssemblyID,  
    mdToken      FileToken,  
    mdToken      tkType,  
    void const*  pCustomValue,  
    DWORD        cbCustomValue,  
    BOOL         bSecurity,  
    BOOL         bAllowMulti  
) PURE;  
```  
  
## <a name="parameters"></a>Параметры  

 `AssemblyID`  
 Идентификатор сборки.  
  
 `FileToken`  
 Файл, который разфайлет атрибут. Может иметь значение NULL `AssemblyID` , если не указывает на непривязанный netmodule.  
  
 `tkType`  
 Тип настраиваемого атрибута.  
  
 `pCustomValue`  
 Пользовательские данные значения.  
  
 `cbCustomValue`  
 Длина данных пользовательского значения.  
  
 `bSecurity`  
 Значение TRUE, если настраиваемый атрибут связан с подписыванием сборки.  
  
 `bAllowMulti`  
 Значение TRUE, если требуется выдавать несколько атрибутов.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Возвращает S_OK, если метод завершается с ошибкой.  
  
## <a name="requirements"></a>Требования  

 Требуется ALink. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс IALink](ialink-interface.md)
- [Интерфейс IALink2](ialink2-interface.md)
- [API ALink](index.md)
