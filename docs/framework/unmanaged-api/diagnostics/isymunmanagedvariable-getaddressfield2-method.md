---
title: Метод ISymUnmanagedVariable::GetAddressField2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField2
helpviewer_keywords:
- GetAddressField2 method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressField2 method [.NET Framework debugging]
ms.assetid: 1f25b294-72b6-4882-a49b-6c9d364b6008
topic_type:
- apiref
ms.openlocfilehash: 858341d5b8b1b3ecbe9dd5bd39a38f9cfd0d08dc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714176"
---
# <a name="isymunmanagedvariablegetaddressfield2-method"></a><span data-ttu-id="a2c78-102">Метод ISymUnmanagedVariable::GetAddressField2</span><span class="sxs-lookup"><span data-stu-id="a2c78-102">ISymUnmanagedVariable::GetAddressField2 Method</span></span>

<span data-ttu-id="a2c78-103">Получает второе поле адреса для этой переменной.</span><span class="sxs-lookup"><span data-stu-id="a2c78-103">Gets the second address field for this variable.</span></span> <span data-ttu-id="a2c78-104">Его значение зависит от типа адреса.</span><span class="sxs-lookup"><span data-stu-id="a2c78-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2c78-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a2c78-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressField2(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2c78-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="a2c78-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="a2c78-107">заполняет Указатель на объект `ULONG32` , который получает второе поле адреса.</span><span class="sxs-lookup"><span data-stu-id="a2c78-107">[out] A pointer to a `ULONG32` that receives the second address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a2c78-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a2c78-108">Return Value</span></span>  

 <span data-ttu-id="a2c78-109">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="a2c78-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2c78-110">Требования</span><span class="sxs-lookup"><span data-stu-id="a2c78-110">Requirements</span></span>  

 <span data-ttu-id="a2c78-111">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="a2c78-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2c78-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a2c78-112">See also</span></span>

- [<span data-ttu-id="a2c78-113">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="a2c78-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="a2c78-114">Метод GetAddressField1</span><span class="sxs-lookup"><span data-stu-id="a2c78-114">GetAddressField1 Method</span></span>](isymunmanagedvariable-getaddressfield1-method.md)
- [<span data-ttu-id="a2c78-115">Метод GetAddressField3</span><span class="sxs-lookup"><span data-stu-id="a2c78-115">GetAddressField3 Method</span></span>](isymunmanagedvariable-getaddressfield3-method.md)
- [<span data-ttu-id="a2c78-116">Метод GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="a2c78-116">GetAddressKind Method</span></span>](isymunmanagedvariable-getaddresskind-method.md)
