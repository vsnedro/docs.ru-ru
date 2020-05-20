---
title: Интерфейс ISymENCUnmanagedMethod
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod
helpviewer_keywords:
- ISymENCUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: faebf594-67d5-4abf-b9c1-547fd3a1ff87
topic_type:
- apiref
ms.openlocfilehash: 54c8c7f5c3ba6b4afd4ff352a8afb947a92e2d61
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441881"
---
# <a name="isymencunmanagedmethod-interface"></a>Интерфейс ISymENCUnmanagedMethod
Предоставляет сведения для функции "изменить и продолжить".  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetDocumentsForMethod](isymencunmanagedmethod-getdocumentsformethod-method.md)|Возвращает документы, в которых у этого метода есть строки.|  
|[Метод GetDocumentsForMethodCount](isymencunmanagedmethod-getdocumentsformethodcount-method.md)|Возвращает число документов, в которых у этого метода есть строки.|  
|[Метод GetFileNameFromOffset](isymencunmanagedmethod-getfilenamefromoffset-method.md)|Возвращает имя файла для строки, связанной со смещением.|  
|[Метод GetLineFromOffset](isymencunmanagedmethod-getlinefromoffset-method.md)|Возвращает сведения о строке, связанные со смещением.|  
|[Метод GetSourceExtentInDocument](isymencunmanagedmethod-getsourceextentindocument-method.md)|Возвращает наименьшую начальную строку и самую новую конечную строку для метода в определенном документе.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>Дополнительно

- [Интерфейсы хранилища символов диагностики](diagnostics-symbol-store-interfaces.md)
