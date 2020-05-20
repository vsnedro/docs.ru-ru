---
title: Функция ClrCreateManagedInstance
ms.date: 03/30/2017
api_name:
- ClrCreateManagedInstance
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- ClrCreateManagedInstance
helpviewer_keywords:
- ClrCreateManagedInstance function [.NET Framework hosting]
ms.assetid: 58ba42c0-4857-43bf-a039-73a4dc6544c2
topic_type:
- apiref
ms.openlocfilehash: ecd618ecf08836ea5e38ce738f97fc91ee6426f4
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616818"
---
# <a name="clrcreatemanagedinstance-function"></a><span data-ttu-id="44f11-102">Функция ClrCreateManagedInstance</span><span class="sxs-lookup"><span data-stu-id="44f11-102">ClrCreateManagedInstance Function</span></span>
<span data-ttu-id="44f11-103">Создает экземпляр указанного управляемого типа.</span><span class="sxs-lookup"><span data-stu-id="44f11-103">Creates an instance of the specified managed type.</span></span>  
  
 <span data-ttu-id="44f11-104">Эта функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="44f11-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="44f11-105">Используйте активацию COM для создания экземпляра управляемого типа или используйте размещение (см. Дополнительные сведения о [интерфейсах размещения CLR, добавленных в .NET Framework 4 и 4,5](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span><span class="sxs-lookup"><span data-stu-id="44f11-105">Use COM activation to create an instance of the managed type, or use hosting (see [CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44f11-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="44f11-106">Syntax</span></span>  
  
```cpp  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,
    [in]  REFIID   riid,
    [out] void     **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44f11-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="44f11-107">Parameters</span></span>  
 `pTypeName`  
 <span data-ttu-id="44f11-108">окне Указатель на имя запрашиваемого типа экземпляра.</span><span class="sxs-lookup"><span data-stu-id="44f11-108">[in] A pointer to the name of the instance type being requested.</span></span>  
  
 `riid`  
 <span data-ttu-id="44f11-109">окне `IID`Тип запрашиваемого типа экземпляра.</span><span class="sxs-lookup"><span data-stu-id="44f11-109">[in] The `IID` of the instance type being requested.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="44f11-110">заполняет Указатель на указатель на экземпляр управляемого типа, запрошенный вызывающим объектом.</span><span class="sxs-lookup"><span data-stu-id="44f11-110">[out] A pointer to a pointer to an instance of the managed type that was requested by the caller.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44f11-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="44f11-111">Remarks</span></span>  
 <span data-ttu-id="44f11-112">Среда CLR уже должна быть загружена в процесс.</span><span class="sxs-lookup"><span data-stu-id="44f11-112">The common language runtime should already be loaded into a process.</span></span> <span data-ttu-id="44f11-113">Например, его можно загрузить с помощью вызова функции [CorBindToRuntimeEx](corbindtoruntimeex-function.md) перед `ClrCreateManagedInstance` вызовом функции.</span><span class="sxs-lookup"><span data-stu-id="44f11-113">For example, it can be loaded by using a call to the [CorBindToRuntimeEx](corbindtoruntimeex-function.md) function before the `ClrCreateManagedInstance` function is called.</span></span> <span data-ttu-id="44f11-114">Если среда выполнения не загружена, `ClrCreateManagedInstance` сначала пытается загрузить v 1.0.3705 среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="44f11-114">If the runtime is not loaded, `ClrCreateManagedInstance` first tries to load v1.0.3705 of the runtime.</span></span> <span data-ttu-id="44f11-115">В случае сбоя он пытается загрузить последнюю версию среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="44f11-115">If that fails, it attempts to load the latest version of the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44f11-116">Требования</span><span class="sxs-lookup"><span data-stu-id="44f11-116">Requirements</span></span>  
 <span data-ttu-id="44f11-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44f11-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44f11-118">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="44f11-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="44f11-119">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="44f11-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="44f11-120">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44f11-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44f11-121">См. также статью</span><span class="sxs-lookup"><span data-stu-id="44f11-121">See also</span></span>

- [<span data-ttu-id="44f11-122">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="44f11-122">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
- [<span data-ttu-id="44f11-123">Размещение</span><span class="sxs-lookup"><span data-stu-id="44f11-123">Hosting</span></span>](index.md)
