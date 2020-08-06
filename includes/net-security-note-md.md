---
ms.openlocfilehash: 8b0edd9a49ca431355ab4f57fa041c5d1756d7eb
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855674"
---
> [!CAUTION]
> <span data-ttu-id="5710b-101">Разграничение доступа кода (CAS) и частично доверенный код</span><span class="sxs-lookup"><span data-stu-id="5710b-101">Code Access Security (CAS) and Partially Trusted Code</span></span>
>
> <span data-ttu-id="5710b-102">Платформа .NET Framework предоставляет механизм для принудительного применения различных уровней доверия к разным частям кода, выполняемым в одном и том же приложении. Этот механизм называется управлением доступом для кода.</span><span class="sxs-lookup"><span data-stu-id="5710b-102">The .NET Framework provides a mechanism for the enforcement of varying levels of trust on different code running in the same application called Code Access Security (CAS).</span></span>
>
> <span data-ttu-id="5710b-103">**CAS не поддерживается в .NET Core, .NET 5 или более поздних версиях. Центры сертификации не поддерживаются версиями C# более поздней версии, чем 7,0.**</span><span class="sxs-lookup"><span data-stu-id="5710b-103">**CAS is not supported in .NET Core, .NET 5, or later versions. CAS is not supported by versions of C# later than 7.0.**</span></span>
>
> <span data-ttu-id="5710b-104">CAS в .NET Framework не следует использовать в качестве механизма для обеспечения границ безопасности на основе происхождения кода или других аспектов идентификации.</span><span class="sxs-lookup"><span data-stu-id="5710b-104">CAS in .NET Framework should not be used as a mechanism for enforcing security boundaries based on code origination or other identity aspects.</span></span> <span data-ttu-id="5710b-105">CAS и прозрачный с точки зрения безопасности код не поддерживаются в качестве границы безопасности с частично доверенным кодом, особенно кода неизвестного происхождения.</span><span class="sxs-lookup"><span data-stu-id="5710b-105">CAS and Security-Transparent Code are not supported as a security boundary with partially trusted code, especially code of unknown origin.</span></span> <span data-ttu-id="5710b-106">Мы не рекомендуем загружать и выполнять код из неизвестных источников, не предприняв дополнительные меры безопасности.</span><span class="sxs-lookup"><span data-stu-id="5710b-106">We advise against loading and executing code of unknown origins without putting alternative security measures in place.</span></span>
>
> <span data-ttu-id="5710b-107">Эта политика действует в отношении всех версий платформы .NET Framework, кроме платформы .NET Framework в составе Silverlight.</span><span class="sxs-lookup"><span data-stu-id="5710b-107">This policy applies to all versions of .NET Framework, but does not apply to the .NET Framework included in Silverlight.</span></span>
