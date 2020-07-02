---
ms.openlocfilehash: 4a65e721e5639f12445a9a44f46baa0d26898a88
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615754"
---
### <a name="il-ret-not-allowed-in-a-try-region"></a><span data-ttu-id="b1f85-101">Инструкция IL ret недопустима в области try</span><span class="sxs-lookup"><span data-stu-id="b1f85-101">IL ret not allowed in a try region</span></span>

#### <a name="details"></a><span data-ttu-id="b1f85-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="b1f85-102">Details</span></span>

<span data-ttu-id="b1f85-103">В отличие от JIT-компилятора JIT64, компилятор RyuJIT (в .NET Framework 4.6) не разрешает инструкцию IL ret в области try.</span><span class="sxs-lookup"><span data-stu-id="b1f85-103">Unlike the JIT64 just-in-time compiler, RyuJIT (used in .NET Framework 4.6) does not allow an IL ret instruction in a try region.</span></span> <span data-ttu-id="b1f85-104">Возврат из области try запрещен в спецификации ECMA-335, и ни один известный управляемый компилятор не создает такие IL.</span><span class="sxs-lookup"><span data-stu-id="b1f85-104">Returning from a try region is disallowed by the ECMA-335 specification, and no known managed compiler generates such IL.</span></span> <span data-ttu-id="b1f85-105">Однако компилятор JIT64 выполнит такие IL, если они созданы с помощью порождения отражения.</span><span class="sxs-lookup"><span data-stu-id="b1f85-105">However, the JIT64 compiler will execute such IL if it is generated using reflection emit.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b1f85-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="b1f85-106">Suggestion</span></span>

<span data-ttu-id="b1f85-107">Если приложение создает IL, который включает в себя код операции ret в области try, это приложение можно нацелить на платформу .NET Framework 4.5, чтобы использовать старый JIT-компилятор и избежать этой проблемы.</span><span class="sxs-lookup"><span data-stu-id="b1f85-107">If an app is generating IL that includes a ret opcode in a try region, the app may target .NET Framework 4.5 to use the old JIT and avoid this break.</span></span> <span data-ttu-id="b1f85-108">Кроме того, создаваемый IL-код можно обновить, чтобы он возвращался после области try.</span><span class="sxs-lookup"><span data-stu-id="b1f85-108">Alternatively, the generated IL may be updated to return after the try region.</span></span>

| <span data-ttu-id="b1f85-109">name</span><span class="sxs-lookup"><span data-stu-id="b1f85-109">Name</span></span>    | <span data-ttu-id="b1f85-110">Значение</span><span class="sxs-lookup"><span data-stu-id="b1f85-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b1f85-111">Область</span><span class="sxs-lookup"><span data-stu-id="b1f85-111">Scope</span></span>   | <span data-ttu-id="b1f85-112">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="b1f85-112">Edge</span></span>        |
| <span data-ttu-id="b1f85-113">Version</span><span class="sxs-lookup"><span data-stu-id="b1f85-113">Version</span></span> | <span data-ttu-id="b1f85-114">4.6</span><span class="sxs-lookup"><span data-stu-id="b1f85-114">4.6</span></span>         |
| <span data-ttu-id="b1f85-115">Type</span><span class="sxs-lookup"><span data-stu-id="b1f85-115">Type</span></span>    | <span data-ttu-id="b1f85-116">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="b1f85-116">Retargeting</span></span> |
