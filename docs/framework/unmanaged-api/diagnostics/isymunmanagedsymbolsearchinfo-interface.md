---
title: Интерфейс ISymUnmanagedSymbolSearchInfo
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo
helpviewer_keywords:
- ISymUnmanagedSymbolSearchInfo interface [.NET Framework debugging]
ms.assetid: 30817373-0a21-49c1-a0c4-8e8daeecb8db
topic_type:
- apiref
ms.openlocfilehash: 308c501e17446719067d2dc0580d698c1770bf53
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610669"
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a>Интерфейс ISymUnmanagedSymbolSearchInfo
Предоставляет методы, получающие сведения о пути поиска. Получите этот интерфейс, вызвав `QueryInterface` для объекта, который реализует интерфейс [ISymUnmanagedReader](isymunmanagedreader-interface.md) .  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetHRESULT](isymunmanagedsymbolsearchinfo-gethresult-method.md)|Возвращает значение HRESULT.|  
|[Метод GetSearchPath](isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|Возвращает путь поиска.|  
|[Метод GetSearchPathLength](isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|Возвращает длину пути поиска.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>Дополнительно

- [Интерфейсы хранилища символов диагностики](diagnostics-symbol-store-interfaces.md)
