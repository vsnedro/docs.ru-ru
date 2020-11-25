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
ms.openlocfilehash: aa3b742babe4a94a43e4e6168dea67c0a0245eb0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720585"
---
# <a name="isymunmanagedreadergetsymattribute-method"></a><span data-ttu-id="c0373-102">Метод ISymUnmanagedReader::GetSymAttribute</span><span class="sxs-lookup"><span data-stu-id="c0373-102">ISymUnmanagedReader::GetSymAttribute Method</span></span>

<span data-ttu-id="c0373-103">Возвращает настраиваемый атрибут на основе его имени.</span><span class="sxs-lookup"><span data-stu-id="c0373-103">Gets a custom attribute based upon its name.</span></span> <span data-ttu-id="c0373-104">В отличие от пользовательских атрибутов метаданных эти пользовательские атрибуты хранятся в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="c0373-104">Unlike metadata custom attributes, these custom attributes are held in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0373-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c0373-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSymAttribute (  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is (cBuffer),  
        length_is (*pcBuffer)] BYTE buffer[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0373-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="c0373-106">Parameters</span></span>  

 `parent`  
 <span data-ttu-id="c0373-107">окне Токен метаданных для объекта, для которого запрашивается атрибут.</span><span class="sxs-lookup"><span data-stu-id="c0373-107">[in] The metadata token for the object for which the attribute is requested.</span></span>  
  
 `name`  
 <span data-ttu-id="c0373-108">окне Указатель на переменную, которая указывает извлекаемый атрибут.</span><span class="sxs-lookup"><span data-stu-id="c0373-108">[in] A pointer to the variable that indicates the attribute to retrieve.</span></span>  
  
 `cBuffer`  
 <span data-ttu-id="c0373-109">[in] Размер массива `buffer`.</span><span class="sxs-lookup"><span data-stu-id="c0373-109">[in] The size of the `buffer` array.</span></span>  
  
 `pcBuffer`  
 <span data-ttu-id="c0373-110">заполняет Указатель на переменную, которая получает длину данных атрибута.</span><span class="sxs-lookup"><span data-stu-id="c0373-110">[out] A pointer to the variable that receives the length of the attribute data.</span></span>  
  
 `buffer`  
 <span data-ttu-id="c0373-111">заполняет Указатель на переменную, которая получает данные атрибута.</span><span class="sxs-lookup"><span data-stu-id="c0373-111">[out] A pointer to the variable that receives the attribute data.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c0373-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c0373-112">Return Value</span></span>  

 <span data-ttu-id="c0373-113">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="c0373-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0373-114">Требования</span><span class="sxs-lookup"><span data-stu-id="c0373-114">Requirements</span></span>  

 <span data-ttu-id="c0373-115">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="c0373-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0373-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c0373-116">See also</span></span>

- [<span data-ttu-id="c0373-117">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="c0373-117">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
