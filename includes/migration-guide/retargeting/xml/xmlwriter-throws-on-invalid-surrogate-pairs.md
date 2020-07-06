---
ms.openlocfilehash: f87b70708398226516ab5eac32c24a9fc2c1106b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615779"
---
### <a name="xmlwriter-throws-on-invalid-surrogate-pairs"></a><span data-ttu-id="14744-101">XmlWriter вызывает недействительные суррогатные пары</span><span class="sxs-lookup"><span data-stu-id="14744-101">XmlWriter throws on invalid surrogate pairs</span></span>

#### <a name="details"></a><span data-ttu-id="14744-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="14744-102">Details</span></span>

<span data-ttu-id="14744-103">Для приложений с целевой платформой .NET Framework 4.5.2 или предыдущих версий запись недействительной суррогатной пары с помощью обработки резервного исключения не всегда вызывает исключение.</span><span class="sxs-lookup"><span data-stu-id="14744-103">For apps that target the .NET Framework 4.5.2 or previous versions, writing an invalid surrogate pair using exception fallback handling does not always throw an exception.</span></span> <span data-ttu-id="14744-104">Для приложений с целевой платформой .NET Framework 4.6 попытка записи недействительной суррогатной пары вызывает исключение <xref:System.ArgumentException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="14744-104">For apps that target the .NET Framework 4.6, attempting to write an invalid surrogate pair throws an <xref:System.ArgumentException?displayProperty=fullName>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="14744-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="14744-105">Suggestion</span></span>

<span data-ttu-id="14744-106">При необходимости этого прерывания можно избежать, выбрав в качестве целевой платформы .NET Framework 4.5.2 или более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="14744-106">If necessary, this break can be avoided by targeting the .NET Framework 4.5.2 or earlier.</span></span> <span data-ttu-id="14744-107">Кроме того, до записи недействительных суррогатных пар можно предварительно обработать их и преобразовать в допустимый xml.</span><span class="sxs-lookup"><span data-stu-id="14744-107">Alternatively, invalid surrogate pairs can be pre-processed into valid xml prior to writing them.</span></span>

| <span data-ttu-id="14744-108">name</span><span class="sxs-lookup"><span data-stu-id="14744-108">Name</span></span>    | <span data-ttu-id="14744-109">Значение</span><span class="sxs-lookup"><span data-stu-id="14744-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="14744-110">Область</span><span class="sxs-lookup"><span data-stu-id="14744-110">Scope</span></span>   | <span data-ttu-id="14744-111">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="14744-111">Edge</span></span>        |
| <span data-ttu-id="14744-112">Version</span><span class="sxs-lookup"><span data-stu-id="14744-112">Version</span></span> | <span data-ttu-id="14744-113">4.6</span><span class="sxs-lookup"><span data-stu-id="14744-113">4.6</span></span>         |
| <span data-ttu-id="14744-114">Type</span><span class="sxs-lookup"><span data-stu-id="14744-114">Type</span></span>    | <span data-ttu-id="14744-115">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="14744-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="14744-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="14744-116">Affected APIs</span></span>

- <xref:System.Xml.XmlWriter.WriteAttributeString(System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteAttributeString(System.String,System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteAttributeString(System.String,System.String,System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteAttributeStringAsync(System.String,System.String,System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteCData(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteCDataAsync(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteChars(System.Char[],System.Int32,System.Int32)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteCharsAsync(System.Char[],System.Int32,System.Int32)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteComment(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteCommentAsync(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteEntityRef(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteEntityRefAsync(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteRaw(System.Char[],System.Int32,System.Int32)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteProcessingInstruction(System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteProcessingInstructionAsync(System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteRaw(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteRawAsync(System.Char[],System.Int32,System.Int32)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteRawAsync(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteString(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteStringAsync(System.String)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteSurrogateCharEntity(System.Char,System.Char)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteSurrogateCharEntityAsync(System.Char,System.Char)?displayProperty=nameWithType>
- <xref:System.Xml.XmlWriter.WriteValue(System.String)?displayProperty=nameWithType>
