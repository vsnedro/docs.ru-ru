---
title: Интерфейс ISymUnmanagedWriter4
ms.date: 03/30/2017
ms.assetid: 4af5e8c0-987d-405e-b934-8b9e70fcae6e
ms.openlocfilehash: c2b57897e4f0e8b23337302f344065d79677e0c4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725811"
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
|[Метод GetDebugInfoWithPadding](isymunmanagedwriter4-getdebuginfowithpadding-method.md)|Функция аналогична [методу GetDebugInfo](isymunmanagedwriter-getdebuginfo-method.md) , за исключением того, что строка пути дополнена нулями после завершающего нуль-символа, чтобы сделать строку фиксированным размером `MAX_PATH` . Заполнение задается только в том случае, если длина строки пути меньше `MAX_PATH` .<br /><br /> Это упрощает написание средств, которые отличаются от PE файлов.|  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы хранилища символов диагностики](diagnostics-symbol-store-interfaces.md)
- [Интерфейс ISymUnmanagedWriter3](isymunmanagedwriter3-interface.md)
