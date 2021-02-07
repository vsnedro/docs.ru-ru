---
description: 'Дополнительные сведения о методе: ISymUnmanagedWriter:: Опенмесод'
title: Метод ISymUnmanagedWriter::OpenMethod
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenMethod
helpviewer_keywords:
- ISymUnmanagedWriter::OpenMethod method [.NET Framework debugging]
- OpenMethod method [.NET Framework debugging]
ms.assetid: fb90cb7f-af88-45e8-a99f-80a0bbddb08b
topic_type:
- apiref
ms.openlocfilehash: 2cf7e6bf7c632449c25a2b49c7658fa7b1cc287e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762231"
---
# <a name="isymunmanagedwriteropenmethod-method"></a>Метод ISymUnmanagedWriter::OpenMethod

Открывает метод, в который порождается символьная информация. Данный метод преобразуется в текущий метод для вызовов для определения точек следования, параметров и лексических областей. Существует неявная лексическая область вокруг всего метода. Повторное открытие метода, который ранее был закрыт, стирает все ранее определенные символы для этого метода. Одновременно может быть только один метод открытия.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT OpenMethod(  
    [in] mdMethodDef method);  
```  
  
## <a name="parameters"></a>Параметры  

 `method`  
 окне Токен метаданных для открываемого метода.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedWriter](isymunmanagedwriter-interface.md)
- [Метод CloseMethod](isymunmanagedwriter-closemethod-method.md)
- [Метод OpenMethod2](isymunmanagedwriter3-openmethod2-method.md)
