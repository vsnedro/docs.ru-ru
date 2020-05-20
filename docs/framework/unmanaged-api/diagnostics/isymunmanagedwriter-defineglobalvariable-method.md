---
title: Метод ISymUnmanagedWriter::DefineGlobalVariable
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineGlobalVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineGlobalVariable
helpviewer_keywords:
- ISymUnmanagedWriter::DefineGlobalVariable method [.NET Framework debugging]
- DefineGlobalVariable method [.NET Framework debugging]
ms.assetid: 843c904a-8176-4d8f-bd47-b4d4c29f4c5c
topic_type:
- apiref
ms.openlocfilehash: 674089f8a1076342a2479c64e253b7dda53ade87
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615206"
---
# <a name="isymunmanagedwriterdefineglobalvariable-method"></a><span data-ttu-id="14734-102">Метод ISymUnmanagedWriter::DefineGlobalVariable</span><span class="sxs-lookup"><span data-stu-id="14734-102">ISymUnmanagedWriter::DefineGlobalVariable Method</span></span>
<span data-ttu-id="14734-103">Определяет одну глобальную переменную.</span><span class="sxs-lookup"><span data-stu-id="14734-103">Defines a single global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14734-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="14734-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineGlobalVariable(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14734-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="14734-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="14734-106">окне Указатель на объект `WCHAR` , который определяет имя глобальной переменной.</span><span class="sxs-lookup"><span data-stu-id="14734-106">[in] A pointer to a `WCHAR` that defines the global variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="14734-107">окне Атрибуты глобальных переменных.</span><span class="sxs-lookup"><span data-stu-id="14734-107">[in] The global variable attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="14734-108">окне Значение типа `ULONG32` , указывающее размер буфера (в символах) `signature` .</span><span class="sxs-lookup"><span data-stu-id="14734-108">[in] A `ULONG32` that indicates the size, in characters, of the `signature` buffer.</span></span>  
  
 `signature`  
 <span data-ttu-id="14734-109">окне Сигнатура глобальной переменной.</span><span class="sxs-lookup"><span data-stu-id="14734-109">[in] The global variable signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="14734-110">окне Тип адреса.</span><span class="sxs-lookup"><span data-stu-id="14734-110">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="14734-111">окне Первый адрес для спецификации параметра.</span><span class="sxs-lookup"><span data-stu-id="14734-111">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="14734-112">окне Второй адрес для спецификации параметра.</span><span class="sxs-lookup"><span data-stu-id="14734-112">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="14734-113">окне Третий адрес для спецификации параметра.</span><span class="sxs-lookup"><span data-stu-id="14734-113">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="14734-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="14734-114">Return Value</span></span>  
 <span data-ttu-id="14734-115">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="14734-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14734-116">Требования</span><span class="sxs-lookup"><span data-stu-id="14734-116">Requirements</span></span>  
 <span data-ttu-id="14734-117">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="14734-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14734-118">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="14734-118">See also</span></span>

- [<span data-ttu-id="14734-119">Интерфейс ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="14734-119">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
- [<span data-ttu-id="14734-120">Метод DefineLocalVariable</span><span class="sxs-lookup"><span data-stu-id="14734-120">DefineLocalVariable Method</span></span>](isymunmanagedwriter-definelocalvariable-method.md)
- [<span data-ttu-id="14734-121">Метод DefineGlobalVariable2</span><span class="sxs-lookup"><span data-stu-id="14734-121">DefineGlobalVariable2 Method</span></span>](isymunmanagedwriter2-defineglobalvariable2-method.md)
