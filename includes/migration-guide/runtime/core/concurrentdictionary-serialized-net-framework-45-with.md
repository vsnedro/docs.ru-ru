---
ms.openlocfilehash: 450bfc56c99a3df9be71be2ef7df6e4e12d4ed76
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496700"
---
### <a name="a-concurrentdictionary-serialized-in-net-framework-45-with-netdatacontractserializer-cannot-be-deserialized-by-net-framework-451-or-452"></a><span data-ttu-id="88685-101">Объект ConcurrentDictionary, сериализованный в .NET Framework 4.5 с помощью NetDataContractSerializer, нельзя десериализовать в .NET Framework 4.5.1 или 4.5.2</span><span class="sxs-lookup"><span data-stu-id="88685-101">A ConcurrentDictionary serialized in .NET Framework 4.5 with NetDataContractSerializer cannot be deserialized by .NET Framework 4.5.1 or 4.5.2</span></span>

#### <a name="details"></a><span data-ttu-id="88685-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="88685-102">Details</span></span>

<span data-ttu-id="88685-103">Из-за внутренних изменений типа объекты <xref:System.Collections.Concurrent.ConcurrentDictionary%602>, сериализованные в .NET Framework 4.5 с помощью <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName>, не могут быть десериализованы в .NET Framework 4.5.1 или .NET Framework 4.5.2. Обратите внимание, что сериализация в .NET Framework 4.5.x с последующей десериализацией в .NET Framework 4.5 будет работать нормально.</span><span class="sxs-lookup"><span data-stu-id="88685-103">Due to internal changes to the type, <xref:System.Collections.Concurrent.ConcurrentDictionary%602> objects that are serialized with the .NET Framework 4.5 using the <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> cannot be deserialized in the .NET Framework 4.5.1 or in the .NET Framework 4.5.2.Note that moving in the other direction (serializing with the .NET Framework 4.5.x and deserializing with the .NET Framework 4.5) works.</span></span> <span data-ttu-id="88685-104">Аналогичным образом, сериализация в версиях 4.x работает в .NET Framework 4.6. Сериализация и десериализация в одной версии платформы .NET Framework не затрагивается.</span><span class="sxs-lookup"><span data-stu-id="88685-104">Similarly, all 4.x cross-version serialization works with the .NET Framework 4.6.Serializing and deserializing with a single version of the .NET Framework is not affected.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="88685-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="88685-105">Suggestion</span></span>

<span data-ttu-id="88685-106">Если требуется выполнить сериализацию и десериализацию объектов <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName> между версиями .NET Framework 4.5 и .NET Framework 4.5.1/4.5.2, следует использовать альтернативный сериализатор, например <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=fullName> или <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName>, вместо <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName>. Кроме того, поскольку эта проблема была устранена в .NET Framework 4.6, она может быть решена путем обновления до этой версии платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="88685-106">If it is necessary to serialize and deserialize a <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName> between the .NET Framework 4.5 and .NET Framework 4.5.1/4.5.2, an alternate serializer like the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=fullName> or <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> serializer should be used instead of the <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName>.Alternatively, because this issue is addressed in the .NET Framework 4.6, it may be solved by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="88685-107">Имя</span><span class="sxs-lookup"><span data-stu-id="88685-107">Name</span></span>    | <span data-ttu-id="88685-108">Значение</span><span class="sxs-lookup"><span data-stu-id="88685-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="88685-109">Область</span><span class="sxs-lookup"><span data-stu-id="88685-109">Scope</span></span>   |<span data-ttu-id="88685-110">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="88685-110">Minor</span></span>|
|<span data-ttu-id="88685-111">Version</span><span class="sxs-lookup"><span data-stu-id="88685-111">Version</span></span>|<span data-ttu-id="88685-112">4.5.1</span><span class="sxs-lookup"><span data-stu-id="88685-112">4.5.1</span></span>|
|<span data-ttu-id="88685-113">Type</span><span class="sxs-lookup"><span data-stu-id="88685-113">Type</span></span>|<span data-ttu-id="88685-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="88685-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="88685-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="88685-115">Affected APIs</span></span>

<span data-ttu-id="88685-116">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="88685-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
