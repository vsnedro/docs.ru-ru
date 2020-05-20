---
title: Метод ISymUnmanagedDocument::GetSourceLength
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetSourceLength
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetSourceLength
helpviewer_keywords:
- GetSourceLength method [.NET Framework debugging]
- ISymUnmanagedDocument::GetSourceLength method [.NET Framework debugging]
ms.assetid: e087dbbb-f4fb-4fbe-8292-e4f1a14d0df2
topic_type:
- apiref
ms.openlocfilehash: e84639c1d63e6935b9b363f01c12bf0fbd3390e3
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615622"
---
# <a name="isymunmanageddocumentgetsourcelength-method"></a><span data-ttu-id="ab09e-102">Метод ISymUnmanagedDocument::GetSourceLength</span><span class="sxs-lookup"><span data-stu-id="ab09e-102">ISymUnmanagedDocument::GetSourceLength Method</span></span>
<span data-ttu-id="ab09e-103">Возвращает длину внедренного источника в байтах.</span><span class="sxs-lookup"><span data-stu-id="ab09e-103">Gets the length, in bytes, of the embedded source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab09e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ab09e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceLength(  
    [out, retval]  ULONG32*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab09e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ab09e-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="ab09e-106">заполняет Указатель на переменную, которая указывает длину внедренного источника в байтах.</span><span class="sxs-lookup"><span data-stu-id="ab09e-106">[out] A pointer to a variable that indicates the length, in bytes, of the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ab09e-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ab09e-107">Return Value</span></span>  
 <span data-ttu-id="ab09e-108">S_OK, если метод выполнен.</span><span class="sxs-lookup"><span data-stu-id="ab09e-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab09e-109">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="ab09e-109">See also</span></span>

- [<span data-ttu-id="ab09e-110">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="ab09e-110">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
