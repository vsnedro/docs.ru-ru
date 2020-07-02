---
ms.openlocfilehash: 598df2121b480d411dac9c5571772a4a8d22b5ff
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620636"
---
### <a name="mef-catalogs-implement-ienumerable-and-therefore-can-no-longer-be-used-to-create-a-serializer"></a><span data-ttu-id="49fa4-101">Каталоги MEF реализуют IEnumerable и поэтому больше не могут использоваться для создания сериализатора</span><span class="sxs-lookup"><span data-stu-id="49fa4-101">MEF catalogs implement IEnumerable and therefore can no longer be used to create a serializer</span></span>

#### <a name="details"></a><span data-ttu-id="49fa4-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="49fa4-102">Details</span></span>

<span data-ttu-id="49fa4-103">Начиная с .NET Framework 4.5 каталоги MEF реализуют IEnumerable и поэтому больше не могут использоваться для создания сериализатора (объекта <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName>).</span><span class="sxs-lookup"><span data-stu-id="49fa4-103">Starting with the .NET Framework 4.5, MEF catalogs implement IEnumerable and therefore can no longer be used to create a serializer (<xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> object).</span></span> <span data-ttu-id="49fa4-104">При попытке сериализации каталога MEF происходит вызов исключения.</span><span class="sxs-lookup"><span data-stu-id="49fa4-104">Trying to serialize a MEF catalog throws an exception.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="49fa4-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="49fa4-105">Suggestion</span></span>

<span data-ttu-id="49fa4-106">Больше не следует использовать MEF для создания сериализатора.</span><span class="sxs-lookup"><span data-stu-id="49fa4-106">Can no longer use MEF to create a serializer</span></span>

| <span data-ttu-id="49fa4-107">name</span><span class="sxs-lookup"><span data-stu-id="49fa4-107">Name</span></span>    | <span data-ttu-id="49fa4-108">Значение</span><span class="sxs-lookup"><span data-stu-id="49fa4-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="49fa4-109">Область</span><span class="sxs-lookup"><span data-stu-id="49fa4-109">Scope</span></span>   |<span data-ttu-id="49fa4-110">Значительно</span><span class="sxs-lookup"><span data-stu-id="49fa4-110">Major</span></span>|
|<span data-ttu-id="49fa4-111">Version</span><span class="sxs-lookup"><span data-stu-id="49fa4-111">Version</span></span>|<span data-ttu-id="49fa4-112">4.5</span><span class="sxs-lookup"><span data-stu-id="49fa4-112">4.5</span></span>|
|<span data-ttu-id="49fa4-113">Type</span><span class="sxs-lookup"><span data-stu-id="49fa4-113">Type</span></span>|<span data-ttu-id="49fa4-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="49fa4-114">Runtime</span></span>|
