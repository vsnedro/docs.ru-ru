---
title: Метод GetWin32ResBlob
ms.date: 03/30/2017
api_name:
- IALink.GetWin32ResBlob
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetWin32ResBlob
helpviewer_keywords:
- GetWin32ResBlob method
ms.assetid: 36997e04-f9f6-4254-a041-6767ac6c51d9
topic_type:
- apiref
ms.openlocfilehash: 03f6c97b4a5bbbdc0aeaf7b3f07277e66d7d0e9a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684516"
---
# <a name="getwin32resblob-method"></a><span data-ttu-id="00e28-102">Метод GetWin32ResBlob</span><span class="sxs-lookup"><span data-stu-id="00e28-102">GetWin32ResBlob Method</span></span>

<span data-ttu-id="00e28-103">Извлекает BLOB-объект ресурса Win32.</span><span class="sxs-lookup"><span data-stu-id="00e28-103">Retrieves Win32 resource blob.</span></span> <span data-ttu-id="00e28-104">Вызовите этот метод после установки параметров сборки.</span><span class="sxs-lookup"><span data-stu-id="00e28-104">Call this method after setting assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00e28-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="00e28-105">Syntax</span></span>  
  
```cpp  
HRESULT GetWin32ResBlob(  
    mdAssembly    AssemblyID,  
    mdToken       FileToken,  
    BOOL          fDll,  
    LPCWSTR       pszIconFile,  
    const void**  ppResBlob,  
    DWORD*        pcbResBlob  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="00e28-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="00e28-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="00e28-107">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="00e28-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="00e28-108">Токен файла, используемый для получения имени файла, используемого при создании ресурса версии Win32</span><span class="sxs-lookup"><span data-stu-id="00e28-108">File token used to retrieve the filename to be used when constructing the Win32 Version resource</span></span>  
  
 `fDll`  
 <span data-ttu-id="00e28-109">Значение TRUE, если файл является библиотекой DLL, и false для EXE-файла.</span><span class="sxs-lookup"><span data-stu-id="00e28-109">TRUE if file is a DLL, false for an EXE.</span></span>  
  
 `pszIconFile`  
 <span data-ttu-id="00e28-110">Необязательный значок для вставки в большой двоичный объект ресурса.</span><span class="sxs-lookup"><span data-stu-id="00e28-110">Optional icon to insert into the resource blob.</span></span>  
  
 `ppResBlob`  
 <span data-ttu-id="00e28-111">Получает большой двоичный объект ресурса.</span><span class="sxs-lookup"><span data-stu-id="00e28-111">Receives the resource blob.</span></span>  
  
 `pcbResBlob`  
 <span data-ttu-id="00e28-112">Получает размер большого двоичного объекта.</span><span class="sxs-lookup"><span data-stu-id="00e28-112">Receives the size of the blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="00e28-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="00e28-113">Return Value</span></span>  

 <span data-ttu-id="00e28-114">Возвращает S_OK, если метод завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="00e28-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00e28-115">Требования</span><span class="sxs-lookup"><span data-stu-id="00e28-115">Requirements</span></span>  

 <span data-ttu-id="00e28-116">Требуется ALink. h</span><span class="sxs-lookup"><span data-stu-id="00e28-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00e28-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="00e28-117">See also</span></span>

- [<span data-ttu-id="00e28-118">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="00e28-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="00e28-119">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="00e28-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="00e28-120">API ALink</span><span class="sxs-lookup"><span data-stu-id="00e28-120">ALink API</span></span>](index.md)
