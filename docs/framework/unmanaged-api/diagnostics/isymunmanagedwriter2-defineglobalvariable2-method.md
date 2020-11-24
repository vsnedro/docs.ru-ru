---
title: Метод ISymUnmanagedWriter2::DefineGlobalVariable2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineGlobalVariable2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineGlobalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineGlobalVariable2 method [.NET Framework debugging]
- DefineGlobalVariable2 method [.NET Framework debugging]
ms.assetid: 04d569d6-a151-4957-9872-f3f694c3e4a9
topic_type:
- apiref
ms.openlocfilehash: e417854f5f82ba2e0f16848f53b2b605dccf9eb5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683463"
---
# <a name="isymunmanagedwriter2defineglobalvariable2-method"></a><span data-ttu-id="a7738-102">Метод ISymUnmanagedWriter2::DefineGlobalVariable2</span><span class="sxs-lookup"><span data-stu-id="a7738-102">ISymUnmanagedWriter2::DefineGlobalVariable2 Method</span></span>

<span data-ttu-id="a7738-103">Определяет одну глобальную переменную.</span><span class="sxs-lookup"><span data-stu-id="a7738-103">Defines a single global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7738-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a7738-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineGlobalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7738-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a7738-105">Parameters</span></span>  

 `name`  
 <span data-ttu-id="a7738-106">окне Имя глобальной переменной.</span><span class="sxs-lookup"><span data-stu-id="a7738-106">[in] The global variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="a7738-107">окне Атрибуты глобальных переменных.</span><span class="sxs-lookup"><span data-stu-id="a7738-107">[in] The global variable attributes.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="a7738-108">окне Маркер метаданных сигнатуры.</span><span class="sxs-lookup"><span data-stu-id="a7738-108">[in] The metadata token of the signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="a7738-109">окне Тип адреса.</span><span class="sxs-lookup"><span data-stu-id="a7738-109">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="a7738-110">окне Первый адрес для спецификации параметра.</span><span class="sxs-lookup"><span data-stu-id="a7738-110">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="a7738-111">окне Второй адрес для спецификации параметра.</span><span class="sxs-lookup"><span data-stu-id="a7738-111">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="a7738-112">окне Третий адрес для спецификации параметра.</span><span class="sxs-lookup"><span data-stu-id="a7738-112">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a7738-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a7738-113">Return Value</span></span>  

 <span data-ttu-id="a7738-114">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="a7738-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7738-115">Требования</span><span class="sxs-lookup"><span data-stu-id="a7738-115">Requirements</span></span>  

 <span data-ttu-id="a7738-116">**Заголовок:** Корсим. idl</span><span class="sxs-lookup"><span data-stu-id="a7738-116">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7738-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a7738-117">See also</span></span>

- [<span data-ttu-id="a7738-118">Интерфейс ISymUnmanagedWriter2</span><span class="sxs-lookup"><span data-stu-id="a7738-118">ISymUnmanagedWriter2 Interface</span></span>](isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="a7738-119">Метод DefineGlobalVariable</span><span class="sxs-lookup"><span data-stu-id="a7738-119">DefineGlobalVariable Method</span></span>](isymunmanagedwriter-defineglobalvariable-method.md)
