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
ms.openlocfilehash: c384fe6c4357c63bc56f9f9b1cc907dea64fddf7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700942"
---
# <a name="isymunmanageddocumentgetsourcelength-method"></a><span data-ttu-id="498a3-102">Метод ISymUnmanagedDocument::GetSourceLength</span><span class="sxs-lookup"><span data-stu-id="498a3-102">ISymUnmanagedDocument::GetSourceLength Method</span></span>

<span data-ttu-id="498a3-103">Возвращает длину внедренного источника в байтах.</span><span class="sxs-lookup"><span data-stu-id="498a3-103">Gets the length, in bytes, of the embedded source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="498a3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="498a3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceLength(  
    [out, retval]  ULONG32*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="498a3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="498a3-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="498a3-106">заполняет Указатель на переменную, которая указывает длину внедренного источника в байтах.</span><span class="sxs-lookup"><span data-stu-id="498a3-106">[out] A pointer to a variable that indicates the length, in bytes, of the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="498a3-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="498a3-107">Return Value</span></span>  

 <span data-ttu-id="498a3-108">S_OK, если метод выполнен.</span><span class="sxs-lookup"><span data-stu-id="498a3-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="498a3-109">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="498a3-109">See also</span></span>

- [<span data-ttu-id="498a3-110">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="498a3-110">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
