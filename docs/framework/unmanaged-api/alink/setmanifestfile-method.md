---
title: Метод SetManifestFile
ms.date: 03/30/2017
api_name:
- IALink3.SetManifestFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetManifestFile
helpviewer_keywords:
- SetManifestFile method
ms.assetid: 1b33de4c-19cb-4a36-a93f-8675b2a36d58
topic_type:
- apiref
ms.openlocfilehash: a4518e93db887dbdc4397636479be8bf5a705c2d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733728"
---
# <a name="setmanifestfile-method"></a><span data-ttu-id="33206-102">Метод SetManifestFile</span><span class="sxs-lookup"><span data-stu-id="33206-102">SetManifestFile Method</span></span>

<span data-ttu-id="33206-103">Позволяет указать или сбросить файл манифеста, используемый компоновщиком при создании сборки.</span><span class="sxs-lookup"><span data-stu-id="33206-103">Enables you to specify or reset the manifest file that the linker uses when it creates the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33206-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="33206-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="33206-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="33206-105">Parameters</span></span>  

 `pszFile`  
  
 <span data-ttu-id="33206-106">Имя файла манифеста, содержимое которого помещается в большой двоичный объект Win32 Resources.</span><span class="sxs-lookup"><span data-stu-id="33206-106">The name of the manifest file whose contents are put into the Win32 resources blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="33206-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="33206-107">Return Value</span></span>  

 <span data-ttu-id="33206-108">Возвращает S_OK, если метод завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="33206-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33206-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="33206-109">Remarks</span></span>  

 <span data-ttu-id="33206-110">Вызовите этот метод, прежде чем запрашивать Win32ResBlob.</span><span class="sxs-lookup"><span data-stu-id="33206-110">Call this before asking for the Win32ResBlob.</span></span> <span data-ttu-id="33206-111">Значение `pszFile` параметра — это имя файла манифеста, содержимое которого считывается и помещается в ресурсы Win32 с идентификатором RT_MANIFEST.</span><span class="sxs-lookup"><span data-stu-id="33206-111">The value of the `pszFile` parameter is the name of the manifest file whose contents are read and put in the Win32 resources with ID of RT_MANIFEST.</span></span> <span data-ttu-id="33206-112">При вызове с помощью параметра NULL все ранее прочитанные манифесты очищаются.</span><span class="sxs-lookup"><span data-stu-id="33206-112">When called by using a parameter of NULL, any previously read manifest is cleared.</span></span> <span data-ttu-id="33206-113">Это позволяет сбросить состояние компоновщика до значения времени инициализации.</span><span class="sxs-lookup"><span data-stu-id="33206-113">This enables one to reset the state of the linker to that of initialization time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33206-114">Требования</span><span class="sxs-lookup"><span data-stu-id="33206-114">Requirements</span></span>  

 <span data-ttu-id="33206-115">Требуется aLink. h</span><span class="sxs-lookup"><span data-stu-id="33206-115">Requires aLink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33206-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="33206-116">See also</span></span>

- [<span data-ttu-id="33206-117">Интерфейс IALink3</span><span class="sxs-lookup"><span data-stu-id="33206-117">IALink3 Interface</span></span>](ialink3-interface.md)
- [<span data-ttu-id="33206-118">API ALink</span><span class="sxs-lookup"><span data-stu-id="33206-118">ALink API</span></span>](index.md)
- [<span data-ttu-id="33206-119">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="33206-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="33206-120">Al.exe (компоновщик сборок)</span><span class="sxs-lookup"><span data-stu-id="33206-120">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
