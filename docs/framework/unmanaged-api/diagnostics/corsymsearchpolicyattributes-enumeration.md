---
title: Перечисление CorSymSearchPolicyAttributes
ms.date: 03/30/2017
api_name:
- CorSymSearchPolicyAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymSearchPolicyAttributes
helpviewer_keywords:
- CorSymSearchPolicyAttributes enumeration [.NET Framework debugging]
ms.assetid: 03abde84-930a-49d3-bac3-23abb34a0184
topic_type:
- apiref
ms.openlocfilehash: 8af71314cf8a24c710d3b8980c082daaf9186715
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501876"
---
# <a name="corsymsearchpolicyattributes-enumeration"></a><span data-ttu-id="85a8b-102">Перечисление CorSymSearchPolicyAttributes</span><span class="sxs-lookup"><span data-stu-id="85a8b-102">CorSymSearchPolicyAttributes Enumeration</span></span>
<span data-ttu-id="85a8b-103">Указывает политику, используемую при поиске средства чтения символов.</span><span class="sxs-lookup"><span data-stu-id="85a8b-103">Specifies the policy to be used when doing a search for a symbol reader.</span></span> <span data-ttu-id="85a8b-104">Эти константы используются методами [ISymUnmanagedBinder2:: GetReaderForFile2](isymunmanagedbinder2-getreaderforfile2-method.md) и [ISymUnmanagedBinder3:: жетреадерфромкаллбакк](isymunmanagedbinder3-getreaderfromcallback-method.md) .</span><span class="sxs-lookup"><span data-stu-id="85a8b-104">These constants are used by the [ISymUnmanagedBinder2::GetReaderForFile2](isymunmanagedbinder2-getreaderforfile2-method.md) and [ISymUnmanagedBinder3::GetReaderFromCallback](isymunmanagedbinder3-getreaderfromcallback-method.md) methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="85a8b-105">При открытии файла базы данных программы (PDB) из ненадежного источника возникает угроза безопасности.</span><span class="sxs-lookup"><span data-stu-id="85a8b-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85a8b-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="85a8b-106">Syntax</span></span>  
  
```cpp  
typedef enum CorSymSearchPolicyAttributes  
{  
    AllowRegistryAccess      = 0x1,
    AllowSymbolServerAccess  = 0x2,  
    AllowOriginalPathAccess  = 0x4,     //
    AllowReferencePathAccess = 0x8  
} CorSymSearchPolicyAttributes;  
```  
  
## <a name="members"></a><span data-ttu-id="85a8b-107">Участники</span><span class="sxs-lookup"><span data-stu-id="85a8b-107">Members</span></span>  
  
|<span data-ttu-id="85a8b-108">Член</span><span class="sxs-lookup"><span data-stu-id="85a8b-108">Member</span></span>|<span data-ttu-id="85a8b-109">Описание</span><span class="sxs-lookup"><span data-stu-id="85a8b-109">Description</span></span>|  
|------------|-----------------|  
|`AllowRegistryAccess`|<span data-ttu-id="85a8b-110">Запрашивает пути поиска символов в реестре.</span><span class="sxs-lookup"><span data-stu-id="85a8b-110">Queries the registry for symbol search paths.</span></span>|  
|`AllowSymbolServerAccess`|<span data-ttu-id="85a8b-111">Обращается к серверу символов.</span><span class="sxs-lookup"><span data-stu-id="85a8b-111">Accesses a symbol server.</span></span>|  
|`AllowOriginalPathAccess`|<span data-ttu-id="85a8b-112">Выполняет поиск по пути, указанному в каталоге отладки.</span><span class="sxs-lookup"><span data-stu-id="85a8b-112">Searches the path specified in the Debug directory.</span></span>|  
|`AllowReferencePathAccess`|<span data-ttu-id="85a8b-113">Выполняет поиск PDB в месте, где находится EXE-файл.</span><span class="sxs-lookup"><span data-stu-id="85a8b-113">Searches for the PDB in the place where the .exe file is.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="85a8b-114">Требования</span><span class="sxs-lookup"><span data-stu-id="85a8b-114">Requirements</span></span>  
 <span data-ttu-id="85a8b-115">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="85a8b-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85a8b-116">См. также</span><span class="sxs-lookup"><span data-stu-id="85a8b-116">See also</span></span>

- [<span data-ttu-id="85a8b-117">Перечисления хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="85a8b-117">Diagnostics Symbol Store Enumerations</span></span>](diagnostics-symbol-store-enumerations.md)
