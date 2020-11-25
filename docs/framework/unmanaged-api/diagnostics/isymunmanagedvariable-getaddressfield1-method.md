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
ms.openlocfilehash: e3ea3c0fd65750d52c0cfb10edbe18b1512f724b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729022"
---
# <a name="isymunmanagedvariablegetaddressfield1-method"></a><span data-ttu-id="054cc-102">Метод ISymUnmanagedVariable::GetAddressField1</span><span class="sxs-lookup"><span data-stu-id="054cc-102">ISymUnmanagedVariable::GetAddressField1 Method</span></span>

<span data-ttu-id="054cc-103">Возвращает первое поле адреса для этой переменной.</span><span class="sxs-lookup"><span data-stu-id="054cc-103">Gets the first address field for this variable.</span></span> <span data-ttu-id="054cc-104">Его значение зависит от типа адреса.</span><span class="sxs-lookup"><span data-stu-id="054cc-104">Its meaning depends on the kind of address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="054cc-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="054cc-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAddressField1(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="054cc-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="054cc-106">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="054cc-107">заполняет Указатель на объект `ULONG32` , который получает первое поле адреса.</span><span class="sxs-lookup"><span data-stu-id="054cc-107">[out] A pointer to a `ULONG32` that receives the first address field.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="054cc-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="054cc-108">Return Value</span></span>  

 <span data-ttu-id="054cc-109">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="054cc-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="054cc-110">Требования</span><span class="sxs-lookup"><span data-stu-id="054cc-110">Requirements</span></span>  

 <span data-ttu-id="054cc-111">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="054cc-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="054cc-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="054cc-112">See also</span></span>

- [<span data-ttu-id="054cc-113">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="054cc-113">ISymUnmanagedVariable Interface</span></span>](isymunmanagedvariable-interface.md)
- [<span data-ttu-id="054cc-114">Метод GetAddressField2</span><span class="sxs-lookup"><span data-stu-id="054cc-114">GetAddressField2 Method</span></span>](isymunmanagedvariable-getaddressfield2-method.md)
- [<span data-ttu-id="054cc-115">Метод GetAddressField3</span><span class="sxs-lookup"><span data-stu-id="054cc-115">GetAddressField3 Method</span></span>](isymunmanagedvariable-getaddressfield3-method.md)
- [<span data-ttu-id="054cc-116">Метод GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="054cc-116">GetAddressKind Method</span></span>](isymunmanagedvariable-getaddresskind-method.md)
