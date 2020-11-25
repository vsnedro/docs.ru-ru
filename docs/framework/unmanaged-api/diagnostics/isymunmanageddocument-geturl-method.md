---
title: Метод ISymUnmanagedDocument::GetURL
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetURL
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetURL
helpviewer_keywords:
- GetURL method [.NET Framework debugging]
- ISymUnmanagedDocument::GetURL method [.NET Framework debugging]
ms.assetid: 60600178-c2b5-4cab-b3a5-f0f61acebaf1
topic_type:
- apiref
ms.openlocfilehash: c862b6d3bfa415b622b68898db1ff30c6759e8f2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726942"
---
# <a name="isymunmanageddocumentgeturl-method"></a><span data-ttu-id="bcd38-102">Метод ISymUnmanagedDocument::GetURL</span><span class="sxs-lookup"><span data-stu-id="bcd38-102">ISymUnmanagedDocument::GetURL Method</span></span>

<span data-ttu-id="bcd38-103">Возвращает универсальный указатель ресурса (URL) для этого документа.</span><span class="sxs-lookup"><span data-stu-id="bcd38-103">Returns the uniform resource locator (URL) for this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcd38-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bcd38-104">Syntax</span></span>  
  
```cpp  
HRESULT GetURL(  
    [in]  ULONG32  cchUrl,  
    [out] ULONG32  *pcchUrl,  
    [out, size_is(cchUrl), length_is(*pcchUrl)] WCHAR szUrl[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bcd38-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bcd38-105">Parameters</span></span>  

 `cchUrl`  
 <span data-ttu-id="bcd38-106">окне Размер буфера (в символах) `szURL` .</span><span class="sxs-lookup"><span data-stu-id="bcd38-106">[in] The size, in characters, of the `szURL` buffer.</span></span>  
  
 `pcchUrl`  
 <span data-ttu-id="bcd38-107">заполняет Указатель на переменную, которая получает размер URL-адреса, включая завершение, равное NULL.</span><span class="sxs-lookup"><span data-stu-id="bcd38-107">[out] A pointer to a variable that receives the size of the URL, including the null termination.</span></span>  
  
 `szUrl`  
 <span data-ttu-id="bcd38-108">заполняет Буфер, содержащий URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="bcd38-108">[out] The buffer containing the URL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bcd38-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bcd38-109">Return Value</span></span>  

 <span data-ttu-id="bcd38-110">S_OK, если метод выполнен. в противном случае — код ошибки.</span><span class="sxs-lookup"><span data-stu-id="bcd38-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcd38-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bcd38-111">See also</span></span>

- [<span data-ttu-id="bcd38-112">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="bcd38-112">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
