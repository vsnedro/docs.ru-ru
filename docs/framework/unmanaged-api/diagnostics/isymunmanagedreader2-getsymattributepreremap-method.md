---
title: Метод ISymUnmanagedReader2::GetSymAttributePreRemap
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetSymAttributePreRemap
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetSymAttributePreRemap
helpviewer_keywords:
- GetSymAttributePreRemap method [.NET Framework debugging]
- ISymUnmanagedReader2::GetSymAttributePreRemap method [.NET Framework debugging]
ms.assetid: 7580d546-a709-40c5-ad02-aa70d774fd0b
topic_type:
- apiref
ms.openlocfilehash: 812c0d08930efff9140c6e897d3f93c4909e8464
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709093"
---
# <a name="isymunmanagedreader2getsymattributepreremap-method"></a><span data-ttu-id="a5d5f-102">Метод ISymUnmanagedReader2::GetSymAttributePreRemap</span><span class="sxs-lookup"><span data-stu-id="a5d5f-102">ISymUnmanagedReader2::GetSymAttributePreRemap Method</span></span>

<span data-ttu-id="a5d5f-103">Возвращает настраиваемый атрибут на основе его имени.</span><span class="sxs-lookup"><span data-stu-id="a5d5f-103">Gets a custom attribute based upon its name.</span></span> <span data-ttu-id="a5d5f-104">В отличие от пользовательских атрибутов метаданных эти атрибуты хранятся в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="a5d5f-104">Unlike metadata custom attributes, these attributes are held in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5d5f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a5d5f-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSymAttributePreRemap(  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is(cBuffer),  
        length_is(*pcBuffer)] BYTE buffer[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5d5f-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="a5d5f-106">Parameters</span></span>  

 `parent`  
 <span data-ttu-id="a5d5f-107">окне Маркер метаданных родителя.</span><span class="sxs-lookup"><span data-stu-id="a5d5f-107">[in] The metadata token of the parent.</span></span>  
  
 `name`  
 <span data-ttu-id="a5d5f-108">окне Указатель на объект `WCHAR` , содержащий имя.</span><span class="sxs-lookup"><span data-stu-id="a5d5f-108">[in] A pointer to a `WCHAR` that contains the name.</span></span>  
  
 `cBuffer`  
 <span data-ttu-id="a5d5f-109">окне Значение типа `ULONG32` , указывающее размер `buffer` массива.</span><span class="sxs-lookup"><span data-stu-id="a5d5f-109">[in] A `ULONG32` that indicates the size of the `buffer` array.</span></span>  
  
 `pcBuffer`  
 <span data-ttu-id="a5d5f-110">заполняет Указатель на объект `ULONG32` , который получает размер буфера, необходимого для хранения байтов атрибута.</span><span class="sxs-lookup"><span data-stu-id="a5d5f-110">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the attribute bytes.</span></span>  
  
 `buffer`  
 <span data-ttu-id="a5d5f-111">заполняет Указатель на буфер, который получает байты атрибута.</span><span class="sxs-lookup"><span data-stu-id="a5d5f-111">[out] A pointer to the buffer that receives the attribute bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a5d5f-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a5d5f-112">Return Value</span></span>  

 <span data-ttu-id="a5d5f-113">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="a5d5f-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5d5f-114">Требования</span><span class="sxs-lookup"><span data-stu-id="a5d5f-114">Requirements</span></span>  

 <span data-ttu-id="a5d5f-115">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="a5d5f-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5d5f-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a5d5f-116">See also</span></span>

- [<span data-ttu-id="a5d5f-117">Интерфейс ISymUnmanagedReader2</span><span class="sxs-lookup"><span data-stu-id="a5d5f-117">ISymUnmanagedReader2 Interface</span></span>](isymunmanagedreader2-interface.md)
