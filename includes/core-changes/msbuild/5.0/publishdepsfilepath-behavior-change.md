---
ms.openlocfilehash: 077eadb05ab16f5cec8817b89bc771de0c94aefa
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679338"
---
### <a name="publishdepsfilepath-behavior-change"></a><span data-ttu-id="87a91-101">Изменение поведения PublishDepsFilePath</span><span class="sxs-lookup"><span data-stu-id="87a91-101">PublishDepsFilePath behavior change</span></span>

<span data-ttu-id="87a91-102">Свойство MSBuild `PublishDepsFilePath` пусто для однофайловых приложений.</span><span class="sxs-lookup"><span data-stu-id="87a91-102">The `PublishDepsFilePath` MSBuild property is empty for single-file applications.</span></span> <span data-ttu-id="87a91-103">Кроме того, для приложений с несколькими файлами файл *deps.json* может быть скопирован в выходной каталог только на более поздних этапах сборки.</span><span class="sxs-lookup"><span data-stu-id="87a91-103">Additionally, for non single-file applications, the *deps.json* file may not be copied to the output directory until later in the build.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="87a91-104">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="87a91-104">Version introduced</span></span>

<span data-ttu-id="87a91-105">5.0</span><span class="sxs-lookup"><span data-stu-id="87a91-105">5.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="87a91-106">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="87a91-106">Change description</span></span>

<span data-ttu-id="87a91-107">В предыдущих версиях .NET свойство MSBuild `PublishDepsFilePath` является путем к файлу *deps.json* приложения в выходном каталоге для приложений с несколькими файлами и путем в промежуточном каталоге для однофайловых приложений.</span><span class="sxs-lookup"><span data-stu-id="87a91-107">In previous .NET versions, the `PublishDepsFilePath` MSBuild property is the path to the app's *deps.json* file in the output directory for non single-file applications, and a path in the intermediate directory for single-file apps.</span></span>

<span data-ttu-id="87a91-108">Начиная с .NET 5.0 свойство `PublishDepsFilePath` пусто для однофайловых приложений, а новое свойство `IntermediateDepsFilePath` указывает расположение файла *deps.json* в промежуточном каталоге.</span><span class="sxs-lookup"><span data-stu-id="87a91-108">Starting in .NET 5.0, `PublishDepsFilePath` is empty for single-file applications and a new `IntermediateDepsFilePath` property specifies the *deps.json* location in the intermediate directory.</span></span> <span data-ttu-id="87a91-109">Кроме того, для приложений с несколькими файлами файл *deps.json* может быть скопирован в выходной каталог (т. е. по пути, указанному в `PublishDepsFilePath`) только на более поздних этапах сборки.</span><span class="sxs-lookup"><span data-stu-id="87a91-109">Additionally, for non single-file applications, the *deps.json* file may not be copied to the output directory (that is, the path specified by `PublishDepsFilePath`) until later in the build.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="87a91-110">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="87a91-110">Reason for change</span></span>

<span data-ttu-id="87a91-111">Это изменение было внесено по нескольким причинам.</span><span class="sxs-lookup"><span data-stu-id="87a91-111">This change was made for a couple of reasons:</span></span>

- <span data-ttu-id="87a91-112">Из-за рефакторинга логики публикации для поддержки [улучшенных однофайловых приложений](https://github.com/dotnet/designs/blob/master/accepted/2020/single-file/design.md) в .NET 5.</span><span class="sxs-lookup"><span data-stu-id="87a91-112">Due to a refactoring of the publish logic in order to support [improved single-file apps](https://github.com/dotnet/designs/blob/master/accepted/2020/single-file/design.md) in .NET 5.</span></span>

- <span data-ttu-id="87a91-113">Для защиты однофайловых приложений от целевых объектов, которые пытаются перезаписать файл *deps.json* уже после его объединения в пакет, без влияния на приложение.</span><span class="sxs-lookup"><span data-stu-id="87a91-113">In single-file apps, to help guard against targets that try to rewrite the *deps.json* file after *deps.json* has already been bundled, thus silently not affecting the app.</span></span> <span data-ttu-id="87a91-114">Поэтому свойство MSBuild `PublishDepsFilePath` пусто для однофайловых приложений.</span><span class="sxs-lookup"><span data-stu-id="87a91-114">For this reason, `PublishDepsFilePath` is empty for single-file applications.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="87a91-115">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="87a91-115">Recommended action</span></span>

<span data-ttu-id="87a91-116">Целевые объекты, которые перезаписывают файл *deps.json*, обычно используют для этого свойство `IntermediateDepsFilePath`.</span><span class="sxs-lookup"><span data-stu-id="87a91-116">Targets that rewrite the *deps.json* file should generally do so using the `IntermediateDepsFilePath` property.</span></span>

#### <a name="category"></a><span data-ttu-id="87a91-117">Категория</span><span class="sxs-lookup"><span data-stu-id="87a91-117">Category</span></span>

<span data-ttu-id="87a91-118">MSBuild</span><span class="sxs-lookup"><span data-stu-id="87a91-118">MSBuild</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="87a91-119">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="87a91-119">Affected APIs</span></span>

<span data-ttu-id="87a91-120">Н/Д</span><span class="sxs-lookup"><span data-stu-id="87a91-120">N/A</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
