---
ms.openlocfilehash: 4ad7c4c2781480c08ad4cf27e40de445b1c50671
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617300"
---
### <a name="encoderparameter-ctor-is-obsolete"></a><span data-ttu-id="5db39-101">Конструктор EncoderParameter устарел</span><span class="sxs-lookup"><span data-stu-id="5db39-101">EncoderParameter ctor is obsolete</span></span>

#### <a name="details"></a><span data-ttu-id="5db39-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="5db39-102">Details</span></span>

<span data-ttu-id="5db39-103">Конструктор <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)> устарел. При его использовании будут выводиться предупреждения сборки.</span><span class="sxs-lookup"><span data-stu-id="5db39-103">The <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)> constructor is obsolete now and will introduce build warnings if used.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="5db39-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="5db39-104">Suggestion</span></span>

<span data-ttu-id="5db39-105">Несмотря на то, что конструктор <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)> будет продолжать работать, во избежание вывода устаревшего предупреждения сборки при повторной компиляции кода с помощью средств .NET Framework 4.5 нужен следующий конструктор: <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Drawing.Imaging.EncoderParameterValueType,System.IntPtr)>.</span><span class="sxs-lookup"><span data-stu-id="5db39-105">Although the <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)>constructor will continue to work, the following constructor should be used instead to avoid the obsolete build warning when re-compiling code with .NET Framework  4.5 tools: <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Drawing.Imaging.EncoderParameterValueType,System.IntPtr)>.</span></span>

| <span data-ttu-id="5db39-106">name</span><span class="sxs-lookup"><span data-stu-id="5db39-106">Name</span></span>    | <span data-ttu-id="5db39-107">Значение</span><span class="sxs-lookup"><span data-stu-id="5db39-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="5db39-108">Область</span><span class="sxs-lookup"><span data-stu-id="5db39-108">Scope</span></span>   | <span data-ttu-id="5db39-109">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="5db39-109">Minor</span></span>       |
| <span data-ttu-id="5db39-110">Version</span><span class="sxs-lookup"><span data-stu-id="5db39-110">Version</span></span> | <span data-ttu-id="5db39-111">4.5</span><span class="sxs-lookup"><span data-stu-id="5db39-111">4.5</span></span>         |
| <span data-ttu-id="5db39-112">Type</span><span class="sxs-lookup"><span data-stu-id="5db39-112">Type</span></span>    | <span data-ttu-id="5db39-113">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="5db39-113">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="5db39-114">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="5db39-114">Affected APIs</span></span>

- <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)>
