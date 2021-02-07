---
description: 'Дополнительные сведения о: интерфейс ISymUnmanagedScope2'
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
ms.openlocfilehash: a15094da68b00dbec454b2f6a642ac333f9a34ed
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763154"
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
  
## <a name="see-also"></a>См. также

- [Интерфейсы хранилища символов диагностики](diagnostics-symbol-store-interfaces.md)
- [Интерфейс ISymUnmanagedScope](isymunmanagedscope-interface.md)
