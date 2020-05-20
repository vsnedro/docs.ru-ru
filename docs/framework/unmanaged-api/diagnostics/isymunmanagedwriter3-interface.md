---
title: Интерфейс ISymUnmanagedWriter3
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter3
helpviewer_keywords:
- ISymUnmanagedWriter3 interface [.NET Framework debugging]
ms.assetid: a034c21e-e371-4360-b470-29e88288948f
topic_type:
- apiref
ms.openlocfilehash: 006045ce101884119f676e4f6324815eb21a10a4
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614660"
---
# <a name="isymunmanagedwriter3-interface"></a>Интерфейс ISymUnmanagedWriter3
Представляет средство записи символов и предоставляет методы для определения документов, точек следования, лексических областей и переменных. Этот интерфейс расширяет интерфейс [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) .  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Commit](isymunmanagedwriter3-commit-method.md)|Фиксирует изменения, записанные на данный момент в поток.|  
|[Метод OpenMethod2](isymunmanagedwriter3-openmethod2-method.md)|Открывает метод и предоставляет его фактическое смещение раздела в изображении.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>Дополнительно

- [Интерфейсы хранилища символов диагностики](diagnostics-symbol-store-interfaces.md)
- [Интерфейс ISymUnmanagedWriter](isymunmanagedwriter-interface.md)
- [Интерфейс ISymUnmanagedWriter2](isymunmanagedwriter2-interface.md)
