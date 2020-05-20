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
ms.openlocfilehash: 3685707f1983ffec413e9cea2df5034ac53f643a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615596"
---
# <a name="isymunmanageddocumentgeturl-method"></a><span data-ttu-id="c9a56-102">Метод ISymUnmanagedDocument::GetURL</span><span class="sxs-lookup"><span data-stu-id="c9a56-102">ISymUnmanagedDocument::GetURL Method</span></span>
<span data-ttu-id="c9a56-103">Возвращает универсальный указатель ресурса (URL) для этого документа.</span><span class="sxs-lookup"><span data-stu-id="c9a56-103">Returns the uniform resource locator (URL) for this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9a56-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c9a56-104">Syntax</span></span>  
  
```cpp  
HRESULT GetURL(  
    [in]  ULONG32  cchUrl,  
    [out] ULONG32  *pcchUrl,  
    [out, size_is(cchUrl), length_is(*pcchUrl)] WCHAR szUrl[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9a56-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c9a56-105">Parameters</span></span>  
 `cchUrl`  
 <span data-ttu-id="c9a56-106">окне Размер буфера (в символах) `szURL` .</span><span class="sxs-lookup"><span data-stu-id="c9a56-106">[in] The size, in characters, of the `szURL` buffer.</span></span>  
  
 `pcchUrl`  
 <span data-ttu-id="c9a56-107">заполняет Указатель на переменную, которая получает размер URL-адреса, включая завершение, равное NULL.</span><span class="sxs-lookup"><span data-stu-id="c9a56-107">[out] A pointer to a variable that receives the size of the URL, including the null termination.</span></span>  
  
 `szUrl`  
 <span data-ttu-id="c9a56-108">заполняет Буфер, содержащий URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="c9a56-108">[out] The buffer containing the URL.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c9a56-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c9a56-109">Return Value</span></span>  
 <span data-ttu-id="c9a56-110">S_OK, если метод выполнен. в противном случае — код ошибки.</span><span class="sxs-lookup"><span data-stu-id="c9a56-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9a56-111">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="c9a56-111">See also</span></span>

- [<span data-ttu-id="c9a56-112">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="c9a56-112">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
