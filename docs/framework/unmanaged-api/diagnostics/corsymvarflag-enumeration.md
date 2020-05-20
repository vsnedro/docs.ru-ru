---
title: Перечисление CorSymVarFlag
ms.date: 03/30/2017
api_name:
- CorSymVarFlag
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSymVarFlag
helpviewer_keywords:
- CorSymVarFlag enumeration [.NET Framework debugging]
ms.assetid: c3f7d307-4047-4f9a-be8c-f152fca42fd0
topic_type:
- apiref
ms.openlocfilehash: d41e048b67d4bc7159f6dd5266457651f1658290
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420595"
---
# <a name="corsymvarflag-enumeration"></a><span data-ttu-id="42a21-102">Перечисление CorSymVarFlag</span><span class="sxs-lookup"><span data-stu-id="42a21-102">CorSymVarFlag Enumeration</span></span>
<span data-ttu-id="42a21-103">Указывает, создается ли переменная компилятором.</span><span class="sxs-lookup"><span data-stu-id="42a21-103">Indicates whether a variable is compiler-generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42a21-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="42a21-104">Syntax</span></span>  
  
```cpp  
typedef enum CorSymVarFlag
{  
    VAR_IS_COMP_GEN = 1  
} CorSymVarFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="42a21-105">Участники</span><span class="sxs-lookup"><span data-stu-id="42a21-105">Members</span></span>  
  
|<span data-ttu-id="42a21-106">Член</span><span class="sxs-lookup"><span data-stu-id="42a21-106">Member</span></span>|<span data-ttu-id="42a21-107">Описание</span><span class="sxs-lookup"><span data-stu-id="42a21-107">Description</span></span>|  
|------------|-----------------|  
|`VAR_IS_COMP_GEN`|<span data-ttu-id="42a21-108">Указывает, что заданная переменная создается компилятором.</span><span class="sxs-lookup"><span data-stu-id="42a21-108">Indicates that the given variable is compiler-generated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="42a21-109">Требования</span><span class="sxs-lookup"><span data-stu-id="42a21-109">Requirements</span></span>  
 <span data-ttu-id="42a21-110">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="42a21-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42a21-111">См. также статью</span><span class="sxs-lookup"><span data-stu-id="42a21-111">See also</span></span>

- [<span data-ttu-id="42a21-112">Перечисления хранилища символов диагностики</span><span class="sxs-lookup"><span data-stu-id="42a21-112">Diagnostics Symbol Store Enumerations</span></span>](diagnostics-symbol-store-enumerations.md)
