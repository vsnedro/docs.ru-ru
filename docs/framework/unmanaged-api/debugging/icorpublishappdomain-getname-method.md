---
title: Метод ICorPublishAppDomain::GetName
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomain.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomain::GetName
helpviewer_keywords:
- GetName method, ICorPublishAppDomain interface [.NET Framework debugging]
- ICorPublishAppDomain::GetName method [.NET Framework debugging]
ms.assetid: 6ef8ac9b-9803-4b65-8b13-25f3e0b1bc6b
topic_type:
- apiref
ms.openlocfilehash: e95f96847c6e069758362fb6febc28dc31911bc9
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396300"
---
# <a name="icorpublishappdomaingetname-method"></a><span data-ttu-id="d66a6-102">Метод ICorPublishAppDomain::GetName</span><span class="sxs-lookup"><span data-stu-id="d66a6-102">ICorPublishAppDomain::GetName Method</span></span>
<span data-ttu-id="d66a6-103">Возвращает имя домена приложения, представленного этим [ICorPublishAppDomain](icorpublishappdomain-interface.md).</span><span class="sxs-lookup"><span data-stu-id="d66a6-103">Gets the name of the application domain that is represented by this [ICorPublishAppDomain](icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d66a6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d66a6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32   cchName,
    [out] ULONG32   *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
        WCHAR       *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d66a6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d66a6-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="d66a6-106">[in] Размер массива `szName`.</span><span class="sxs-lookup"><span data-stu-id="d66a6-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="d66a6-107">заполняет Указатель на число расширенных символов, включая символ null, возвращаемый в `szName` массиве.</span><span class="sxs-lookup"><span data-stu-id="d66a6-107">[out] A pointer to the number of wide characters, including the null character, returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="d66a6-108">заполняет Массив, в котором сохраняется имя.</span><span class="sxs-lookup"><span data-stu-id="d66a6-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d66a6-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="d66a6-109">Remarks</span></span>  
 <span data-ttu-id="d66a6-110">Если `szName` параметр имеет значение, отличное от NULL, `GetName` метод копирует до `cchName` символов (включая знак завершения null) в `szName` .</span><span class="sxs-lookup"><span data-stu-id="d66a6-110">If `szName` is non-null, the `GetName` method copies up to `cchName` characters (including the null terminator) into `szName`.</span></span> <span data-ttu-id="d66a6-111">Если в возвращается значение, отличное от NULL `pcchName` , то фактическое число символов в имени (включая знак завершения null) сохраняется в `szName` массиве.</span><span class="sxs-lookup"><span data-stu-id="d66a6-111">If a non-null is returned in `pcchName`, the actual number of characters in the name (including the null terminator) is stored in the `szName` array.</span></span>  
  
 <span data-ttu-id="d66a6-112">`GetName`Метод возвращает S_OK HRESULT, независимо от количества скопированных символов.</span><span class="sxs-lookup"><span data-stu-id="d66a6-112">The `GetName` method returns an S_OK HRESULT regardless of how many characters were copied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d66a6-113">Требования</span><span class="sxs-lookup"><span data-stu-id="d66a6-113">Requirements</span></span>  
 <span data-ttu-id="d66a6-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d66a6-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d66a6-115">**Заголовок:** Корпуб. idl, Корпуб. h</span><span class="sxs-lookup"><span data-stu-id="d66a6-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="d66a6-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d66a6-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d66a6-117">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d66a6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d66a6-118">См. также статью</span><span class="sxs-lookup"><span data-stu-id="d66a6-118">See also</span></span>

- [<span data-ttu-id="d66a6-119">Интерфейс ICorPublishAppDomain</span><span class="sxs-lookup"><span data-stu-id="d66a6-119">ICorPublishAppDomain Interface</span></span>](icorpublishappdomain-interface.md)
