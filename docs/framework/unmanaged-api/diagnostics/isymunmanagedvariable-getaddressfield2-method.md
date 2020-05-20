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
ms.openlocfilehash: 6256d052780b1c610e61267be2517954d722a42d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610604"
---
# <a name="isymunmanagedvariablegetaddressfield2-method"></a><span data-ttu-id="6aa76-102">Метод ISymUnmanagedVariable::GetAddressField2</span><span class="sxs-lookup"><span data-stu-id="6aa76-102">ISymUnmanagedVariable::GetAddressField2 Method</span></span>
<span data-ttu-id="6aa76-103">Получает второе поле адреса для этой переменной.</span><span class="sxs-lookup"><span data-stu-id="6aa76-103">Gets the second address field for this variable.</span></span> <span data-ttu-id="6aa76-104">Его значение зависит от типа адреса.</span><span class="sxs-lookup"><span data-stu-id="6aa76-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6aa76-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6aa76-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressField2(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6aa76-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="6aa76-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="6aa76-107">заполняет Указатель на объект `ULONG32` , который получает второе поле адреса.</span><span class="sxs-lookup"><span data-stu-id="6aa76-107">[out] A pointer to a `ULONG32` that receives the second address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6aa76-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6aa76-108">Return Value</span></span>  
 <span data-ttu-id="6aa76-109">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="6aa76-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6aa76-110">Требования</span><span class="sxs-lookup"><span data-stu-id="6aa76-110">Requirements</span></span>  
 <span data-ttu-id="6aa76-111">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="6aa76-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6aa76-112">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="6aa76-112">See also</span></span>

- [<span data-ttu-id="6aa76-113">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="6aa76-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="6aa76-114">Метод GetAddressField1</span><span class="sxs-lookup"><span data-stu-id="6aa76-114">GetAddressField1 Method</span></span>](isymunmanagedvariable-getaddressfield1-method.md)
- [<span data-ttu-id="6aa76-115">Метод GetAddressField3</span><span class="sxs-lookup"><span data-stu-id="6aa76-115">GetAddressField3 Method</span></span>](isymunmanagedvariable-getaddressfield3-method.md)
- [<span data-ttu-id="6aa76-116">Метод GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="6aa76-116">GetAddressKind Method</span></span>](isymunmanagedvariable-getaddresskind-method.md)
