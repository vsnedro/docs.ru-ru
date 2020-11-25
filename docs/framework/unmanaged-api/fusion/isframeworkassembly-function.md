---
title: Функция IsFrameworkAssembly
ms.date: 03/30/2017
api_name:
- IsFrameworkAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IsFrameworkAssembly
helpviewer_keywords:
- IsFrameworkAssembly function [.NET Framework fusion]
ms.assetid: b0c6f19b-d4fd-4971-88f0-12ffb5793da3
topic_type:
- apiref
ms.openlocfilehash: 828c7660d6c006e700302d119ce4caf7d76e5d84
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728567"
---
# <a name="isframeworkassembly-function"></a><span data-ttu-id="beadf-102">Функция IsFrameworkAssembly</span><span class="sxs-lookup"><span data-stu-id="beadf-102">IsFrameworkAssembly Function</span></span>

<span data-ttu-id="beadf-103">Возвращает значение, указывающее, является ли указанная сборка управляемой.</span><span class="sxs-lookup"><span data-stu-id="beadf-103">Gets a value that indicates whether the specified assembly is managed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="beadf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="beadf-104">Syntax</span></span>  
  
```cpp  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="beadf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="beadf-105">Parameters</span></span>  

 `pwzAssemblyReference`  
 <span data-ttu-id="beadf-106">окне Имя проверяемой сборки.</span><span class="sxs-lookup"><span data-stu-id="beadf-106">[in] The name of the assembly to check.</span></span>  
  
 `pbIsFrameworkAssembly`  
 <span data-ttu-id="beadf-107">заполняет Логическое значение, указывающее, является ли сборка управляемой.</span><span class="sxs-lookup"><span data-stu-id="beadf-107">[out] A Boolean value that indicates whether the assembly is managed.</span></span>  
  
 `pwzFrameworkAssemblyIdentity`  
 <span data-ttu-id="beadf-108">окне Неканоническая строка, содержащая уникальный идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="beadf-108">[in] An uncanonicalized string that contains the unique identity of the assembly.</span></span>  
  
 `pccSize`  
 <span data-ttu-id="beadf-109">[входной] Размер `pwzFrameworkAssemblyIdentity`.</span><span class="sxs-lookup"><span data-stu-id="beadf-109">[in] The size of `pwzFrameworkAssemblyIdentity`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="beadf-110">Комментарии</span><span class="sxs-lookup"><span data-stu-id="beadf-110">Remarks</span></span>  

 <span data-ttu-id="beadf-111">`pwzAssemblyReference`Параметр является указателем на символьную строку, содержащую имя сборки.</span><span class="sxs-lookup"><span data-stu-id="beadf-111">The `pwzAssemblyReference` parameter is a pointer to a character string that contains the name of an assembly.</span></span>  
  
 <span data-ttu-id="beadf-112">Если эта сборка является частью .NET Framework, `pbIsFrameworkAssembly` параметр будет содержать логическое значение `true` .</span><span class="sxs-lookup"><span data-stu-id="beadf-112">If this assembly is part of the .NET Framework, the `pbIsFrameworkAssembly` parameter will contain a Boolean value of `true`.</span></span>  
  
 <span data-ttu-id="beadf-113">Если именованная сборка не является частью .NET Framework или если `pwzAssemblyReference` параметр не имеет имени сборки, `pbIsFrameworkAssembly` то будет содержать логическое значение `false` .</span><span class="sxs-lookup"><span data-stu-id="beadf-113">If the named assembly is not part of the .NET Framework, or if the `pwzAssemblyReference` parameter does not name an assembly, `pbIsFrameworkAssembly` will contain a Boolean value of `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="beadf-114">Требования</span><span class="sxs-lookup"><span data-stu-id="beadf-114">Requirements</span></span>  

 <span data-ttu-id="beadf-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="beadf-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="beadf-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="beadf-116">See also</span></span>

- [<span data-ttu-id="beadf-117">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="beadf-117">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
