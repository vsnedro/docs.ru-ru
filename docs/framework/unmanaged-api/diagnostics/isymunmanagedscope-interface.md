---
description: 'Дополнительные сведения о: интерфейс Исимунманажедскопе'
title: Интерфейс ISymUnmanagedScope
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope
helpviewer_keywords:
- ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 3db7a220-cfe9-4810-8ca8-a094bb8e0f5b
topic_type:
- apiref
ms.openlocfilehash: f1175656fb49ee16fd1cd676d08f6ebb76f40c6d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763271"
---
# <a name="isymunmanagedscope-interface"></a>Интерфейс ISymUnmanagedScope

Представляет лексическую область внутри метода.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetChildren](isymunmanagedscope-getchildren-method.md)|Возвращает дочерние элементы этой области.|  
|[Метод GetEndOffset](isymunmanagedscope-getendoffset-method.md)|Возвращает конечное смещение для данной области.|  
|[Метод GetLocalCount](isymunmanagedscope-getlocalcount-method.md)|Возвращает число локальных переменных, определенных в этой области.|  
|[Метод GetLocals](isymunmanagedscope-getlocals-method.md)|Возвращает локальные переменные, определенные в этой области.|  
|[Метод GetMethod](isymunmanagedscope-getmethod-method.md)|Возвращает метод, содержащий эту область.|  
|[Метод GetNamespaces](isymunmanagedscope-getnamespaces-method.md)|Возвращает пространства имен, используемые в этой области.|  
|[Метод GetParent](isymunmanagedscope-getparent-method.md)|Возвращает родительскую область этой области.|  
|[Метод GetStartOffset](isymunmanagedscope-getstartoffset-method.md)|Возвращает начальное смещение для этой области.|  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейсы хранилища символов диагностики](diagnostics-symbol-store-interfaces.md)
- [Интерфейс ISymUnmanagedScope2](isymunmanagedscope2-interface.md)
