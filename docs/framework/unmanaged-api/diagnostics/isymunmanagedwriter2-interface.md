---
description: 'Дополнительные сведения о: интерфейс ISymUnmanagedWriter2'
title: Интерфейс ISymUnmanagedWriter2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2
helpviewer_keywords:
- ISymUnmanagedWriter2 interface [.NET Framework debugging]
ms.assetid: 8e78faa4-cf43-44fb-a91d-94d6df692a25
topic_type:
- apiref
ms.openlocfilehash: 228bae40e12376b3b5e8ca3bbd3463ba70a6d67b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761782"
---
# <a name="isymunmanagedwriter2-interface"></a>Интерфейс ISymUnmanagedWriter2

Представляет средство записи символов и предоставляет методы для определения документов, точек следования, лексических областей и переменных. Этот интерфейс расширяет интерфейс [ISymUnmanagedWriter](isymunmanagedwriter-interface.md) .  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод DefineConstant2](isymunmanagedwriter2-defineconstant2-method.md)|Определяет имя для постоянного значения.|  
|[Метод DefineGlobalVariable2](isymunmanagedwriter2-defineglobalvariable2-method.md)|Определяет одну глобальную переменную.|  
|[Метод DefineLocalVariable2](isymunmanagedwriter2-definelocalvariable2-method.md)|Определяет одну переменную в текущей лексической области видимости.|  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейсы хранилища символов диагностики](diagnostics-symbol-store-interfaces.md)
- [Интерфейс ISymUnmanagedWriter](isymunmanagedwriter-interface.md)
- [Интерфейс ISymUnmanagedWriter3](isymunmanagedwriter3-interface.md)
