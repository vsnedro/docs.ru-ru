---
title: Метод ISymUnmanagedDocument::GetLanguageVendor
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetLanguageVendor
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetLanguageVendor
helpviewer_keywords:
- GetLanguageVendor method [.NET Framework debugging]
- ISymUnmanagedDocument::GetLanguageVendor method [.NET Framework debugging]
ms.assetid: 1d4b702e-4922-441d-8b44-03804284f70b
topic_type:
- apiref
ms.openlocfilehash: bac0f187409a191dda1ef635ec9b2da1aee25981
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700955"
---
# <a name="isymunmanageddocumentgetlanguagevendor-method"></a><span data-ttu-id="27245-102">Метод ISymUnmanagedDocument::GetLanguageVendor</span><span class="sxs-lookup"><span data-stu-id="27245-102">ISymUnmanagedDocument::GetLanguageVendor Method</span></span>

<span data-ttu-id="27245-103">Получает поставщика языка этого документа.</span><span class="sxs-lookup"><span data-stu-id="27245-103">Gets the language vendor of this document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27245-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="27245-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLanguageVendor(  
    [out, retval]  GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27245-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="27245-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="27245-106">заполняет Указатель на переменную, которая получает поставщик языка.</span><span class="sxs-lookup"><span data-stu-id="27245-106">[out] A pointer to a variable that receives the language vendor.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="27245-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="27245-107">Return Value</span></span>  

 <span data-ttu-id="27245-108">S_OK, если метод выполнен.</span><span class="sxs-lookup"><span data-stu-id="27245-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27245-109">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="27245-109">See also</span></span>

- [<span data-ttu-id="27245-110">Интерфейс ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="27245-110">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
