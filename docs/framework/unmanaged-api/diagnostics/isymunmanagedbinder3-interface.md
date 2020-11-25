---
title: Интерфейс ISymUnmanagedBinder3
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder3 Interface
helpviewer_keywords:
- ISymUnmanagedBinder3 interface [.NET Framework debugging]
ms.assetid: 37527a84-4b03-4f08-8135-94d898599089
topic_type:
- apiref
ms.openlocfilehash: 0cb0b91f2dca8203c37599400b3b61f84eb7d282
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727319"
---
# <a name="isymunmanagedbinder3-interface"></a>Интерфейс ISymUnmanagedBinder3

Расширяет интерфейс связывателя символов. Получите этот интерфейс, вызвав метод `QueryInterface` для объекта, который реализует `ISymUnmanagedBinder` интерфейс.  
  
> [!IMPORTANT]
> При открытии файла базы данных программы (PDB) из ненадежного источника возникает угроза безопасности.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetReaderFromCallback](isymunmanagedbinder3-getreaderfromcallback-method.md)|Позволяет пользователю реализовать или предоставить через обратный вызов либо `IID_IDiaReadExeAtRVACallback` `IID_IDiaReadExeAtOffsetCallback` для получения сведений о каталоге отладки из памяти.|  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы хранилища символов диагностики](diagnostics-symbol-store-interfaces.md)
- [Интерфейс ISymUnmanagedBinder](isymunmanagedbinder-interface.md)
- [Интерфейс ISymUnmanagedBinder2](isymunmanagedbinder2-interface.md)
