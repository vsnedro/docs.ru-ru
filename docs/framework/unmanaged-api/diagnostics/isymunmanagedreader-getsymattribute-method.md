---
title: Метод ISymUnmanagedReader::GetSymAttribute
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetSymAttribute
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetSymAttribute
helpviewer_keywords:
- GetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedReader::GetSymAttribute method [.NET Framework debugging]
ms.assetid: c675ce7e-76e7-45ff-8273-3b6489a2767c
topic_type:
- apiref
ms.openlocfilehash: b7e2814e56765037b69c6ef7ca0ba610dd7d3c95
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614933"
---
# <a name="isymunmanagedreadergetsymattribute-method"></a><span data-ttu-id="28ab8-102">Метод ISymUnmanagedReader::GetSymAttribute</span><span class="sxs-lookup"><span data-stu-id="28ab8-102">ISymUnmanagedReader::GetSymAttribute Method</span></span>
<span data-ttu-id="28ab8-103">Возвращает настраиваемый атрибут на основе его имени.</span><span class="sxs-lookup"><span data-stu-id="28ab8-103">Gets a custom attribute based upon its name.</span></span> <span data-ttu-id="28ab8-104">В отличие от пользовательских атрибутов метаданных эти пользовательские атрибуты хранятся в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="28ab8-104">Unlike metadata custom attributes, these custom attributes are held in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28ab8-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="28ab8-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSymAttribute (  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is (cBuffer),  
        length_is (*pcBuffer)] BYTE buffer[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28ab8-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="28ab8-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="28ab8-107">окне Токен метаданных для объекта, для которого запрашивается атрибут.</span><span class="sxs-lookup"><span data-stu-id="28ab8-107">[in] The metadata token for the object for which the attribute is requested.</span></span>  
  
 `name`  
 <span data-ttu-id="28ab8-108">окне Указатель на переменную, которая указывает извлекаемый атрибут.</span><span class="sxs-lookup"><span data-stu-id="28ab8-108">[in] A pointer to the variable that indicates the attribute to retrieve.</span></span>  
  
 `cBuffer`  
 <span data-ttu-id="28ab8-109">[in] Размер массива `buffer`.</span><span class="sxs-lookup"><span data-stu-id="28ab8-109">[in] The size of the `buffer` array.</span></span>  
  
 `pcBuffer`  
 <span data-ttu-id="28ab8-110">заполняет Указатель на переменную, которая получает длину данных атрибута.</span><span class="sxs-lookup"><span data-stu-id="28ab8-110">[out] A pointer to the variable that receives the length of the attribute data.</span></span>  
  
 `buffer`  
 <span data-ttu-id="28ab8-111">заполняет Указатель на переменную, которая получает данные атрибута.</span><span class="sxs-lookup"><span data-stu-id="28ab8-111">[out] A pointer to the variable that receives the attribute data.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="28ab8-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="28ab8-112">Return Value</span></span>  
 <span data-ttu-id="28ab8-113">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="28ab8-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28ab8-114">Требования</span><span class="sxs-lookup"><span data-stu-id="28ab8-114">Requirements</span></span>  
 <span data-ttu-id="28ab8-115">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="28ab8-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28ab8-116">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="28ab8-116">See also</span></span>

- [<span data-ttu-id="28ab8-117">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="28ab8-117">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
