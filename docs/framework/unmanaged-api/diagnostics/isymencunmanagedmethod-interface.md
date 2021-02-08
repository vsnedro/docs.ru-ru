---
description: 'Дополнительные сведения о: интерфейс ISymENCUnmanagedMethod'
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
ms.openlocfilehash: 59dd56c20279b2507fc4432182d0abb5b3e9c289
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790325"
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
  
## <a name="see-also"></a>См. также

- [Интерфейсы хранилища символов диагностики](diagnostics-symbol-store-interfaces.md)
