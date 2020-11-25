---
title: Метод ISymUnmanagedDocument::GetCheckSumAlgorithmId
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetCheckSumAlgorithmId
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetCheckSumAlgorithmId
helpviewer_keywords:
- ISymUnmanagedDocument::GetCheckSumAlgorithmId method [.NET Framework debugging]
- GetCheckSumAlgorithmId method [.NET Framework debugging]
ms.assetid: c7f941cd-e25b-4b85-b1ce-5f77c9208fa9
topic_type:
- apiref
ms.openlocfilehash: 3c82cf45bca3cc9ec73255586db73a903edaf1ef
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698576"
---
# <a name="isymunmanageddocumentgetchecksumalgorithmid-method"></a>Метод ISymUnmanagedDocument::GetCheckSumAlgorithmId

Возвращает идентификатор алгоритма контрольной суммы или возвращает идентификатор GUID всех нулей, если контрольная сумма отсутствует.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetCheckSumAlgorithmId(  
    [out, retval] GUID*  pRetVal);  
```  
  
## <a name="parameters"></a>Параметры  

 `pRetVal`  
 заполняет Указатель на переменную, которая получает идентификатор алгоритма контрольной суммы.  
  
## <a name="return-value"></a>Возвращаемое значение  

 S_OK, если метод выполнен.  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ISymUnmanagedDocument](isymunmanageddocument-interface.md)
