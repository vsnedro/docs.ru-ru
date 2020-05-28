---
title: Интерфейс ICeeGen
ms.date: 03/30/2017
api_name:
- ICeeGen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen
helpviewer_keywords:
- ICeeGen interface [.NET Framework metadata]
ms.assetid: 383d20b0-efe9-4e71-8fb8-1186b2e7d0c0
topic_type:
- apiref
ms.openlocfilehash: e6cf0aa6f731d0a417e1a2be0ca1d0f8c9299379
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008278"
---
# <a name="iceegen-interface"></a><span data-ttu-id="7db1d-102">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="7db1d-102">ICeeGen Interface</span></span>
<span data-ttu-id="7db1d-103">Предоставляет методы для динамической компиляции кода.</span><span class="sxs-lookup"><span data-stu-id="7db1d-103">Provides methods for dynamic code compilation.</span></span>  
  
 <span data-ttu-id="7db1d-104">Этот интерфейс устарел и не должен использоваться.</span><span class="sxs-lookup"><span data-stu-id="7db1d-104">This interface is obsolete and should not be used.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7db1d-105">Методы</span><span class="sxs-lookup"><span data-stu-id="7db1d-105">Methods</span></span>  
  
|<span data-ttu-id="7db1d-106">Метод</span><span class="sxs-lookup"><span data-stu-id="7db1d-106">Method</span></span>|<span data-ttu-id="7db1d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="7db1d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7db1d-108">Метод AddSectionReloc</span><span class="sxs-lookup"><span data-stu-id="7db1d-108">AddSectionReloc Method</span></span>](iceegen-addsectionreloc-method.md)|<span data-ttu-id="7db1d-109">Устаревшее.</span><span class="sxs-lookup"><span data-stu-id="7db1d-109">Obsolete.</span></span> <span data-ttu-id="7db1d-110">Добавляет инструкцию. reloc в базу кода.</span><span class="sxs-lookup"><span data-stu-id="7db1d-110">Adds a .reloc instruction to the code base.</span></span>|  
|[<span data-ttu-id="7db1d-111">Метод AllocateMethodBuffer</span><span class="sxs-lookup"><span data-stu-id="7db1d-111">AllocateMethodBuffer Method</span></span>](iceegen-allocatemethodbuffer-method.md)|<span data-ttu-id="7db1d-112">Устаревшее.</span><span class="sxs-lookup"><span data-stu-id="7db1d-112">Obsolete.</span></span> <span data-ttu-id="7db1d-113">Создает буфер указанного размера для метода и получает относительный виртуальный адрес метода.</span><span class="sxs-lookup"><span data-stu-id="7db1d-113">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>|  
|[<span data-ttu-id="7db1d-114">Метод ComputePointer</span><span class="sxs-lookup"><span data-stu-id="7db1d-114">ComputePointer Method</span></span>](iceegen-computepointer-method.md)|<span data-ttu-id="7db1d-115">Устаревшее.</span><span class="sxs-lookup"><span data-stu-id="7db1d-115">Obsolete.</span></span> <span data-ttu-id="7db1d-116">Определяет буфер для указанного раздела кода.</span><span class="sxs-lookup"><span data-stu-id="7db1d-116">Determines the buffer for the specified code section.</span></span>|  
|[<span data-ttu-id="7db1d-117">Метод EmitString</span><span class="sxs-lookup"><span data-stu-id="7db1d-117">EmitString Method</span></span>](iceegen-emitstring-method.md)|<span data-ttu-id="7db1d-118">Устаревшее.</span><span class="sxs-lookup"><span data-stu-id="7db1d-118">Obsolete.</span></span> <span data-ttu-id="7db1d-119">Порождает указанную строку в базу кода.</span><span class="sxs-lookup"><span data-stu-id="7db1d-119">Emits the specified string into the code base.</span></span>|  
|[<span data-ttu-id="7db1d-120">Метод GenerateCeeFile</span><span class="sxs-lookup"><span data-stu-id="7db1d-120">GenerateCeeFile Method</span></span>](iceegen-generateceefile-method.md)|<span data-ttu-id="7db1d-121">Устаревшее.</span><span class="sxs-lookup"><span data-stu-id="7db1d-121">Obsolete.</span></span> <span data-ttu-id="7db1d-122">Создает файл с базовым кодом, который содержит базу кода, загруженную в данный момент `ICeeGen` .</span><span class="sxs-lookup"><span data-stu-id="7db1d-122">Generates a code-base file that contains the code base currently loaded into this `ICeeGen`.</span></span>|  
|[<span data-ttu-id="7db1d-123">Метод GenerateCeeMemoryImage</span><span class="sxs-lookup"><span data-stu-id="7db1d-123">GenerateCeeMemoryImage Method</span></span>](iceegen-generateceememoryimage-method.md)|<span data-ttu-id="7db1d-124">Устаревшее.</span><span class="sxs-lookup"><span data-stu-id="7db1d-124">Obsolete.</span></span> <span data-ttu-id="7db1d-125">Создает изображение в памяти для базы кода.</span><span class="sxs-lookup"><span data-stu-id="7db1d-125">Generates an image in memory for the code base.</span></span>|  
|[<span data-ttu-id="7db1d-126">Метод GetIlSection</span><span class="sxs-lookup"><span data-stu-id="7db1d-126">GetIlSection Method</span></span>](iceegen-getilsection-method.md)|<span data-ttu-id="7db1d-127">Устаревшее.</span><span class="sxs-lookup"><span data-stu-id="7db1d-127">Obsolete.</span></span> <span data-ttu-id="7db1d-128">Возвращает раздел базы кода промежуточного языка, на который ссылается указанный обработчик.</span><span class="sxs-lookup"><span data-stu-id="7db1d-128">Gets the section of the intermediate language code base referenced by the specified handle.</span></span>|  
|[<span data-ttu-id="7db1d-129">Метод GetIMapTokenIface</span><span class="sxs-lookup"><span data-stu-id="7db1d-129">GetIMapTokenIface Method</span></span>](iceegen-getimaptokeniface-method.md)|<span data-ttu-id="7db1d-130">Устаревшее.</span><span class="sxs-lookup"><span data-stu-id="7db1d-130">Obsolete.</span></span> <span data-ttu-id="7db1d-131">Возвращает интерфейс, на который ссылается указанный токен.</span><span class="sxs-lookup"><span data-stu-id="7db1d-131">Gets the interface referenced by the specified token.</span></span>|  
|[<span data-ttu-id="7db1d-132">Метод GetMethodBuffer</span><span class="sxs-lookup"><span data-stu-id="7db1d-132">GetMethodBuffer Method</span></span>](iceegen-getmethodbuffer-method.md)|<span data-ttu-id="7db1d-133">Устаревшее.</span><span class="sxs-lookup"><span data-stu-id="7db1d-133">Obsolete.</span></span> <span data-ttu-id="7db1d-134">Возвращает буфер соответствующего размера для метода по указанному относительному виртуальному адресу.</span><span class="sxs-lookup"><span data-stu-id="7db1d-134">Gets a buffer of the appropriate size for the method at the specified relative virtual address.</span></span>|  
|[<span data-ttu-id="7db1d-135">Метод GetSectionBlock</span><span class="sxs-lookup"><span data-stu-id="7db1d-135">GetSectionBlock Method</span></span>](iceegen-getsectionblock-method.md)|<span data-ttu-id="7db1d-136">Устаревшее.</span><span class="sxs-lookup"><span data-stu-id="7db1d-136">Obsolete.</span></span> <span data-ttu-id="7db1d-137">Возвращает блок базы кода.</span><span class="sxs-lookup"><span data-stu-id="7db1d-137">Gets a section block of the code base.</span></span>|  
|[<span data-ttu-id="7db1d-138">Метод GetSectionCreate</span><span class="sxs-lookup"><span data-stu-id="7db1d-138">GetSectionCreate Method</span></span>](iceegen-getsectioncreate-method.md)|<span data-ttu-id="7db1d-139">Устаревшее.</span><span class="sxs-lookup"><span data-stu-id="7db1d-139">Obsolete.</span></span> <span data-ttu-id="7db1d-140">Создает и получает раздел кода, используя указанные значения имени и флага.</span><span class="sxs-lookup"><span data-stu-id="7db1d-140">Generates and gets a code section using the specified name and flag values.</span></span>|  
|[<span data-ttu-id="7db1d-141">Метод GetSectionDataLen</span><span class="sxs-lookup"><span data-stu-id="7db1d-141">GetSectionDataLen Method</span></span>](iceegen-getsectiondatalen-method.md)|<span data-ttu-id="7db1d-142">Устаревшее.</span><span class="sxs-lookup"><span data-stu-id="7db1d-142">Obsolete.</span></span> <span data-ttu-id="7db1d-143">Возвращает длину указанного раздела.</span><span class="sxs-lookup"><span data-stu-id="7db1d-143">Gets the length of the specified section.</span></span>|  
|[<span data-ttu-id="7db1d-144">Метод GetString</span><span class="sxs-lookup"><span data-stu-id="7db1d-144">GetString Method</span></span>](iceegen-getstring-method.md)|<span data-ttu-id="7db1d-145">Устаревшее.</span><span class="sxs-lookup"><span data-stu-id="7db1d-145">Obsolete.</span></span> <span data-ttu-id="7db1d-146">Возвращает строку, хранящуюся по указанному относительному виртуальному адресу.</span><span class="sxs-lookup"><span data-stu-id="7db1d-146">Gets the string stored at the specified relative virtual address.</span></span>|  
|[<span data-ttu-id="7db1d-147">Метод GetStringSection</span><span class="sxs-lookup"><span data-stu-id="7db1d-147">GetStringSection Method</span></span>](iceegen-getstringsection-method.md)|<span data-ttu-id="7db1d-148">Устаревшее.</span><span class="sxs-lookup"><span data-stu-id="7db1d-148">Obsolete.</span></span> <span data-ttu-id="7db1d-149">Возвращает строковое представление раздела кода, на который ссылается указанный маркер.</span><span class="sxs-lookup"><span data-stu-id="7db1d-149">Gets a string representation of the code section referenced by the specified handle.</span></span>|  
|[<span data-ttu-id="7db1d-150">Метод TruncateSection</span><span class="sxs-lookup"><span data-stu-id="7db1d-150">TruncateSection Method</span></span>](iceegen-truncatesection-method.md)|<span data-ttu-id="7db1d-151">Устаревшее.</span><span class="sxs-lookup"><span data-stu-id="7db1d-151">Obsolete.</span></span> <span data-ttu-id="7db1d-152">Усекает указанный раздел кода на заданную длину.</span><span class="sxs-lookup"><span data-stu-id="7db1d-152">Truncates the specified code section by the specified length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7db1d-153">Требования</span><span class="sxs-lookup"><span data-stu-id="7db1d-153">Requirements</span></span>  
 <span data-ttu-id="7db1d-154">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7db1d-154">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7db1d-155">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="7db1d-155">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7db1d-156">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7db1d-156">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7db1d-157">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7db1d-157">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7db1d-158">См. также статью</span><span class="sxs-lookup"><span data-stu-id="7db1d-158">See also</span></span>

- [<span data-ttu-id="7db1d-159">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="7db1d-159">Metadata Interfaces</span></span>](metadata-interfaces.md)
