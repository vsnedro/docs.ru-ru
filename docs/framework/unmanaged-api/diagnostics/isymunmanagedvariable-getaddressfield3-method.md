---
title: Метод ISymUnmanagedVariable::GetAddressField3
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetAddressField3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetAddressField3
helpviewer_keywords:
- ISymUnmanagedVariable::GetAddressField3 method [.NET Framework debugging]
- GetAddressField3 method [.NET Framework debugging]
ms.assetid: 4d834721-ad8d-439d-b356-c6b4aef022fc
topic_type:
- apiref
ms.openlocfilehash: ff888d3e2b86efeea3f4e3d33528f731d85886bf
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615271"
---
# <a name="isymunmanagedvariablegetaddressfield3-method"></a><span data-ttu-id="1c2eb-102">Метод ISymUnmanagedVariable::GetAddressField3</span><span class="sxs-lookup"><span data-stu-id="1c2eb-102">ISymUnmanagedVariable::GetAddressField3 Method</span></span>
<span data-ttu-id="1c2eb-103">Возвращает третье поле адреса для этой переменной.</span><span class="sxs-lookup"><span data-stu-id="1c2eb-103">Gets the third address field for this variable.</span></span> <span data-ttu-id="1c2eb-104">Его значение зависит от типа адреса.</span><span class="sxs-lookup"><span data-stu-id="1c2eb-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c2eb-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1c2eb-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressField3(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c2eb-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="1c2eb-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="1c2eb-107">заполняет Указатель на объект `ULONG32` , который получает третье поле адреса.</span><span class="sxs-lookup"><span data-stu-id="1c2eb-107">[out] A pointer to a `ULONG32` that receives the third address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1c2eb-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1c2eb-108">Return Value</span></span>  
 <span data-ttu-id="1c2eb-109">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="1c2eb-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c2eb-110">Требования</span><span class="sxs-lookup"><span data-stu-id="1c2eb-110">Requirements</span></span>  
 <span data-ttu-id="1c2eb-111">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="1c2eb-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c2eb-112">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="1c2eb-112">See also</span></span>

- [<span data-ttu-id="1c2eb-113">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="1c2eb-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="1c2eb-114">Метод GetAddressField1</span><span class="sxs-lookup"><span data-stu-id="1c2eb-114">GetAddressField1 Method</span></span>](isymunmanagedvariable-getaddressfield1-method.md)
- [<span data-ttu-id="1c2eb-115">Метод GetAddressField2</span><span class="sxs-lookup"><span data-stu-id="1c2eb-115">GetAddressField2 Method</span></span>](isymunmanagedvariable-getaddressfield2-method.md)
- [<span data-ttu-id="1c2eb-116">Метод GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="1c2eb-116">GetAddressKind Method</span></span>](isymunmanagedvariable-getaddresskind-method.md)
