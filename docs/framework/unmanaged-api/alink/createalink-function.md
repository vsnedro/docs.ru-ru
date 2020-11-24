---
title: Функция CreateALink
ms.date: 03/30/2017
api_name:
- CreateALink
api_location:
- alink.dll
api_type:
- DLLExport
f1_keywords:
- CreateALink
helpviewer_keywords:
- CreateALink function
- Alink API, CreateALink function
ms.assetid: fc73bcb9-6af6-44d8-bc39-2f4400325dae
topic_type:
- apiref
ms.openlocfilehash: 98c6ed4657dc69554a9fcca27145f65c621492f4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683735"
---
# <a name="createalink-function"></a><span data-ttu-id="02792-102">Функция CreateALink</span><span class="sxs-lookup"><span data-stu-id="02792-102">CreateALink Function</span></span>

<span data-ttu-id="02792-103">Создает экземпляр компоновщика сборок и задает указатель на указанный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="02792-103">Creates an instance of the Assembly Linker and sets a pointer to the specified interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02792-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="02792-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateALink (  
   REFIID riid,  
   IUnknown **ppInterface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="02792-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="02792-105">Parameters</span></span>  
  
|<span data-ttu-id="02792-106">Параметр</span><span class="sxs-lookup"><span data-stu-id="02792-106">Parameter</span></span>|<span data-ttu-id="02792-107">Описание</span><span class="sxs-lookup"><span data-stu-id="02792-107">Description</span></span>|  
|---------------|-----------------|  
|`riid`|<span data-ttu-id="02792-108">Физическое имя одного из интерфейсов компоновщика сборок.</span><span class="sxs-lookup"><span data-stu-id="02792-108">The physical name of one of the Assembly Linker interfaces.</span></span>|  
|`ppInterface`|<span data-ttu-id="02792-109">Расположение, которое в случае успешного завершения содержит указатель на `riid` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="02792-109">The location that on successful completion contains a pointer to the `riid` interface.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="02792-110">Требования</span><span class="sxs-lookup"><span data-stu-id="02792-110">Requirements</span></span>  

 <span data-ttu-id="02792-111">**Библиотека**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="02792-111">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02792-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="02792-112">See also</span></span>

- [<span data-ttu-id="02792-113">Al.exe (компоновщик сборок)</span><span class="sxs-lookup"><span data-stu-id="02792-113">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
