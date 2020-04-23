---
title: DacpGetModuleАдрес::Запрос Метод
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
ms.openlocfilehash: 4dbe6a2c295e5afae1b6761f0c7b695fdb906428
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102911"
---
# <a name="dacpgetmoduleaddressrequest-method"></a><span data-ttu-id="3cdf5-102">DacpGetModuleАдрес::Запрос Метод</span><span class="sxs-lookup"><span data-stu-id="3cdf5-102">DacpGetModuleAddress::Request Method</span></span>

<span data-ttu-id="3cdf5-103">Выполняет запрос на заселяют структуру из заданной структуры времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="3cdf5-103">Performs a request to populate the structure from the given runtime structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="3cdf5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3cdf5-104">Syntax</span></span>

```cpp
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a><span data-ttu-id="3cdf5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3cdf5-105">Parameters</span></span>

`pDataModule`\
<span data-ttu-id="3cdf5-106">(в) Указатель на модуль данных семян.</span><span class="sxs-lookup"><span data-stu-id="3cdf5-106">[in] A pointer to the seed data module.</span></span>

## <a name="remarks"></a><span data-ttu-id="3cdf5-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="3cdf5-107">Remarks</span></span>

<span data-ttu-id="3cdf5-108">Эта структура живет в времени выполнения и не подвергается воздействию каких-либо заголовков или файлов библиотек.</span><span class="sxs-lookup"><span data-stu-id="3cdf5-108">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="3cdf5-109">Проще всего имитировать реализацию:</span><span class="sxs-lookup"><span data-stu-id="3cdf5-109">To use it, the easiest way is to mimic the implementation:</span></span>

- <span data-ttu-id="3cdf5-110">Возврат значения, полученного `Request` от вызова `IXCLRDataModule*` метода по параметру со следующими параметрами:`((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span><span class="sxs-lookup"><span data-stu-id="3cdf5-110">Return the value obtained from calling the `Request` method on the `IXCLRDataModule*` parameter with the following parameters: `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span></span>

## <a name="requirements"></a><span data-ttu-id="3cdf5-111">Требования</span><span class="sxs-lookup"><span data-stu-id="3cdf5-111">Requirements</span></span>

<span data-ttu-id="3cdf5-112">**Платформы:** Посмотреть [системные требования](../../../../docs/framework/get-started/system-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="3cdf5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md)</span></span>\
<span data-ttu-id="3cdf5-113">**Заголовок:** Нет</span><span class="sxs-lookup"><span data-stu-id="3cdf5-113">**Header:** None\</span></span>
<span data-ttu-id="3cdf5-114">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="3cdf5-114">**Library:** None\</span></span>
<span data-ttu-id="3cdf5-115">**Рамочные версии .NET:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3cdf5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="3cdf5-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3cdf5-116">See also</span></span>

- [<span data-ttu-id="3cdf5-117">Отладка</span><span class="sxs-lookup"><span data-stu-id="3cdf5-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="3cdf5-118">DacpGetModuleАдрес структуры</span><span class="sxs-lookup"><span data-stu-id="3cdf5-118">DacpGetModuleAddress structure</span></span>](dacpgetmoduleaddress-structure.md)
