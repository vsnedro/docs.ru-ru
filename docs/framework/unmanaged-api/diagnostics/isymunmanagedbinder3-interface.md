---
description: 'Дополнительные сведения о: интерфейс ISymUnmanagedBinder3'
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
ms.openlocfilehash: 6d2172fb119076cea6d0f912fb3f403d36856599
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689837"
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
  
## <a name="see-also"></a>См. также

- [Интерфейсы хранилища символов диагностики](diagnostics-symbol-store-interfaces.md)
- [Интерфейс ISymUnmanagedBinder](isymunmanagedbinder-interface.md)
- [Интерфейс ISymUnmanagedBinder2](isymunmanagedbinder2-interface.md)
