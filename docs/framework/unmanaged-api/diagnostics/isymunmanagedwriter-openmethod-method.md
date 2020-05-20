---
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
ms.openlocfilehash: d2d16ab0a29fadd3a64d906a64fc46c422e01c45
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610045"
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
  
## <a name="see-also"></a>Дополнительно

- [Интерфейс ISymUnmanagedWriter](isymunmanagedwriter-interface.md)
- [Метод CloseMethod](isymunmanagedwriter-closemethod-method.md)
- [Метод OpenMethod2](isymunmanagedwriter3-openmethod2-method.md)
