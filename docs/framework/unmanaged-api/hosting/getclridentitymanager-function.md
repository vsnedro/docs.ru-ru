---
title: Функция GetCLRIdentityManager
ms.date: 03/30/2017
api_name:
- GetCLRIdentityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetCLRIdentityManager
helpviewer_keywords:
- GetCLRIdentityManager function [.NET Framework hosting]
ms.assetid: 66eeca30-adb4-45f4-aff5-347564c95724
topic_type:
- apiref
ms.openlocfilehash: 8b1e918edf641d38dd6b91d790bcaff8020293a0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493270"
---
# <a name="getclridentitymanager-function"></a><span data-ttu-id="39a11-102">Функция GetCLRIdentityManager</span><span class="sxs-lookup"><span data-stu-id="39a11-102">GetCLRIdentityManager Function</span></span>
<span data-ttu-id="39a11-103">Возвращает указатель на интерфейс, который позволяет среде CLR управлять удостоверениями.</span><span class="sxs-lookup"><span data-stu-id="39a11-103">Gets a pointer to an interface that allows the common language runtime (CLR) to manage identities.</span></span>  
  
 <span data-ttu-id="39a11-104">Эта функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="39a11-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39a11-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="39a11-105">Syntax</span></span>  
  
```cpp  
STDAPI GetCLRIdentityManager(  
    [in]  REFIID      riid,  
    [out] IUnknown  **ppManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39a11-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="39a11-106">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="39a11-107">окне Объект `REFIID` (идентификатор интерфейса), указывающий, какой интерфейс следует получить.</span><span class="sxs-lookup"><span data-stu-id="39a11-107">[in] A `REFIID` (an interface identifier) that specifies which interface to get.</span></span> <span data-ttu-id="39a11-108">Это значение должно быть либо IID_ICLRAssemblyIdentityManager, либо IID_ICLRHostBindingPolicyManager.</span><span class="sxs-lookup"><span data-stu-id="39a11-108">This value must be either IID_ICLRAssemblyIdentityManager or IID_ICLRHostBindingPolicyManager.</span></span>  
  
 `ppManager`  
 <span data-ttu-id="39a11-109">заполняет Указатель на адрес объекта [ICLRAssemblyIdentityManager](iclrassemblyidentitymanager-interface.md) или [ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="39a11-109">[out] A pointer to the address of either an [ICLRAssemblyIdentityManager](iclrassemblyidentitymanager-interface.md) or an [ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39a11-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="39a11-110">Remarks</span></span>  
 <span data-ttu-id="39a11-111">Вызовите функцию [жетреалпрокаддресс](getrealprocaddress-function.md) , чтобы получить указатель на `GetCLRIdentityManager` функцию.</span><span class="sxs-lookup"><span data-stu-id="39a11-111">Call the [GetRealProcAddress](getrealprocaddress-function.md) function to get a pointer to the `GetCLRIdentityManager` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39a11-112">Требования</span><span class="sxs-lookup"><span data-stu-id="39a11-112">Requirements</span></span>  
 <span data-ttu-id="39a11-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39a11-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39a11-114">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="39a11-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="39a11-115">**Библиотека:** MSCorWks. dll</span><span class="sxs-lookup"><span data-stu-id="39a11-115">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="39a11-116">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39a11-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39a11-117">См. также</span><span class="sxs-lookup"><span data-stu-id="39a11-117">See also</span></span>

- [<span data-ttu-id="39a11-118">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="39a11-118">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
