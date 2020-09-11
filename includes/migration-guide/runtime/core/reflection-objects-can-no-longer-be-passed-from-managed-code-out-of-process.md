---
ms.openlocfilehash: f011f6ebe0fa85a59f3e69c93bba9eddc4c1689b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496765"
---
### <a name="reflection-objects-can-no-longer-be-passed-from-managed-code-to-out-of-process-dcom-clients"></a><span data-ttu-id="2ef7f-101">Объекты отражения больше невозможно передавать из управляемого кода во внепроцессные клиенты DCOM</span><span class="sxs-lookup"><span data-stu-id="2ef7f-101">Reflection objects can no longer be passed from managed code to out-of-process DCOM clients</span></span>

#### <a name="details"></a><span data-ttu-id="2ef7f-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="2ef7f-102">Details</span></span>

<span data-ttu-id="2ef7f-103">Объекты отражения больше невозможно передавать из управляемого кода во внепроцессные клиенты DCOM.</span><span class="sxs-lookup"><span data-stu-id="2ef7f-103">Reflection objects can no longer be passed from managed code to out-of-process DCOM clients.</span></span> <span data-ttu-id="2ef7f-104">Затронуты следующие типы:</span><span class="sxs-lookup"><span data-stu-id="2ef7f-104">The following types are affected:</span></span>

- <xref:System.Reflection.Assembly?displayProperty=fullName>
- <span data-ttu-id="2ef7f-105"><xref:System.Reflection.MemberInfo?displayProperty=fullName> (и его производные типы, включая <xref:System.Reflection.FieldInfo?displayProperty=fullName>, <xref:System.Reflection.MethodInfo?displayProperty=fullName>, <xref:System.Type?displayProperty=fullName> и <xref:System.Reflection.TypeInfo?displayProperty=fullName>)</span><span class="sxs-lookup"><span data-stu-id="2ef7f-105"><xref:System.Reflection.MemberInfo?displayProperty=fullName> (and its derived types, including <xref:System.Reflection.FieldInfo?displayProperty=fullName>, <xref:System.Reflection.MethodInfo?displayProperty=fullName>, <xref:System.Type?displayProperty=fullName>, and <xref:System.Reflection.TypeInfo?displayProperty=fullName>)</span></span>
- <xref:System.Reflection.MethodBody?displayProperty=fullName>
- <xref:System.Reflection.Module?displayProperty=fullName>
- <xref:System.Reflection.ParameterInfo?displayProperty=fullName>

<span data-ttu-id="2ef7f-106">Вызовы <code>IMarshal</code> объекта возвращают <code>E_NOINTERFACE</code>.</span><span class="sxs-lookup"><span data-stu-id="2ef7f-106">Calls to <code>IMarshal</code> for the object return <code>E_NOINTERFACE</code>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2ef7f-107">Предложение</span><span class="sxs-lookup"><span data-stu-id="2ef7f-107">Suggestion</span></span>

<span data-ttu-id="2ef7f-108">Обновите код маршалинга для работы с объектами без отражения.</span><span class="sxs-lookup"><span data-stu-id="2ef7f-108">Update marshaling code to work with non-reflection objects.</span></span>

| <span data-ttu-id="2ef7f-109">Имя</span><span class="sxs-lookup"><span data-stu-id="2ef7f-109">Name</span></span>    | <span data-ttu-id="2ef7f-110">Значение</span><span class="sxs-lookup"><span data-stu-id="2ef7f-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2ef7f-111">Область</span><span class="sxs-lookup"><span data-stu-id="2ef7f-111">Scope</span></span>   |<span data-ttu-id="2ef7f-112">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="2ef7f-112">Minor</span></span>|
|<span data-ttu-id="2ef7f-113">Version</span><span class="sxs-lookup"><span data-stu-id="2ef7f-113">Version</span></span>|<span data-ttu-id="2ef7f-114">4.6</span><span class="sxs-lookup"><span data-stu-id="2ef7f-114">4.6</span></span>|
|<span data-ttu-id="2ef7f-115">Type</span><span class="sxs-lookup"><span data-stu-id="2ef7f-115">Type</span></span>|<span data-ttu-id="2ef7f-116">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="2ef7f-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="2ef7f-117">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="2ef7f-117">Affected APIs</span></span>

- <xref:System.Reflection.Assembly?displayProperty=fullName>
- <xref:System.Reflection.FieldInfo?displayProperty=fullName>
- <xref:System.Reflection.MemberInfo?displayProperty=fullName>
- <xref:System.Reflection.MethodBody?displayProperty=fullName>
- <xref:System.Reflection.MethodInfo?displayProperty=fullName>
- <xref:System.Reflection.Module?displayProperty=fullName>
- <xref:System.Reflection.ParameterInfo?displayProperty=fullName>
- <xref:System.Reflection.TypeInfo?displayProperty=fullName>
- <xref:System.Type?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Reflection.Assembly`
- `T:System.Reflection.FieldInfo`
- `T:System.Reflection.MemberInfo`
- `T:System.Reflection.MethodBody`
- `T:System.Reflection.MethodInfo`
- `T:System.Reflection.Module`
- `T:System.Reflection.ParameterInfo`
- `T:System.Reflection.TypeInfo`
- `T:System.Type`

-->
