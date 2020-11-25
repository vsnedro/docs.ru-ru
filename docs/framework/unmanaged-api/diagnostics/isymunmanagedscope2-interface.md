---
title: Интерфейс ISymUnmanagedScope2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2
helpviewer_keywords:
- ISymUnmanagedScope2 interface [.NET Framework debugging]
ms.assetid: 2ed6a387-ba45-483e-9a1e-b0c69f67998b
topic_type:
- apiref
ms.openlocfilehash: 40c437e109eaa4352a83c5566185593cbc6b0eba
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725837"
---
# <a name="isymunmanagedscope2-interface"></a>Интерфейс ISymUnmanagedScope2

Представляет лексическую область внутри метода. Этот интерфейс расширяет интерфейс [исимунманажедскопе](isymunmanagedscope-interface.md) с помощью методов, которые получают сведения о константах, определенных в области.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetConstantCount](isymunmanagedscope2-getconstantcount-method.md)|Возвращает число констант, определенных в этой области.|  
|[Метод GetConstants](isymunmanagedscope2-getconstants-method.md)|Возвращает локальные константы, определенные в этой области.|  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы хранилища символов диагностики](diagnostics-symbol-store-interfaces.md)
- [Интерфейс ISymUnmanagedScope](isymunmanagedscope-interface.md)
