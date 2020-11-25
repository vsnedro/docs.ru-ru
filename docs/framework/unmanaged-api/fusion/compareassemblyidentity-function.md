---
title: Функция CompareAssemblyIdentity
ms.date: 03/30/2017
api_name:
- CompareAssemblyIdentity
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- CompareAssemblyIdentity
helpviewer_keywords:
- CompareAssemblyIdentity function [.NET Framework fusion]
ms.assetid: 8b364ae1-8efa-4744-a7da-81fd093d84d6
topic_type:
- apiref
ms.openlocfilehash: da32ce6a40378a6f88cf71bd7707be2079d71068
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717607"
---
# <a name="compareassemblyidentity-function"></a><span data-ttu-id="9c3e6-102">Функция CompareAssemblyIdentity</span><span class="sxs-lookup"><span data-stu-id="9c3e6-102">CompareAssemblyIdentity Function</span></span>

<span data-ttu-id="9c3e6-103">Сравнивает два идентификатора сборки, чтобы определить, являются ли они эквивалентными.</span><span class="sxs-lookup"><span data-stu-id="9c3e6-103">Compares two assembly identities to determine whether they are equivalent.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c3e6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9c3e6-104">Syntax</span></span>  
  
```cpp  
STDAPI CompareAssemblyIdentity (  
    [in]  LPCWSTR                  pwzAssemblyIdentity1,  
    [in]  BOOL                     fUnified1,  
    [in]  LPCWSTR                  pwzAssemblyIdentity2,  
    [in]  BOOL                     fUnified2,  
    [out] BOOL                     *pfEquivalent,  
    [out] AssemblyComparisonResult *pResult  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c3e6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9c3e6-105">Parameters</span></span>  

 `pwzAssemblyIdentity1`  
 <span data-ttu-id="9c3e6-106">окне Текстовое удостоверение первой сборки в сравнении.</span><span class="sxs-lookup"><span data-stu-id="9c3e6-106">[in] The textual identity of the first assembly in the comparison.</span></span>  
  
 `fUnified1`  
 <span data-ttu-id="9c3e6-107">окне Логический флаг, который указывает на определенное пользователем унификацию для `pwzAssemblyIdentity1` .</span><span class="sxs-lookup"><span data-stu-id="9c3e6-107">[in] A Boolean flag that indicates user-specified unification for `pwzAssemblyIdentity1`.</span></span>  
  
 `pwzAssemblyIdentity2`  
 <span data-ttu-id="9c3e6-108">окне Текстовое удостоверение второй сборки в сравнении.</span><span class="sxs-lookup"><span data-stu-id="9c3e6-108">[in] The textual identity of the second assembly in the comparison.</span></span>  
  
 `fUnified2`  
 <span data-ttu-id="9c3e6-109">окне Логический флаг, который указывает на определенное пользователем унификацию для `pwzAssemblyIdentity2` .</span><span class="sxs-lookup"><span data-stu-id="9c3e6-109">[in] A Boolean flag that indicates user-specified unification for `pwzAssemblyIdentity2`.</span></span>  
  
 `pfEquivalent`  
 <span data-ttu-id="9c3e6-110">заполняет Логический флаг, указывающий, эквивалентны ли две сборки.</span><span class="sxs-lookup"><span data-stu-id="9c3e6-110">[out] A Boolean flag that indicates whether the two assemblies are equivalent.</span></span>  
  
 `pResult`  
 <span data-ttu-id="9c3e6-111">заполняет Перечисление [ассембликомпарисонресулт](assemblycomparisonresult-enumeration.md) , содержащее подробные сведения о сравнении.</span><span class="sxs-lookup"><span data-stu-id="9c3e6-111">[out] An [AssemblyComparisonResult](assemblycomparisonresult-enumeration.md) enumeration that contains detailed information about the comparison.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9c3e6-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9c3e6-112">Return Value</span></span>  

 <span data-ttu-id="9c3e6-113">`pfEquivalent` Возвращает логическое значение, указывающее, эквивалентны ли две сборки.</span><span class="sxs-lookup"><span data-stu-id="9c3e6-113">`pfEquivalent` returns a Boolean value that indicates whether the two assemblies are equivalent.</span></span> <span data-ttu-id="9c3e6-114">`pResult` Возвращает одно из `AssemblyComparisonResult` значений, чтобы получить более подробную причину для значения `pfEquivalent` .</span><span class="sxs-lookup"><span data-stu-id="9c3e6-114">`pResult` returns one of the `AssemblyComparisonResult` values, to give a more detailed reason for the value of `pfEquivalent`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c3e6-115">Комментарии</span><span class="sxs-lookup"><span data-stu-id="9c3e6-115">Remarks</span></span>  

 <span data-ttu-id="9c3e6-116">`CompareAssemblyIdentity` проверяет, `pwzAssemblyIdentity1` `pwzAssemblyIdentity2` эквивалентны ли и.</span><span class="sxs-lookup"><span data-stu-id="9c3e6-116">`CompareAssemblyIdentity` checks whether `pwzAssemblyIdentity1` and `pwzAssemblyIdentity2` are equivalent.</span></span> <span data-ttu-id="9c3e6-117">`pfEquivalent` задается в `true` одном или нескольких следующих случаях.</span><span class="sxs-lookup"><span data-stu-id="9c3e6-117">`pfEquivalent` is set to `true` under one or more of the following conditions:</span></span>  
  
- <span data-ttu-id="9c3e6-118">Два удостоверения сборки эквивалентны.</span><span class="sxs-lookup"><span data-stu-id="9c3e6-118">The two assembly identities are equivalent.</span></span> <span data-ttu-id="9c3e6-119">Для строго именованных сборок эквивалентность требует идентичности имени сборки, версии, токена открытого ключа и языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="9c3e6-119">For strongly named assemblies, equivalency requires the assembly name, version, public key token, and culture to be identical.</span></span> <span data-ttu-id="9c3e6-120">Для просто именованных сборок эквивалентность требует соответствия имени сборки и языку и региональным параметрам.</span><span class="sxs-lookup"><span data-stu-id="9c3e6-120">For simply named assemblies, equivalency requires a match on the assembly name and culture.</span></span>  
  
- <span data-ttu-id="9c3e6-121">Оба удостоверения сборки ссылаются на сборки, которые выполняются в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9c3e6-121">Both assembly identities refer to assemblies that run on the .NET Framework.</span></span> <span data-ttu-id="9c3e6-122">Это условие возвращает значение `true` , даже если номера версий сборки не совпадают.</span><span class="sxs-lookup"><span data-stu-id="9c3e6-122">This condition returns `true` even if the assembly version numbers do not match.</span></span>  
  
- <span data-ttu-id="9c3e6-123">Эти две сборки не являются управляемыми сборками, но `fUnified1` или имеют `fUnified2` значение `true` .</span><span class="sxs-lookup"><span data-stu-id="9c3e6-123">The two assemblies are not managed assemblies, but `fUnified1` or `fUnified2` was set to `true`.</span></span>  
  
 <span data-ttu-id="9c3e6-124">`fUnified`Флаг указывает, что все номера версий, вплоть до номера версии строго именованной сборки, считаются эквивалентными сборке со строгим именем.</span><span class="sxs-lookup"><span data-stu-id="9c3e6-124">The `fUnified` flag indicates that all version numbers up to the version number of the strongly named assembly are considered equivalent to the strongly named assembly.</span></span> <span data-ttu-id="9c3e6-125">Например, если значение `pwzAssemblyIndentity1` равно "MyAssembly, Version = 3.0.0.0, Culture = Neutral, PublicKeyToken =....", а значение `fUnified1` равно `true` , это означает, что все версии myAssembly от версии 0.0.0.0 до 3.0.0.0 должны рассматриваться как эквивалентные.</span><span class="sxs-lookup"><span data-stu-id="9c3e6-125">For example, if the value of `pwzAssemblyIndentity1` is "MyAssembly, version=3.0.0.0, culture=neutral, publicKeyToken=....", and the value of `fUnified1` is `true`, this indicates that all versions of MyAssembly from version 0.0.0.0 to 3.0.0.0 should be treated as equivalent.</span></span> <span data-ttu-id="9c3e6-126">В этом случае, если `pwzAssemblyIndentity2` ссылается на ту же сборку, что `pwzAssemblyIndentity1` и, за исключением того, что имеет меньший номер версии, устанавливается `pfEquivalent` в значение `true` .</span><span class="sxs-lookup"><span data-stu-id="9c3e6-126">In such a case, if `pwzAssemblyIndentity2` refers to the same assembly as `pwzAssemblyIndentity1`, except that it has a lower version number, `pfEquivalent` is set to `true`.</span></span> <span data-ttu-id="9c3e6-127">Если `pwzAssemblyIdentity2` ссылается на более высокий номер версии, `pfEquivalent` задается `true` только в том случае, если значение `fUnified2` равно `true` .</span><span class="sxs-lookup"><span data-stu-id="9c3e6-127">If `pwzAssemblyIdentity2` refers to a higher version number, `pfEquivalent` is set to `true` only if the value of `fUnified2` is `true`.</span></span>  
  
 <span data-ttu-id="9c3e6-128">`pResult`Параметр содержит конкретные сведения о том, почему две сборки считаются эквивалентными или не эквивалентными.</span><span class="sxs-lookup"><span data-stu-id="9c3e6-128">The `pResult` parameter includes specific information about why the two assemblies are considered equivalent or not equivalent.</span></span> <span data-ttu-id="9c3e6-129">Дополнительные сведения см. в разделе [перечисление ассембликомпарисонресулт](assemblycomparisonresult-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="9c3e6-129">For more information, see [AssemblyComparisonResult Enumeration](assemblycomparisonresult-enumeration.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c3e6-130">Требования</span><span class="sxs-lookup"><span data-stu-id="9c3e6-130">Requirements</span></span>  

 <span data-ttu-id="9c3e6-131">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c3e6-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c3e6-132">**Заголовок:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="9c3e6-132">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="9c3e6-133">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9c3e6-133">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9c3e6-134">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c3e6-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c3e6-135">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9c3e6-135">See also</span></span>

- [<span data-ttu-id="9c3e6-136">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="9c3e6-136">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
- [<span data-ttu-id="9c3e6-137">Перечисление AssemblyComparisonResult</span><span class="sxs-lookup"><span data-stu-id="9c3e6-137">AssemblyComparisonResult Enumeration</span></span>](assemblycomparisonresult-enumeration.md)
