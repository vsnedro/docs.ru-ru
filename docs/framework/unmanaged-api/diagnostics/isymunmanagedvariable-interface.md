---
title: Интерфейс ISymUnmanagedVariable
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable
helpviewer_keywords:
- ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: 704c69ba-77bc-40d7-8c0c-400061686321
topic_type:
- apiref
ms.openlocfilehash: d05d4451e8fb75829b22e0a1b9c9afcb0607eb8b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610175"
---
# <a name="isymunmanagedvariable-interface"></a><span data-ttu-id="9a763-102">Интерфейс ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="9a763-102">ISymUnmanagedVariable Interface</span></span>
<span data-ttu-id="9a763-103">Представляет переменную, например параметр, локальную переменную или поле.</span><span class="sxs-lookup"><span data-stu-id="9a763-103">Represents a variable, such as a parameter, a local variable, or a field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9a763-104">Методы</span><span class="sxs-lookup"><span data-stu-id="9a763-104">Methods</span></span>  
  
|<span data-ttu-id="9a763-105">Метод</span><span class="sxs-lookup"><span data-stu-id="9a763-105">Method</span></span>|<span data-ttu-id="9a763-106">Описание</span><span class="sxs-lookup"><span data-stu-id="9a763-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9a763-107">Метод GetAddressField1</span><span class="sxs-lookup"><span data-stu-id="9a763-107">GetAddressField1 Method</span></span>](isymunmanagedvariable-getaddressfield1-method.md)|<span data-ttu-id="9a763-108">Возвращает первое поле адреса для этой переменной.</span><span class="sxs-lookup"><span data-stu-id="9a763-108">Gets the first address field for this variable.</span></span> <span data-ttu-id="9a763-109">Его значение зависит от типа адреса.</span><span class="sxs-lookup"><span data-stu-id="9a763-109">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="9a763-110">Метод GetAddressField2</span><span class="sxs-lookup"><span data-stu-id="9a763-110">GetAddressField2 Method</span></span>](isymunmanagedvariable-getaddressfield2-method.md)|<span data-ttu-id="9a763-111">Получает второе поле адреса для этой переменной.</span><span class="sxs-lookup"><span data-stu-id="9a763-111">Gets the second address field for this variable.</span></span> <span data-ttu-id="9a763-112">Его значение зависит от типа адреса.</span><span class="sxs-lookup"><span data-stu-id="9a763-112">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="9a763-113">Метод GetAddressField3</span><span class="sxs-lookup"><span data-stu-id="9a763-113">GetAddressField3 Method</span></span>](isymunmanagedvariable-getaddressfield3-method.md)|<span data-ttu-id="9a763-114">Возвращает третье поле адреса для этой переменной.</span><span class="sxs-lookup"><span data-stu-id="9a763-114">Gets the third address field for this variable.</span></span> <span data-ttu-id="9a763-115">Его значение зависит от типа адреса.</span><span class="sxs-lookup"><span data-stu-id="9a763-115">Its meaning depends on the kind of address.</span></span>|  
|[<span data-ttu-id="9a763-116">Метод GetAddressKind</span><span class="sxs-lookup"><span data-stu-id="9a763-116">GetAddressKind Method</span></span>](isymunmanagedvariable-getaddresskind-method.md)|<span data-ttu-id="9a763-117">Возвращает тип адреса этой переменной.</span><span class="sxs-lookup"><span data-stu-id="9a763-117">Gets the kind of address of this variable.</span></span>|  
|[<span data-ttu-id="9a763-118">Метод GetAttributes</span><span class="sxs-lookup"><span data-stu-id="9a763-118">GetAttributes Method</span></span>](isymunmanagedvariable-getattributes-method.md)|<span data-ttu-id="9a763-119">Возвращает флаги атрибута для этой переменной.</span><span class="sxs-lookup"><span data-stu-id="9a763-119">Gets the attribute flags for this variable.</span></span>|  
|[<span data-ttu-id="9a763-120">Метод GetEndOffset</span><span class="sxs-lookup"><span data-stu-id="9a763-120">GetEndOffset Method</span></span>](isymunmanagedvariable-getendoffset-method.md)|<span data-ttu-id="9a763-121">Возвращает конечное смещение данной переменной в родительском объекте.</span><span class="sxs-lookup"><span data-stu-id="9a763-121">Gets the end offset of this variable within its parent.</span></span>|  
|[<span data-ttu-id="9a763-122">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="9a763-122">GetName Method</span></span>](isymunmanagedvariable-getname-method.md)|<span data-ttu-id="9a763-123">Возвращает имя этой переменной.</span><span class="sxs-lookup"><span data-stu-id="9a763-123">Gets the name of this variable.</span></span>|  
|[<span data-ttu-id="9a763-124">Метод GetSignature</span><span class="sxs-lookup"><span data-stu-id="9a763-124">GetSignature Method</span></span>](isymunmanagedvariable-getsignature-method.md)|<span data-ttu-id="9a763-125">Возвращает сигнатуру этой переменной.</span><span class="sxs-lookup"><span data-stu-id="9a763-125">Gets the signature of this variable.</span></span>|  
|[<span data-ttu-id="9a763-126">Метод GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="9a763-126">GetStartOffset Method</span></span>](isymunmanagedvariable-getstartoffset-method.md)|<span data-ttu-id="9a763-127">Возвращает начальное смещение этой переменной в родительском элементе.</span><span class="sxs-lookup"><span data-stu-id="9a763-127">Gets the start offset of this variable within its parent.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9a763-128">Требования</span><span class="sxs-lookup"><span data-stu-id="9a763-128">Requirements</span></span>  
 <span data-ttu-id="9a763-129">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="9a763-129">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a763-130">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="9a763-130">See also</span></span>

- [<span data-ttu-id="9a763-131">Интерфейсы хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="9a763-131">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
