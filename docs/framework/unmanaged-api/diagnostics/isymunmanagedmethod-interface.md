---
title: Интерфейс ISymUnmanagedMethod
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod
helpviewer_keywords:
- ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: f204d74c-cc79-4092-83bb-60654be95649
topic_type:
- apiref
ms.openlocfilehash: 7a98a0c40f68cef9bab1ea2de0850208aaef77a0
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615128"
---
# <a name="isymunmanagedmethod-interface"></a>Интерфейс ISymUnmanagedMethod
Представляет метод в хранилище символов. Этот интерфейс предоставляет доступ только к атрибутам метода, относящимся к символам, а не к атрибутам, связанным с типом.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetNamespace](isymunmanagedmethod-getnamespace-method.md)|Возвращает пространство имен, в котором определен этот метод.|  
|[Метод GetOffset](isymunmanagedmethod-getoffset-method.md)|Возвращает смещение в этом методе, соответствующее заданной позиции в документе.|  
|[Метод GetParameters](isymunmanagedmethod-getparameters-method.md)|Возвращает параметры для этого метода.|  
|[Метод GetRanges](isymunmanagedmethod-getranges-method.md)|При наличии позиции в документе возвращает массив пар начального и конечного смещения, соответствующих диапазонам промежуточного языка MSIL, которые находятся в этом методе.|  
|[Метод GetRootScope](isymunmanagedmethod-getrootscope-method.md)|Возвращает корневую лексическую область внутри этого метода. Эта область включает весь метод.|  
|[Метод GetScopeFromOffset](isymunmanagedmethod-getscopefromoffset-method.md)|Возвращает наиболее окружающую лексическую область внутри этого метода, которая заключает заданное смещение.|  
|[Метод GetSequencePointCount](isymunmanagedmethod-getsequencepointcount-method.md)|Возвращает число точек следования в этом методе.|  
|[Метод GetSequencePoints](isymunmanagedmethod-getsequencepoints-method.md)|Возвращает все точки следования в этом методе.|  
|[Метод GetSourceStartEnd](isymunmanagedmethod-getsourcestartend-method.md)|Возвращает начальную и конечную позиции документа для источника данного метода.|  
|[Метод GetToken](isymunmanagedmethod-gettoken-method.md)|Возвращает маркер метаданных для данного метода.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>Дополнительно

- [Интерфейсы хранилища символов диагностики](diagnostics-symbol-store-interfaces.md)
