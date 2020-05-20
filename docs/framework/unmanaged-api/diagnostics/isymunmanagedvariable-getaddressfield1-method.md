---
title: Метод ISymUnmanagedVariable::GetAddressField1
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField1
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField1
helpviewer_keywords:
- GetAddressField1 method [.NET Framework debugging]
- ISymUnmanagedVariable::GetAddressField1 method [.NET Framework debugging]
ms.assetid: 25788ed1-0ce3-4b97-96fc-88f8997812a3
topic_type:
- apiref
ms.openlocfilehash: 253fd17178c03bc0c4d8ea031888a404ad56f876
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615284"
---
# <a name="isymunmanagedvariablegetaddressfield1-method"></a><span data-ttu-id="efed0-102">Метод ISymUnmanagedVariable::GetAddressField1</span><span class="sxs-lookup"><span data-stu-id="efed0-102">ISymUnmanagedVariable::GetAddressField1 Method</span></span>
<span data-ttu-id="efed0-103">Возвращает первое поле адреса для этой переменной.</span><span class="sxs-lookup"><span data-stu-id="efed0-103">Gets the first address field for this variable.</span></span> <span data-ttu-id="efed0-104">Его значение зависит от типа адреса.</span><span class="sxs-lookup"><span data-stu-id="efed0-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efed0-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="efed0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressField1(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="efed0-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="efed0-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="efed0-107">заполняет Указатель на объект `ULONG32` , который получает первое поле адреса.</span><span class="sxs-lookup"><span data-stu-id="efed0-107">[out] A pointer to a `ULONG32` that receives the first address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="efed0-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="efed0-108">Return Value</span></span>  
 <span data-ttu-id="efed0-109">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="efed0-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efed0-110">Требования</span><span class="sxs-lookup"><span data-stu-id="efed0-110">Requirements</span></span>  
 <span data-ttu-id="efed0-111">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="efed0-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efed0-112">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="efed0-112">See also</span></span>

- [<span data-ttu-id="efed0-113">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="efed0-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="efed0-114">Метод GetAddressField2</span><span class="sxs-lookup"><span data-stu-id="efed0-114">GetAddressField2 Method</span></span>](isymunmanagedvariable-getaddressfield2-method.md)
- [<span data-ttu-id="efed0-115">Метод GetAddressField3</span><span class="sxs-lookup"><span data-stu-id="efed0-115">GetAddressField3 Method</span></span>](isymunmanagedvariable-getaddressfield3-method.md)
- [<span data-ttu-id="efed0-116">Метод GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="efed0-116">GetAddressKind Method</span></span>](isymunmanagedvariable-getaddresskind-method.md)
