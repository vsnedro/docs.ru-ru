---
title: Метод ISymUnmanagedWriter::DefineField
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineField
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineField
helpviewer_keywords:
- ISymUnmanagedWriter::DefineField method [.NET Framework debugging]
- DefineField method, ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: c6a1f797-dbf4-40f5-ab99-d9b4bfb26148
topic_type:
- apiref
ms.openlocfilehash: 5683c10938873821cbe998dbf13937a6a7d24d7c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675091"
---
# <a name="isymunmanagedwriterdefinefield-method"></a><span data-ttu-id="a7599-102">Метод ISymUnmanagedWriter::DefineField</span><span class="sxs-lookup"><span data-stu-id="a7599-102">ISymUnmanagedWriter::DefineField Method</span></span>

<span data-ttu-id="a7599-103">Определяет одну переменную, не находящиеся в методе.</span><span class="sxs-lookup"><span data-stu-id="a7599-103">Defines a single variable that is not within a method.</span></span> <span data-ttu-id="a7599-104">Этот метод используется для определенных полей в классах, битовых полях и т. д.</span><span class="sxs-lookup"><span data-stu-id="a7599-104">This method is used for certain fields in classes, bit fields, and so on.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7599-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a7599-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineField(  
    [in] mdTypeDef    parent,  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7599-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="a7599-106">Parameters</span></span>  

 `parent`  
 <span data-ttu-id="a7599-107">окне Тип метаданных или токен метода.</span><span class="sxs-lookup"><span data-stu-id="a7599-107">[in] The metadata type or method token.</span></span>  
  
 `name`  
 <span data-ttu-id="a7599-108">окне Имя поля.</span><span class="sxs-lookup"><span data-stu-id="a7599-108">[in] The field name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="a7599-109">окне Атрибуты поля.</span><span class="sxs-lookup"><span data-stu-id="a7599-109">[in] The field attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="a7599-110">окне Объект `ULONG32` , который представляет собой размер (в символах) буфера, необходимого для хранения подписи поля.</span><span class="sxs-lookup"><span data-stu-id="a7599-110">[in] A `ULONG32` that is the size, in characters, of the buffer required to contain the field signature.</span></span>  
  
 `signature`  
 <span data-ttu-id="a7599-111">окне Массив подписей полей.</span><span class="sxs-lookup"><span data-stu-id="a7599-111">[in] The array of field signatures.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="a7599-112">окне Тип адреса.</span><span class="sxs-lookup"><span data-stu-id="a7599-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="a7599-113">окне Первый адрес для спецификации поля.</span><span class="sxs-lookup"><span data-stu-id="a7599-113">[in] The first address for the field specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="a7599-114">окне Второй адрес для спецификации поля.</span><span class="sxs-lookup"><span data-stu-id="a7599-114">[in] The second address for the field specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="a7599-115">окне Третий адрес для спецификации поля.</span><span class="sxs-lookup"><span data-stu-id="a7599-115">[in] The third address for the field specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a7599-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a7599-116">Return Value</span></span>  

 <span data-ttu-id="a7599-117">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="a7599-117">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7599-118">Требования</span><span class="sxs-lookup"><span data-stu-id="a7599-118">Requirements</span></span>  

 <span data-ttu-id="a7599-119">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="a7599-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7599-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a7599-120">See also</span></span>

- [<span data-ttu-id="a7599-121">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="a7599-121">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
