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
# <a name="isymunmanageddocumentgetchecksumalgorithmid-method"></a><span data-ttu-id="e2f4e-102">Метод ISymUnmanagedDocument::GetCheckSumAlgorithmId</span><span class="sxs-lookup"><span data-stu-id="e2f4e-102">ISymUnmanagedDocument::GetCheckSumAlgorithmId Method</span></span>

<span data-ttu-id="e2f4e-103">Возвращает идентификатор алгоритма контрольной суммы или возвращает идентификатор GUID всех нулей, если контрольная сумма отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e2f4e-103">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2f4e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e2f4e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCheckSumAlgorithmId(  
    [out, retval] GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2f4e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e2f4e-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="e2f4e-106">заполняет Указатель на переменную, которая получает идентификатор алгоритма контрольной суммы.</span><span class="sxs-lookup"><span data-stu-id="e2f4e-106">[out] A pointer to a variable that receives the checksum algorithm identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e2f4e-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e2f4e-107">Return Value</span></span>  

 <span data-ttu-id="e2f4e-108">S_OK, если метод выполнен.</span><span class="sxs-lookup"><span data-stu-id="e2f4e-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2f4e-109">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e2f4e-109">See also</span></span>

- [<span data-ttu-id="e2f4e-110">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="e2f4e-110">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
