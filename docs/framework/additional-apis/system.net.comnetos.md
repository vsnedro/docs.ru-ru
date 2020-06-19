---
title: Класс Комнетос (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.ComNetOS
- System.Net.ComNetOS.IsWin7orLater
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: ed2b970d07df2c338870b386e75c1688703f1d68
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990521"
---
# <a name="comnetos-class"></a><span data-ttu-id="65c30-102">Класс Комнетос</span><span class="sxs-lookup"><span data-stu-id="65c30-102">ComNetOS class</span></span>

<span data-ttu-id="65c30-103">Предоставляет сведения о текущей операционной системе, такие как версия и тип установки (клиент или сервер).</span><span class="sxs-lookup"><span data-stu-id="65c30-103">Provides information about the current operating system, such as its version and installation type (client or server).</span></span> <span data-ttu-id="65c30-104">Этот класс не может быть унаследован.</span><span class="sxs-lookup"><span data-stu-id="65c30-104">This class cannot be inherited.</span></span>
  
```csharp  
internal static class ComNetOS
```

> [!WARNING]
> <span data-ttu-id="65c30-105">Этот класс является внутренним и не предназначен для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="65c30-105">This class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="65c30-106">Корпорация Майкрософт не поддерживает использование этого класса в рабочем приложении при каких-либо обстоятельствах.</span><span class="sxs-lookup"><span data-stu-id="65c30-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="iswin7orlater-field"></a><span data-ttu-id="65c30-107">Поле IsWin7orLater</span><span class="sxs-lookup"><span data-stu-id="65c30-107">IsWin7orLater field</span></span>

<span data-ttu-id="65c30-108">Указывает, является ли версия операционной системы Windows 7 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="65c30-108">Specifies whether the operating system version is Windows 7 or later.</span></span>

```csharp
internal static readonly bool IsWin7orLater
```

## <a name="requirements"></a><span data-ttu-id="65c30-109">Требования</span><span class="sxs-lookup"><span data-stu-id="65c30-109">Requirements</span></span>

<span data-ttu-id="65c30-110">**Пространство имен:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="65c30-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="65c30-111">**Сборка:** Система (в System.dll)</span><span class="sxs-lookup"><span data-stu-id="65c30-111">**Assembly:** System (in System.dll)</span></span>
