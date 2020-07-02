---
ms.openlocfilehash: a54b17b2002bd0f85b8b47c5e37e040470d6c494
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621433"
---
### <a name="reflection-objects-can-no-longer-be-passed-from-managed-code-to-out-of-process-dcom-clients"></a><span data-ttu-id="36c7d-101">Объекты отражения больше невозможно передавать из управляемого кода во внепроцессные клиенты DCOM</span><span class="sxs-lookup"><span data-stu-id="36c7d-101">Reflection objects can no longer be passed from managed code to out-of-process DCOM clients</span></span>

#### <a name="details"></a><span data-ttu-id="36c7d-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="36c7d-102">Details</span></span>

<span data-ttu-id="36c7d-103">Объекты отражения больше невозможно передавать из управляемого кода во внепроцессные клиенты DCOM.</span><span class="sxs-lookup"><span data-stu-id="36c7d-103">Reflection objects can no longer be passed from managed code to out-of-process DCOM clients.</span></span> <span data-ttu-id="36c7d-104">Затронуты следующие типы:</span><span class="sxs-lookup"><span data-stu-id="36c7d-104">The following types are affected:</span></span><ul><li><xref:System.Reflection.Assembly?displayProperty=fullName></li><li><span data-ttu-id="36c7d-105"><xref:System.Reflection.MemberInfo?displayProperty=fullName> (и его производные типы, включая <xref:System.Reflection.FieldInfo?displayProperty=fullName>, <xref:System.Reflection.MethodInfo?displayProperty=fullName>, <xref:System.Type?displayProperty=fullName> и <xref:System.Reflection.TypeInfo?displayProperty=fullName>)</span><span class="sxs-lookup"><span data-stu-id="36c7d-105"><xref:System.Reflection.MemberInfo?displayProperty=fullName> (and its derived types, including <xref:System.Reflection.FieldInfo?displayProperty=fullName>, <xref:System.Reflection.MethodInfo?displayProperty=fullName>, <xref:System.Type?displayProperty=fullName>, and <xref:System.Reflection.TypeInfo?displayProperty=fullName>)</span></span></li><li><xref:System.Reflection.MethodBody?displayProperty=fullName></li><li><xref:System.Reflection.Module?displayProperty=fullName></li><li><span data-ttu-id="36c7d-106"><xref:System.Reflection.ParameterInfo?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="36c7d-106"><xref:System.Reflection.ParameterInfo?displayProperty=fullName>.</span></span></li></ul><span data-ttu-id="36c7d-107">Вызовы <code>IMarshal</code> объекта возвращают <code>E_NOINTERFACE</code>.</span><span class="sxs-lookup"><span data-stu-id="36c7d-107">Calls to <code>IMarshal</code> for the object return <code>E_NOINTERFACE</code>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="36c7d-108">Предложение</span><span class="sxs-lookup"><span data-stu-id="36c7d-108">Suggestion</span></span>

<span data-ttu-id="36c7d-109">Обновите код маршалинга для работы с объектами без отражения</span><span class="sxs-lookup"><span data-stu-id="36c7d-109">Update marshaling code to work with non-reflection objects</span></span>

| <span data-ttu-id="36c7d-110">name</span><span class="sxs-lookup"><span data-stu-id="36c7d-110">Name</span></span>    | <span data-ttu-id="36c7d-111">Значение</span><span class="sxs-lookup"><span data-stu-id="36c7d-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="36c7d-112">Область</span><span class="sxs-lookup"><span data-stu-id="36c7d-112">Scope</span></span>   |<span data-ttu-id="36c7d-113">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="36c7d-113">Minor</span></span>|
|<span data-ttu-id="36c7d-114">Version</span><span class="sxs-lookup"><span data-stu-id="36c7d-114">Version</span></span>|<span data-ttu-id="36c7d-115">4.6</span><span class="sxs-lookup"><span data-stu-id="36c7d-115">4.6</span></span>|
|<span data-ttu-id="36c7d-116">Type</span><span class="sxs-lookup"><span data-stu-id="36c7d-116">Type</span></span>|<span data-ttu-id="36c7d-117">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="36c7d-117">Runtime</span></span>|
