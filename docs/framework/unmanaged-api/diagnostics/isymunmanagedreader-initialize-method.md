---
description: 'Дополнительные сведения о методе: ISymUnmanagedReader:: Initialize'
title: Метод ISymUnmanagedReader::Initialize
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.Initialize
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::Initialize
helpviewer_keywords:
- ISymUnmanagedReader::Initialize method [.NET Framework debugging]
- Initialize method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 8f0dd2fe-7df7-464e-91f4-5518c586bb5f
topic_type:
- apiref
ms.openlocfilehash: cf7f5df3efed7823fc36bd6c9fc56e0c49d17443
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99763882"
---
# <a name="isymunmanagedreaderinitialize-method"></a>Метод ISymUnmanagedReader::Initialize

Инициализирует средство чтения символов с помощью интерфейса средства импорта метаданных, с которым будет связан этот модуль чтения, вместе с именем файла модуля.  
  
> [!NOTE]
> Этот метод может быть вызван только один раз и должен вызываться до любых других методов чтения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Initialize (  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *filename,  
    [in]  const WCHAR  *searchPath,  
    [in]  IStream      *pIStream);  
```  
  
## <a name="parameters"></a>Параметры  

 `importer`  
 окне Интерфейс средства импорта метаданных, с которым будет связан этот модуль чтения.  
  
 `filename`  
 окне Имя файла модуля. Вместо этого можно использовать `pIStream` параметр.  
  
 `searchPath`  
 окне Путь для поиска. Этот параметр является необязательным.  
  
 `pIStream`  
 окне Файловый поток, используемый в качестве альтернативы параметру filename.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="remarks"></a>Remarks  

 Необходимо указать только один из `filename` `pIStream` параметров или, но не оба. Параметр `searchPath` не обязателен.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также

- [Интерфейс ISymUnmanagedReader](isymunmanagedreader-interface.md)
