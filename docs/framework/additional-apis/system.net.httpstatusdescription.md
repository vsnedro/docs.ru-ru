---
title: Класс Хттпстатусдескриптион (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.HttpStatusDescription
- System.Net.HttpStatusDescription.Get
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 0214d8259c735de11abe204680d619a7298466de
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990514"
---
# <a name="httpstatusdescription-class"></a><span data-ttu-id="ad1db-102">Класс Хттпстатусдескриптион</span><span class="sxs-lookup"><span data-stu-id="ad1db-102">HttpStatusDescription class</span></span>

<span data-ttu-id="ad1db-103">Предоставляет стандартные описания состояния HTTP.</span><span class="sxs-lookup"><span data-stu-id="ad1db-103">Provides standard HTTP status descriptions.</span></span> <span data-ttu-id="ad1db-104">Этот класс не может быть унаследован.</span><span class="sxs-lookup"><span data-stu-id="ad1db-104">This class cannot be inherited.</span></span>

```csharp
internal static class HttpStatusDescription
```

> [!WARNING]
> <span data-ttu-id="ad1db-105">Этот класс является внутренним и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="ad1db-105">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="ad1db-106">Корпорация Майкрософт не поддерживает использование этого класса в рабочем приложении при каких-либо обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="ad1db-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="get-method"></a><span data-ttu-id="ad1db-107">Get - метод</span><span class="sxs-lookup"><span data-stu-id="ad1db-107">Get method</span></span>

<span data-ttu-id="ad1db-108">Возвращает описание, связанное с указанным кодом состояния HTTP.</span><span class="sxs-lookup"><span data-stu-id="ad1db-108">Returns the description associated with the specified HTTP status code.</span></span>

```csharp
internal static string Get(int code)
```

### <a name="parameters"></a><span data-ttu-id="ad1db-109">Параметры</span><span class="sxs-lookup"><span data-stu-id="ad1db-109">Parameters</span></span>

<span data-ttu-id="ad1db-110">`code` <xref:System.Int32></span><span class="sxs-lookup"><span data-stu-id="ad1db-110">`code` <xref:System.Int32></span></span>

<span data-ttu-id="ad1db-111">Код состояния HTTP, например `404` .</span><span class="sxs-lookup"><span data-stu-id="ad1db-111">The HTTP status code, for example, `404`.</span></span>

### <a name="return-value"></a><span data-ttu-id="ad1db-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ad1db-112">Return value</span></span>

<xref:System.String?displayProperty=nameWithType>

<span data-ttu-id="ad1db-113">Описание состояния HTTP.</span><span class="sxs-lookup"><span data-stu-id="ad1db-113">The HTTP status description.</span></span>

## <a name="requirements"></a><span data-ttu-id="ad1db-114">Требования</span><span class="sxs-lookup"><span data-stu-id="ad1db-114">Requirements</span></span>

<span data-ttu-id="ad1db-115">**Пространство имен:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="ad1db-115">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="ad1db-116">**Сборка:** Система (в System.dll)</span><span class="sxs-lookup"><span data-stu-id="ad1db-116">**Assembly:** System (in System.dll)</span></span>
