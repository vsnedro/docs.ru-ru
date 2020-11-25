---
title: Перечисление AssemblyOptions
ms.date: 03/30/2017
api_name:
- AssemblyOptions
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AssemblyOptions
helpviewer_keywords:
- Alink API, AssemblyOptions enumeration
- AssemblyOptions enumeration
ms.assetid: 84f83921-64cb-49e3-ac8b-22a0b77b18a8
topic_type:
- apiref
ms.openlocfilehash: 352e1acd1fdd8297754e18b2e8c6448ea723a557
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717035"
---
# <a name="assemblyoptions-enumeration"></a><span data-ttu-id="f2721-102">Перечисление AssemblyOptions</span><span class="sxs-lookup"><span data-stu-id="f2721-102">AssemblyOptions Enumeration</span></span>

<span data-ttu-id="f2721-103">Перечисляет параметры сборки.</span><span class="sxs-lookup"><span data-stu-id="f2721-103">Enumerates the assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2721-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f2721-104">Syntax</span></span>  
  
```cpp  
typedef enum _AssemblyOptions {  
    optAssemTitle = 0,  
    optAssemDescription,  
    optAssemConfig,  
    optAssemOS,  
    optAssemProcessor,  
    optAssemLocale,  
    optAssemVersion,  
    optAssemCompany,  
    optAssemProduct,  
    optAssemProductVersion,  
    optAssemCopyright,  
    optAssemTrademark,  
    optAssemKeyFile,  
    optAssemKeyName,  
    optAssemAlgID,  
    optAssemFlags,  
    optAssemHalfSign,  
    optAssemFileVersion,  
    optAssemSatelliteVer,  
    optLastAssemOption  
}   AssemblyOptions;  
```  
  
## <a name="fields"></a><span data-ttu-id="f2721-105">Поля</span><span class="sxs-lookup"><span data-stu-id="f2721-105">Fields</span></span>  
  
|<span data-ttu-id="f2721-106">Поле</span><span class="sxs-lookup"><span data-stu-id="f2721-106">Field</span></span>|<span data-ttu-id="f2721-107">Описание</span><span class="sxs-lookup"><span data-stu-id="f2721-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f2721-108">оптассемтитле</span><span class="sxs-lookup"><span data-stu-id="f2721-108">optAssemTitle</span></span>|<span data-ttu-id="f2721-109">Строка — представляет заголовок сборки.</span><span class="sxs-lookup"><span data-stu-id="f2721-109">String - Represents the assembly title.</span></span>|  
|<span data-ttu-id="f2721-110">оптассемдескриптион</span><span class="sxs-lookup"><span data-stu-id="f2721-110">optAssemDescription</span></span>|<span data-ttu-id="f2721-111">Строка — содержит описание сборки.</span><span class="sxs-lookup"><span data-stu-id="f2721-111">String - Contains the assembly description.</span></span>|  
|<span data-ttu-id="f2721-112">оптассемконфиг</span><span class="sxs-lookup"><span data-stu-id="f2721-112">optAssemConfig</span></span>|<span data-ttu-id="f2721-113">Строка — содержит конфигурацию сборки.</span><span class="sxs-lookup"><span data-stu-id="f2721-113">String - Contains the assembly configuration.</span></span>|  
|<span data-ttu-id="f2721-114">оптассемос</span><span class="sxs-lookup"><span data-stu-id="f2721-114">optAssemOS</span></span>|<span data-ttu-id="f2721-115">Строка в кодировке: "Двосплатформид. Двосмажорверсион. Двосминорверсион".</span><span class="sxs-lookup"><span data-stu-id="f2721-115">String - Encoded as: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span></span>|  
|<span data-ttu-id="f2721-116">оптассемпроцессор</span><span class="sxs-lookup"><span data-stu-id="f2721-116">optAssemProcessor</span></span>|<span data-ttu-id="f2721-117">ULONG</span><span class="sxs-lookup"><span data-stu-id="f2721-117">ULONG</span></span>|  
|<span data-ttu-id="f2721-118">оптассемлокале</span><span class="sxs-lookup"><span data-stu-id="f2721-118">optAssemLocale</span></span>|<span data-ttu-id="f2721-119">Строка — содержит языковой стандарт сборки.</span><span class="sxs-lookup"><span data-stu-id="f2721-119">String - Contains the assembly locale.</span></span>|  
|<span data-ttu-id="f2721-120">оптассемверсион</span><span class="sxs-lookup"><span data-stu-id="f2721-120">optAssemVersion</span></span>|<span data-ttu-id="f2721-121">Строка в кодировке: "основная. Дополнительная. сборка. Редакция".</span><span class="sxs-lookup"><span data-stu-id="f2721-121">String - Encoded as: "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="f2721-122">оптассемкомпани</span><span class="sxs-lookup"><span data-stu-id="f2721-122">optAssemCompany</span></span>|<span data-ttu-id="f2721-123">Строка — содержит компанию.</span><span class="sxs-lookup"><span data-stu-id="f2721-123">String - Contains the company.</span></span>|  
|<span data-ttu-id="f2721-124">оптассемпродукт</span><span class="sxs-lookup"><span data-stu-id="f2721-124">optAssemProduct</span></span>|<span data-ttu-id="f2721-125">Строка — содержит имя продукта.</span><span class="sxs-lookup"><span data-stu-id="f2721-125">String - Contains the product name.</span></span>|  
|<span data-ttu-id="f2721-126">оптассемпродуктверсион</span><span class="sxs-lookup"><span data-stu-id="f2721-126">optAssemProductVersion</span></span>|<span data-ttu-id="f2721-127">Строка (также известная как Информатионалверсион).</span><span class="sxs-lookup"><span data-stu-id="f2721-127">String (also known as InformationalVersion).</span></span>|  
|<span data-ttu-id="f2721-128">оптассемкопиригхт</span><span class="sxs-lookup"><span data-stu-id="f2721-128">optAssemCopyright</span></span>|<span data-ttu-id="f2721-129">Строка — содержит сведения об авторских правах.</span><span class="sxs-lookup"><span data-stu-id="f2721-129">String - Contains the copyright information.</span></span>|  
|<span data-ttu-id="f2721-130">оптассемтрадемарк</span><span class="sxs-lookup"><span data-stu-id="f2721-130">optAssemTrademark</span></span>|<span data-ttu-id="f2721-131">Строка — содержит сведения о товарном знаке.</span><span class="sxs-lookup"><span data-stu-id="f2721-131">String - Contains the trademark information.</span></span>|  
|<span data-ttu-id="f2721-132">оптассемкэйфиле</span><span class="sxs-lookup"><span data-stu-id="f2721-132">optAssemKeyFile</span></span>|<span data-ttu-id="f2721-133">Строка (имя файла).</span><span class="sxs-lookup"><span data-stu-id="f2721-133">String (file name).</span></span>|  
|<span data-ttu-id="f2721-134">оптассемкэйнаме</span><span class="sxs-lookup"><span data-stu-id="f2721-134">optAssemKeyName</span></span>|<span data-ttu-id="f2721-135">Строка (имя ключа).</span><span class="sxs-lookup"><span data-stu-id="f2721-135">String (The key name).</span></span>|  
|<span data-ttu-id="f2721-136">оптассемалгид</span><span class="sxs-lookup"><span data-stu-id="f2721-136">optAssemAlgID</span></span>|<span data-ttu-id="f2721-137">ULONG</span><span class="sxs-lookup"><span data-stu-id="f2721-137">ULONG</span></span>|  
|<span data-ttu-id="f2721-138">оптассемфлагс</span><span class="sxs-lookup"><span data-stu-id="f2721-138">optAssemFlags</span></span>|<span data-ttu-id="f2721-139">ULONG</span><span class="sxs-lookup"><span data-stu-id="f2721-139">ULONG</span></span>|  
|<span data-ttu-id="f2721-140">оптассемхалфсигн</span><span class="sxs-lookup"><span data-stu-id="f2721-140">optAssemHalfSign</span></span>|<span data-ttu-id="f2721-141">Bool (также называется DelaySign).</span><span class="sxs-lookup"><span data-stu-id="f2721-141">Bool (Also known as DelaySign).</span></span>|  
|<span data-ttu-id="f2721-142">оптассемфилеверсион</span><span class="sxs-lookup"><span data-stu-id="f2721-142">optAssemFileVersion</span></span>|<span data-ttu-id="f2721-143">Строка, закодированная как "основная. Дополнительная. сборка. Редакция"--то же, что и ProductVersion.</span><span class="sxs-lookup"><span data-stu-id="f2721-143">String - Encoded as "Major.Minor.Build.Revision"--same as ProductVersion.</span></span>|  
|<span data-ttu-id="f2721-144">оптассемсателлитевер</span><span class="sxs-lookup"><span data-stu-id="f2721-144">optAssemSatelliteVer</span></span>|<span data-ttu-id="f2721-145">Строка, закодированная как "основная. Дополнительная. сборка. Редакция".</span><span class="sxs-lookup"><span data-stu-id="f2721-145">String - Encoded as "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="f2721-146">оптластассемоптион</span><span class="sxs-lookup"><span data-stu-id="f2721-146">optLastAssemOption</span></span>|<span data-ttu-id="f2721-147">Счетчик числа элементов.</span><span class="sxs-lookup"><span data-stu-id="f2721-147">A counter of the number of elements.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f2721-148">Требования</span><span class="sxs-lookup"><span data-stu-id="f2721-148">Requirements</span></span>  

 <span data-ttu-id="f2721-149">**Заголовок:** ALink. h</span><span class="sxs-lookup"><span data-stu-id="f2721-149">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="f2721-150">**Библиотека**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="f2721-150">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2721-151">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f2721-151">See also</span></span>

- [<span data-ttu-id="f2721-152">Al.exe (компоновщик сборок)</span><span class="sxs-lookup"><span data-stu-id="f2721-152">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
