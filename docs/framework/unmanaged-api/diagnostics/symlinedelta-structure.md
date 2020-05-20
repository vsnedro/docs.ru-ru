---
title: Структура SYMLINEDELTA
ms.date: 03/30/2017
api_name:
- SYMLINEDELTA
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- SYMLINEDELTA
helpviewer_keywords:
- SYMLINEDELTA structure [.NET Framework debugging]
ms.assetid: 9634e995-d46d-4397-ab66-cc5781d11e4e
topic_type:
- apiref
ms.openlocfilehash: fb3b89d25b4c2e23c3980b167db4279246c4d27b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609304"
---
# <a name="symlinedelta-structure"></a><span data-ttu-id="2e794-102">Структура SYMLINEDELTA</span><span class="sxs-lookup"><span data-stu-id="2e794-102">SYMLINEDELTA Structure</span></span>
<span data-ttu-id="2e794-103">Предоставляет сведения обработчику символов о методах, которые были перемещены в результате изменений.</span><span class="sxs-lookup"><span data-stu-id="2e794-103">Provides information to the symbol handler about methods that were moved as a result of edits.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e794-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2e794-104">Syntax</span></span>  
  
```cpp  
typedef struct _SYMLINEDELTA  
    {  
        mdMethodDef  mdMethod;  
        INT32        delta;  
    } SYMLINEDELTA;  
```  
  
## <a name="members"></a><span data-ttu-id="2e794-105">Участники</span><span class="sxs-lookup"><span data-stu-id="2e794-105">Members</span></span>  
  
|<span data-ttu-id="2e794-106">Член</span><span class="sxs-lookup"><span data-stu-id="2e794-106">Member</span></span>|<span data-ttu-id="2e794-107">Описание</span><span class="sxs-lookup"><span data-stu-id="2e794-107">Description</span></span>|  
|------------|-----------------|  
|`mdMethod`|<span data-ttu-id="2e794-108">Токен метаданных метода.</span><span class="sxs-lookup"><span data-stu-id="2e794-108">The method's metadata token.</span></span>|  
|`delta`|<span data-ttu-id="2e794-109">Число строк, в которые был перемещен метод.</span><span class="sxs-lookup"><span data-stu-id="2e794-109">The number of lines the method was moved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2e794-110">Требования</span><span class="sxs-lookup"><span data-stu-id="2e794-110">Requirements</span></span>  
 <span data-ttu-id="2e794-111">**Заголовок:** Корсим. idl</span><span class="sxs-lookup"><span data-stu-id="2e794-111">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e794-112">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="2e794-112">See also</span></span>

- [<span data-ttu-id="2e794-113">Структуры хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="2e794-113">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)
