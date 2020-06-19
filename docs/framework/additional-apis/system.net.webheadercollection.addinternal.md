---
title: Вебхеадерколлектион. Аддинтернал, метод (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.WebHeaderCollection.AddInternal
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: fd7b13ccd1baad48ab99a85d80ccd6154651c608
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990463"
---
# <a name="webheadercollectionaddinternal-method"></a><span data-ttu-id="1da5e-102">Вебхеадерколлектион. Аддинтернал, метод</span><span class="sxs-lookup"><span data-stu-id="1da5e-102">WebHeaderCollection.AddInternal method</span></span>

<span data-ttu-id="1da5e-103">Добавляет новый заголовок с указанным именем и значением в коллекцию, минуя проверки.</span><span class="sxs-lookup"><span data-stu-id="1da5e-103">Adds a new header with the specified name and value to the collection, bypassing checks.</span></span>

```csharp
internal void AddInternal(string name, string value)
```

> [!WARNING]
> <span data-ttu-id="1da5e-104">Этот метод является внутренним и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="1da5e-104">This method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="1da5e-105">Корпорация Майкрософт не поддерживает использование этого метода в рабочем приложении при каких-либо обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="1da5e-105">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="parameters"></a><span data-ttu-id="1da5e-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="1da5e-106">Parameters</span></span>

- <span data-ttu-id="1da5e-107">`name` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="1da5e-107">`name` <xref:System.String></span></span>

  <span data-ttu-id="1da5e-108">Имя заголовка.</span><span class="sxs-lookup"><span data-stu-id="1da5e-108">The name of the header.</span></span>

- <span data-ttu-id="1da5e-109">`value` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="1da5e-109">`value` <xref:System.String></span></span>

  <span data-ttu-id="1da5e-110">Значение заголовка.</span><span class="sxs-lookup"><span data-stu-id="1da5e-110">The value of the header.</span></span>

## <a name="requirements"></a><span data-ttu-id="1da5e-111">Требования</span><span class="sxs-lookup"><span data-stu-id="1da5e-111">Requirements</span></span>

<span data-ttu-id="1da5e-112">**Пространство имен:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="1da5e-112">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="1da5e-113">**Сборка:** Система (в System.dll)</span><span class="sxs-lookup"><span data-stu-id="1da5e-113">**Assembly:** System (in System.dll)</span></span>
