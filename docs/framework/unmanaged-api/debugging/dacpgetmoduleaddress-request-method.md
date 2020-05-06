---
title: Метод DacpGetModuleAddress::Request
ms.date: 01/16/2019
api.name:
- DacpGetModuleAddress::Request Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpGetModuleAddress::Request Method
helpviewer.keywords:
- DacpGetModuleAddress::Request Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 1755526636bed6d78663112e4c2ad5ab7c3f731c
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860839"
---
# <a name="dacpgetmoduleaddressrequest-method"></a><span data-ttu-id="dbed8-102">Метод DacpGetModuleAddress::Request</span><span class="sxs-lookup"><span data-stu-id="dbed8-102">DacpGetModuleAddress::Request Method</span></span>

<span data-ttu-id="dbed8-103">Выполняет запрос на заполнение структуры из заданной структуры среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="dbed8-103">Performs a request to populate the structure from the given runtime structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="dbed8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dbed8-104">Syntax</span></span>

```cpp
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a><span data-ttu-id="dbed8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dbed8-105">Parameters</span></span>

`pDataModule`\
<span data-ttu-id="dbed8-106">окне Указатель на модуль начальных данных.</span><span class="sxs-lookup"><span data-stu-id="dbed8-106">[in] A pointer to the seed data module.</span></span>

## <a name="remarks"></a><span data-ttu-id="dbed8-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="dbed8-107">Remarks</span></span>

<span data-ttu-id="dbed8-108">Эта структура находится внутри среды выполнения и не предоставляется через все файлы заголовков или библиотек.</span><span class="sxs-lookup"><span data-stu-id="dbed8-108">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="dbed8-109">Чтобы использовать его, самый простой способ — имитировать реализацию:</span><span class="sxs-lookup"><span data-stu-id="dbed8-109">To use it, the easiest way is to mimic the implementation:</span></span>

- <span data-ttu-id="dbed8-110">Возвращает значение, полученное от вызова `Request` метода для `IXCLRDataModule*` параметра со следующими параметрами:`((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span><span class="sxs-lookup"><span data-stu-id="dbed8-110">Return the value obtained from calling the `Request` method on the `IXCLRDataModule*` parameter with the following parameters: `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span></span>

## <a name="requirements"></a><span data-ttu-id="dbed8-111">Требования</span><span class="sxs-lookup"><span data-stu-id="dbed8-111">Requirements</span></span>

<span data-ttu-id="dbed8-112">**Платформы:** См. [требования к системе](../../get-started/system-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="dbed8-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md)</span></span>\
<span data-ttu-id="dbed8-113">**Заголовок:** None</span><span class="sxs-lookup"><span data-stu-id="dbed8-113">**Header:** None\</span></span>
<span data-ttu-id="dbed8-114">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="dbed8-114">**Library:** None\</span></span>
<span data-ttu-id="dbed8-115">**.NET Framework версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="dbed8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="dbed8-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="dbed8-116">See also</span></span>

- [<span data-ttu-id="dbed8-117">Отладка</span><span class="sxs-lookup"><span data-stu-id="dbed8-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="dbed8-118">Структура Дакпжетмодулеаддресс</span><span class="sxs-lookup"><span data-stu-id="dbed8-118">DacpGetModuleAddress structure</span></span>](dacpgetmoduleaddress-structure.md)
