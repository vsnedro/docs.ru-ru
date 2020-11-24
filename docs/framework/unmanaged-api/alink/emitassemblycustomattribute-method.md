---
title: Метод EmitAssemblyCustomAttribute
ms.date: 03/30/2017
api_name:
- IALink.EmitAssemblyCustomAttribute
- EmitAssemblyCustomAttribute
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitAssemblyCustomAttribute
helpviewer_keywords:
- EmitAssemblyCustomAttribute method
ms.assetid: b72f5409-79af-4fa7-90a7-7630eec170f1
topic_type:
- apiref
ms.openlocfilehash: 2070d1ec2aec80638c20c764eed5086c4a42e0fa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676365"
---
# <a name="emitassemblycustomattribute-method"></a><span data-ttu-id="cc6b5-102">Метод EmitAssemblyCustomAttribute</span><span class="sxs-lookup"><span data-stu-id="cc6b5-102">EmitAssemblyCustomAttribute Method</span></span>

<span data-ttu-id="cc6b5-103">Вызовите метод, чтобы установить настраиваемые атрибуты уровня сборки.</span><span class="sxs-lookup"><span data-stu-id="cc6b5-103">Call to set assembly-level custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc6b5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cc6b5-104">Syntax</span></span>  
  
```cpp  
HRESULT EmitAssemblyCustomAttribute(  
    mdAssembly   AssemblyID,  
    mdToken      FileToken,  
    mdToken      tkType,  
    void const*  pCustomValue,  
    DWORD        cbCustomValue,  
    BOOL         bSecurity,  
    BOOL         bAllowMulti  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc6b5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cc6b5-105">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="cc6b5-106">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="cc6b5-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="cc6b5-107">Файл, который разфайлет атрибут.</span><span class="sxs-lookup"><span data-stu-id="cc6b5-107">File that defiles the attribute.</span></span> <span data-ttu-id="cc6b5-108">Может иметь значение NULL `AssemblyID` , если не указывает на непривязанный netmodule.</span><span class="sxs-lookup"><span data-stu-id="cc6b5-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `tkType`  
 <span data-ttu-id="cc6b5-109">Тип настраиваемого атрибута.</span><span class="sxs-lookup"><span data-stu-id="cc6b5-109">Type of the custom attribute.</span></span>  
  
 `pCustomValue`  
 <span data-ttu-id="cc6b5-110">Пользовательские данные значения.</span><span class="sxs-lookup"><span data-stu-id="cc6b5-110">Custom value data.</span></span>  
  
 `cbCustomValue`  
 <span data-ttu-id="cc6b5-111">Длина данных пользовательского значения.</span><span class="sxs-lookup"><span data-stu-id="cc6b5-111">Length of custom value data.</span></span>  
  
 `bSecurity`  
 <span data-ttu-id="cc6b5-112">Значение TRUE, если настраиваемый атрибут связан с подписыванием сборки.</span><span class="sxs-lookup"><span data-stu-id="cc6b5-112">TRUE if the custom attribute is related to assembly signing.</span></span>  
  
 `bAllowMulti`  
 <span data-ttu-id="cc6b5-113">Значение TRUE, если требуется выдавать несколько атрибутов.</span><span class="sxs-lookup"><span data-stu-id="cc6b5-113">TRUE if multiple attributes are to be emitted.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cc6b5-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="cc6b5-114">Return Value</span></span>  

 <span data-ttu-id="cc6b5-115">Возвращает S_OK, если метод завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="cc6b5-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc6b5-116">Требования</span><span class="sxs-lookup"><span data-stu-id="cc6b5-116">Requirements</span></span>  

 <span data-ttu-id="cc6b5-117">Требуется ALink. h</span><span class="sxs-lookup"><span data-stu-id="cc6b5-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc6b5-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cc6b5-118">See also</span></span>

- [<span data-ttu-id="cc6b5-119">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="cc6b5-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="cc6b5-120">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="cc6b5-120">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="cc6b5-121">API ALink</span><span class="sxs-lookup"><span data-stu-id="cc6b5-121">ALink API</span></span>](index.md)
