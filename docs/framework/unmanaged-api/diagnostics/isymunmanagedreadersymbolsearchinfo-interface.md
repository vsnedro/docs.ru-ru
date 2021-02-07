---
description: 'Дополнительные сведения о: интерфейс ISymUnmanagedReaderSymbolSearchInfo'
title: Интерфейс ISymUnmanagedReaderSymbolSearchInfo
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReaderSymbolSearchInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReaderSymbolSearchInfo
helpviewer_keywords:
- ISymUnmanagedReaderSymbolSearchInfo interface [.NET Framework debugging]
ms.assetid: fde7e21d-1169-4bed-a34d-792e69652bf9
topic_type:
- apiref
ms.openlocfilehash: f5d13027709698df735af5fceac31f7b73741440
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763570"
---
# <a name="isymunmanagedreadersymbolsearchinfo-interface"></a>Интерфейс ISymUnmanagedReaderSymbolSearchInfo

Предоставляет методы, которые получают сведения о поиске символов. Получите этот интерфейс, вызвав `QueryInterface` для объекта, который реализует интерфейс [ISymUnmanagedReader](isymunmanagedreader-interface.md) .  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetSymbolSearchInfo](isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfo-method.md)|Возвращает сведения о поиске символов.|  
|[Метод GetSymbolSearchInfoCount](isymunmanagedreadersymbolsearchinfo-getsymbolsearchinfocount-method.md)|Возвращает число сведений о поиске символов.|  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейсы хранилища символов диагностики](diagnostics-symbol-store-interfaces.md)
