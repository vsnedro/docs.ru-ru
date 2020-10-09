---
title: Критические изменения во взаимодействии
description: Предоставляет перечень критических изменений во взаимодействии между .NET Core и .NET 5.0 и более поздних версий.
ms.date: 06/23/2020
ms.openlocfilehash: a38fb1837e565be33f8ae1119480c8f1ae848ab0
ms.sourcegitcommit: b4a46f6d7ebf44c0035627d00924164bcae2db30
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91438040"
---
# <a name="interop-breaking-changes"></a><span data-ttu-id="fb010-103">Критические изменения во взаимодействии</span><span class="sxs-lookup"><span data-stu-id="fb010-103">Interop breaking changes</span></span>

<span data-ttu-id="fb010-104">На этой странице описаны следующие критические изменения:</span><span class="sxs-lookup"><span data-stu-id="fb010-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="fb010-105">Критическое изменение</span><span class="sxs-lookup"><span data-stu-id="fb010-105">Breaking change</span></span> | <span data-ttu-id="fb010-106">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="fb010-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="fb010-107">Приведение вызываемой оболочки времени выполнения к интерфейсу `InterfaceIsIInspectable` вызывает исключение PlatformNotSupportedException</span><span class="sxs-lookup"><span data-stu-id="fb010-107">Casting RCW to an `InterfaceIsIInspectable` interface throws PlatformNotSupportedException</span></span>](#casting-rcw-to-an-interfaceisiinspectable-interface-throws-platformnotsupportedexception) | <span data-ttu-id="fb010-108">5.0</span><span class="sxs-lookup"><span data-stu-id="fb010-108">5.0</span></span> |
| [<span data-ttu-id="fb010-109">Отсутствует проверка суффикса A/W на платформах, отличных от Windows</span><span class="sxs-lookup"><span data-stu-id="fb010-109">No A/W suffix probing on non-Windows platforms</span></span>](#no-aw-suffix-probing-on-non-windows-platforms) | <span data-ttu-id="fb010-110">5.0</span><span class="sxs-lookup"><span data-stu-id="fb010-110">5.0</span></span> |
| [<span data-ttu-id="fb010-111">Из .NET удалена встроенная поддержка WinRT</span><span class="sxs-lookup"><span data-stu-id="fb010-111">Built-in support for WinRT is removed from .NET</span></span>](#built-in-support-for-winrt-is-removed-from-net) | <span data-ttu-id="fb010-112">5.0</span><span class="sxs-lookup"><span data-stu-id="fb010-112">5.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="fb010-113">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="fb010-113">.NET 5.0</span></span>

[!INCLUDE [casting-rcw-to-inspectable-interface-throws-exception](../../../includes/core-changes/interop/5.0/casting-rcw-to-inspectable-interface-throws-exception.md)]

***

[!INCLUDE [function-suffix-pinvoke](../../../includes/core-changes/interop/5.0/function-suffix-pinvoke.md)]

***

[!INCLUDE [built-in-support-for-winrt-removed](~/includes/core-changes/interop/5.0/built-in-support-for-winrt-removed.md)]

***
