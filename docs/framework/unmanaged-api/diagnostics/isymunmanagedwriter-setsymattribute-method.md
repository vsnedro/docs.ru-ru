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
ms.openlocfilehash: 484affb2ca87ca50a805d1bb46b7749d294d09f2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683515"
---
# <a name="isymunmanagedwritersetsymattribute-method"></a><span data-ttu-id="1aa08-102">Метод ISymUnmanagedWriter::SetSymAttribute</span><span class="sxs-lookup"><span data-stu-id="1aa08-102">ISymUnmanagedWriter::SetSymAttribute Method</span></span>

<span data-ttu-id="1aa08-103">Определяет настраиваемый атрибут на основе его имени.</span><span class="sxs-lookup"><span data-stu-id="1aa08-103">Defines a custom attribute based upon its name.</span></span> <span data-ttu-id="1aa08-104">Эти атрибуты хранятся в хранилище символов в отличие от пользовательских атрибутов метаданных.</span><span class="sxs-lookup"><span data-stu-id="1aa08-104">These attributes are held in the symbol store, unlike metadata custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1aa08-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1aa08-105">Syntax</span></span>  
  
```cpp  
HRESULT SetSymAttribute(  
    [in] mdToken parent,  
    [in] const WCHAR *name,  
    [in] ULONG32 cData,  
    [in, size_is(cData)] unsigned char data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1aa08-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="1aa08-106">Parameters</span></span>  

 `parent`  
 <span data-ttu-id="1aa08-107">окне Токен метаданных, для которого определяется атрибут.</span><span class="sxs-lookup"><span data-stu-id="1aa08-107">[in] The metadata token for which the attribute is being defined.</span></span>  
  
 `name`  
 <span data-ttu-id="1aa08-108">окне Указатель на объект `WCHAR` , содержащий имя атрибута.</span><span class="sxs-lookup"><span data-stu-id="1aa08-108">[in] A pointer to a `WCHAR` that contains the attribute name.</span></span>  
  
 `cData`  
 <span data-ttu-id="1aa08-109">окне Значение типа `ULONG32` , указывающее размер `data` массива.</span><span class="sxs-lookup"><span data-stu-id="1aa08-109">[in] A `ULONG32` that indicates the size of the `data` array.</span></span>  
  
 `data`  
 <span data-ttu-id="1aa08-110">окне Значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="1aa08-110">[in] The attribute value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1aa08-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1aa08-111">Return Value</span></span>  

 <span data-ttu-id="1aa08-112">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="1aa08-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1aa08-113">Требования</span><span class="sxs-lookup"><span data-stu-id="1aa08-113">Requirements</span></span>  

 <span data-ttu-id="1aa08-114">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="1aa08-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1aa08-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1aa08-115">See also</span></span>

- [<span data-ttu-id="1aa08-116">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="1aa08-116">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
