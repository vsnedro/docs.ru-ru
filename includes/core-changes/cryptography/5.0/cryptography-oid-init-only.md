---
ms.openlocfilehash: cf51d5f6b3eee7189fd9613b3d780a829d197a04
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558012"
---
### <a name="systemsecuritycryptographyoid-is-functionally-init-only"></a><span data-ttu-id="6abb8-101">Класс System.Security.Cryptography.Oid функционально доступен только для инициализации</span><span class="sxs-lookup"><span data-stu-id="6abb8-101">System.Security.Cryptography.Oid is functionally init-only</span></span>

<span data-ttu-id="6abb8-102">Класс <xref:System.Security.Cryptography.Oid?displayProperty=fullName>, используемый для представления значений идентификаторов объектов ASN.1 и их понятных имен, был ранее полностью изменяемым.</span><span class="sxs-lookup"><span data-stu-id="6abb8-102">The <xref:System.Security.Cryptography.Oid?displayProperty=fullName> class, which is used to represent ASN.1 Object Identifier values and their "friendly" names, was previously fully mutable.</span></span> <span data-ttu-id="6abb8-103">Эта изменяемость часто игнорировалась или становилась неожиданностью.</span><span class="sxs-lookup"><span data-stu-id="6abb8-103">This mutability was often overlooked or came as a surprise.</span></span> <span data-ttu-id="6abb8-104">Теперь методы задания свойств вызывают <xref:System.PlatformNotSupportedException> при попытке изменить значение после того, как оно уже было назначено.</span><span class="sxs-lookup"><span data-stu-id="6abb8-104">The property setters now throw a <xref:System.PlatformNotSupportedException> when you attempt to change the value after it's already been assigned.</span></span>

#### <a name="change-description"></a><span data-ttu-id="6abb8-105">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="6abb8-105">Change description</span></span>

<span data-ttu-id="6abb8-106">В предыдущих версиях методы задания свойств в <xref:System.Security.Cryptography.Oid> можно было использовать для изменения значений свойств <xref:System.Security.Cryptography.Oid.FriendlyName> и <xref:System.Security.Cryptography.Oid.Value>.</span><span class="sxs-lookup"><span data-stu-id="6abb8-106">In previous versions, the property setters on <xref:System.Security.Cryptography.Oid> can be used to change the value of the <xref:System.Security.Cryptography.Oid.FriendlyName> and <xref:System.Security.Cryptography.Oid.Value> properties.</span></span>

<span data-ttu-id="6abb8-107">В .NET 5.0 и более поздних версиях методы задания свойств можно использовать только для инициализации значения.</span><span class="sxs-lookup"><span data-stu-id="6abb8-107">In .NET 5.0 and later versions, the property setters can only be used to initialize the value.</span></span> <span data-ttu-id="6abb8-108">После того как свойство получило значение из конструктора или предыдущего вызова метода задания свойств, метод задания свойств всегда будет вызывать <xref:System.PlatformNotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="6abb8-108">Once the property has a value, either from a constructor or a previous call to the property setter, the property setter always throws a <xref:System.PlatformNotSupportedException>.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="6abb8-109">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="6abb8-109">Reason for change</span></span>

<span data-ttu-id="6abb8-110">Это изменение позволяет повторно использовать объекты <xref:System.Security.Cryptography.Oid> как часть возвращаемых значений в общедоступных API для уменьшения количества профилей выделения объектов.</span><span class="sxs-lookup"><span data-stu-id="6abb8-110">This change enables the reuse of <xref:System.Security.Cryptography.Oid> objects as part of return values in public APIs to reduce object allocation profiles.</span></span> <span data-ttu-id="6abb8-111">Это позволяет избежать необходимости создавать временные "защитные" копии, когда значения <xref:System.Security.Cryptography.Oid> используются в качестве входных данных.</span><span class="sxs-lookup"><span data-stu-id="6abb8-111">It avoids the need to create temporary "defensive" copies when <xref:System.Security.Cryptography.Oid> values are used as inputs.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="6abb8-112">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="6abb8-112">Version introduced</span></span>

<span data-ttu-id="6abb8-113">5.0, предварительная версия 8</span><span class="sxs-lookup"><span data-stu-id="6abb8-113">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="6abb8-114">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="6abb8-114">Recommended action</span></span>

<span data-ttu-id="6abb8-115">Избегайте использования методов задания свойств <xref:System.Security.Cryptography.Oid>, отличных от инициализации объектов.</span><span class="sxs-lookup"><span data-stu-id="6abb8-115">Avoid using the <xref:System.Security.Cryptography.Oid> property setters other than for object initialization.</span></span> <span data-ttu-id="6abb8-116">Чтобы представить новое значение, используйте новый экземпляр вместо изменения значения существующего объекта.</span><span class="sxs-lookup"><span data-stu-id="6abb8-116">To represent a new value, use a new instance instead of changing the value on an existing object.</span></span>

#### <a name="category"></a><span data-ttu-id="6abb8-117">Категория</span><span class="sxs-lookup"><span data-stu-id="6abb8-117">Category</span></span>

<span data-ttu-id="6abb8-118">Шифрование</span><span class="sxs-lookup"><span data-stu-id="6abb8-118">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6abb8-119">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="6abb8-119">Affected APIs</span></span>

- <xref:System.Security.Cryptography.Oid.FriendlyName?displayProperty=fullName>
- <xref:System.Security.Cryptography.Oid.Value?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Security.Cryptography.Oid.FriendlyName`
- `P:System.Security.Cryptography.Oid.Value`

-->
