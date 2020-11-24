---
title: Метод ISymUnmanagedReader::GetMethodByVersion
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodByVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodByVersion
helpviewer_keywords:
- ISymUnmanagedReader::GetMethodByVersion method [.NET Framework debugging]
- GetMethodByVersion method [.NET Framework debugging]
ms.assetid: 6ddb0631-4569-41b3-93e4-50fdfaa486dc
topic_type:
- apiref
ms.openlocfilehash: 64e6b9a1942e9a69e43de3d2f09564814328ec08
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689619"
---
# <a name="isymunmanagedreadergetmethodbyversion-method"></a>Метод ISymUnmanagedReader::GetMethodByVersion

Возвращает метод чтения символов по заданному маркеру метода и номеру версии для редактирования и копирования. Номера версий начинаются с 1 и увеличиваются каждый раз при изменении метода в результате операции редактирования и копирования.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetMethodByVersion (  
    [in]  mdMethodDef  token,  
    [in]  int  version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a>Параметры  

 `token`  
 окне Токен метода.  
  
 `version`  
 окне Версия метода.  
  
 `pRetVal`  
 заполняет Указатель на возвращаемый интерфейс.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.  
  
## <a name="requirements"></a>Требования  

 **Заголовок:** Корсим. idl, Корсим. h  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ISymUnmanagedReader](isymunmanagedreader-interface.md)
