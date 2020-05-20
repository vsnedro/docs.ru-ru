---
title: Метод ISymUnmanagedWriter::SetSymAttribute
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetSymAttribute
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetSymAttribute
helpviewer_keywords:
- SetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedWriter::SetSymAttribute method [.NET Framework debugging]
ms.assetid: 64d9b80e-b883-4539-89c7-03573185a1eb
topic_type:
- apiref
ms.openlocfilehash: 39b0c065a324f2b3939467901739f995bc9abbad
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614764"
---
# <a name="isymunmanagedwritersetsymattribute-method"></a><span data-ttu-id="0a850-102">Метод ISymUnmanagedWriter::SetSymAttribute</span><span class="sxs-lookup"><span data-stu-id="0a850-102">ISymUnmanagedWriter::SetSymAttribute Method</span></span>
<span data-ttu-id="0a850-103">Определяет настраиваемый атрибут на основе его имени.</span><span class="sxs-lookup"><span data-stu-id="0a850-103">Defines a custom attribute based upon its name.</span></span> <span data-ttu-id="0a850-104">Эти атрибуты хранятся в хранилище символов в отличие от пользовательских атрибутов метаданных.</span><span class="sxs-lookup"><span data-stu-id="0a850-104">These attributes are held in the symbol store, unlike metadata custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a850-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0a850-105">Syntax</span></span>  
  
```cpp  
HRESULT SetSymAttribute(  
    [in] mdToken parent,  
    [in] const WCHAR *name,  
    [in] ULONG32 cData,  
    [in, size_is(cData)] unsigned char data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a850-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="0a850-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="0a850-107">окне Токен метаданных, для которого определяется атрибут.</span><span class="sxs-lookup"><span data-stu-id="0a850-107">[in] The metadata token for which the attribute is being defined.</span></span>  
  
 `name`  
 <span data-ttu-id="0a850-108">окне Указатель на объект `WCHAR` , содержащий имя атрибута.</span><span class="sxs-lookup"><span data-stu-id="0a850-108">[in] A pointer to a `WCHAR` that contains the attribute name.</span></span>  
  
 `cData`  
 <span data-ttu-id="0a850-109">окне Значение типа `ULONG32` , указывающее размер `data` массива.</span><span class="sxs-lookup"><span data-stu-id="0a850-109">[in] A `ULONG32` that indicates the size of the `data` array.</span></span>  
  
 `data`  
 <span data-ttu-id="0a850-110">окне Значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="0a850-110">[in] The attribute value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0a850-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0a850-111">Return Value</span></span>  
 <span data-ttu-id="0a850-112">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="0a850-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a850-113">Требования</span><span class="sxs-lookup"><span data-stu-id="0a850-113">Requirements</span></span>  
 <span data-ttu-id="0a850-114">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="0a850-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a850-115">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="0a850-115">See also</span></span>

- [<span data-ttu-id="0a850-116">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="0a850-116">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
