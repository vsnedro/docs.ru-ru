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
ms.openlocfilehash: 9d1196749e033c71b0c8923d0325eb4886122d1a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733663"
---
# <a name="getclridentitymanager-function"></a><span data-ttu-id="227ec-102">Функция GetCLRIdentityManager</span><span class="sxs-lookup"><span data-stu-id="227ec-102">GetCLRIdentityManager Function</span></span>

<span data-ttu-id="227ec-103">Возвращает указатель на интерфейс, который позволяет среде CLR управлять удостоверениями.</span><span class="sxs-lookup"><span data-stu-id="227ec-103">Gets a pointer to an interface that allows the common language runtime (CLR) to manage identities.</span></span>  
  
 <span data-ttu-id="227ec-104">Эта функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="227ec-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="227ec-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="227ec-105">Syntax</span></span>  
  
```cpp  
STDAPI GetCLRIdentityManager(  
    [in]  REFIID      riid,  
    [out] IUnknown  **ppManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="227ec-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="227ec-106">Parameters</span></span>  

 `riid`  
 <span data-ttu-id="227ec-107">окне Объект `REFIID` (идентификатор интерфейса), указывающий, какой интерфейс следует получить.</span><span class="sxs-lookup"><span data-stu-id="227ec-107">[in] A `REFIID` (an interface identifier) that specifies which interface to get.</span></span> <span data-ttu-id="227ec-108">Это значение должно быть либо IID_ICLRAssemblyIdentityManager, либо IID_ICLRHostBindingPolicyManager.</span><span class="sxs-lookup"><span data-stu-id="227ec-108">This value must be either IID_ICLRAssemblyIdentityManager or IID_ICLRHostBindingPolicyManager.</span></span>  
  
 `ppManager`  
 <span data-ttu-id="227ec-109">заполняет Указатель на адрес объекта [ICLRAssemblyIdentityManager](iclrassemblyidentitymanager-interface.md) или [ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="227ec-109">[out] A pointer to the address of either an [ICLRAssemblyIdentityManager](iclrassemblyidentitymanager-interface.md) or an [ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="227ec-110">Комментарии</span><span class="sxs-lookup"><span data-stu-id="227ec-110">Remarks</span></span>  

 <span data-ttu-id="227ec-111">Вызовите функцию [жетреалпрокаддресс](getrealprocaddress-function.md) , чтобы получить указатель на `GetCLRIdentityManager` функцию.</span><span class="sxs-lookup"><span data-stu-id="227ec-111">Call the [GetRealProcAddress](getrealprocaddress-function.md) function to get a pointer to the `GetCLRIdentityManager` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="227ec-112">Требования</span><span class="sxs-lookup"><span data-stu-id="227ec-112">Requirements</span></span>  

 <span data-ttu-id="227ec-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="227ec-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="227ec-114">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="227ec-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="227ec-115">**Библиотека:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="227ec-115">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="227ec-116">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="227ec-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="227ec-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="227ec-117">See also</span></span>

- [<span data-ttu-id="227ec-118">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="227ec-118">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
