---
title: Интерфейс ISymUnmanagedWriter4
ms.date: 03/30/2017
ms.assetid: 4af5e8c0-987d-405e-b934-8b9e70fcae6e
ms.openlocfilehash: eaf2e8e60d9812ab6a31fb3b9050cbaae0f1a9d7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609473"
---
# <a name="isymunmanagedwriter4-interface"></a>Интерфейс ISymUnmanagedWriter4
Интерфейс ISymUnmanagedWriter4.  
  
## <a name="syntax"></a>Синтаксис  
  
```idl  
[object,uuid(BC7E3F53-F458-4C23-9DBD-A189E6E96594),pointer_default(unique)]interface ISymUnmanagedWriter4 : ISymUnmanagedWriter3  
```  
  
## <a name="methods"></a>Методы  
 Этот интерфейс содержит следующие методы:  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetDebugInfoWithPadding](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-getdebuginfowithpadding-method.md)|Функция аналогична [методу GetDebugInfo](isymunmanagedwriter-getdebuginfo-method.md) , за исключением того, что строка пути дополнена нулями после завершающего нуль-символа, чтобы сделать строку фиксированным размером `MAX_PATH` . Заполнение задается только в том случае, если длина строки пути меньше `MAX_PATH` .<br /><br /> Это упрощает написание средств, которые отличаются от PE файлов.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>Дополнительно

- [Интерфейсы хранилища символов диагностики](diagnostics-symbol-store-interfaces.md)
- [Интерфейс ISymUnmanagedWriter3](isymunmanagedwriter3-interface.md)
