---
ms.openlocfilehash: 0d6847b7a937094f36efae70ae450cc37824221d
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2020
ms.locfileid: "91955565"
---
### <a name="assembly-related-api-behavior-changes-for-single-file-publishing-format"></a><span data-ttu-id="38699-101">Изменения в поведении API, связанные со сборкой, для формата публикации с одним файлом</span><span class="sxs-lookup"><span data-stu-id="38699-101">Assembly-related API behavior changes for single-file publishing format</span></span>

<span data-ttu-id="38699-102">Изменилось поведение нескольких интерфейсов API, связанных с расположением файла сборки, когда они вызываются в формате публикации с одним файлом.</span><span class="sxs-lookup"><span data-stu-id="38699-102">Multiple APIs related to an assembly's file location have behavior changes when they're invoked in a single-file publishing format.</span></span>

#### <a name="change-description"></a><span data-ttu-id="38699-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="38699-103">Change description</span></span>

<span data-ttu-id="38699-104">В публикации с одним файлом для .NET 5.0 и более поздних версий упакованные сборки загружаются из памяти, а не извлекаются на диск.</span><span class="sxs-lookup"><span data-stu-id="38699-104">In single-file publishing for .NET 5.0 and later versions, bundled assemblies are loaded from memory instead of extracted to disk.</span></span> <span data-ttu-id="38699-105">Для приложений, опубликованных в одном файле, это означает, что определенные интерфейсы API, связанные с расположением, возвращают в .NET 5.0 и более поздних версиях другие значения по сравнению с предыдущими версиями .NET.</span><span class="sxs-lookup"><span data-stu-id="38699-105">For single-file published apps, this means that certain location-related APIs return different values on .NET 5.0 and later than on previous versions of .NET.</span></span> <span data-ttu-id="38699-106">Изменения заключается в следующем.</span><span class="sxs-lookup"><span data-stu-id="38699-106">The changes are as follows:</span></span>

| <span data-ttu-id="38699-107">API</span><span class="sxs-lookup"><span data-stu-id="38699-107">API</span></span> | <span data-ttu-id="38699-108">предыдущих версий</span><span class="sxs-lookup"><span data-stu-id="38699-108">Previous versions</span></span> | <span data-ttu-id="38699-109">.NET 5.0 и более поздней версии</span><span class="sxs-lookup"><span data-stu-id="38699-109">.NET 5.0 and later</span></span> |
| - | - | - |
| <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> | <span data-ttu-id="38699-110">Возвращает путь к извлеченному файлу DLL</span><span class="sxs-lookup"><span data-stu-id="38699-110">Returns extracted DLL file path</span></span> | <span data-ttu-id="38699-111">Возвращает пустую строку для упакованных сборок</span><span class="sxs-lookup"><span data-stu-id="38699-111">Returns empty string for bundled assemblies</span></span> |
| <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType> | <span data-ttu-id="38699-112">Возвращает путь к извлеченному файлу DLL</span><span class="sxs-lookup"><span data-stu-id="38699-112">Returns extracted DLL file path</span></span> | <span data-ttu-id="38699-113">Вызывает исключение для упакованных сборок</span><span class="sxs-lookup"><span data-stu-id="38699-113">Throws exception for bundled assemblies</span></span> |
| <xref:System.Reflection.Assembly.GetFile(System.String)?displayProperty=nameWithType> | <span data-ttu-id="38699-114">Возвращает `null` для упакованных сборок</span><span class="sxs-lookup"><span data-stu-id="38699-114">Returns `null` for bundled assemblies</span></span> | <span data-ttu-id="38699-115">Вызывает исключение для упакованных сборок</span><span class="sxs-lookup"><span data-stu-id="38699-115">Throws exception for bundled assemblies</span></span> |
| `Environment.GetCommandLineArgs()[0]` | <span data-ttu-id="38699-116">Значением является имя точки входа библиотеки DLL</span><span class="sxs-lookup"><span data-stu-id="38699-116">Value is the name of the entry point DLL</span></span> | <span data-ttu-id="38699-117">Значением является имя исполняемого файла узла</span><span class="sxs-lookup"><span data-stu-id="38699-117">Value is the name of the host executable</span></span> |
| <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> | <span data-ttu-id="38699-118">Значением является временный каталог извлечения</span><span class="sxs-lookup"><span data-stu-id="38699-118">Value is the temporary extraction directory</span></span> | <span data-ttu-id="38699-119">Значением является каталог, содержащий исполняемый файл узла</span><span class="sxs-lookup"><span data-stu-id="38699-119">Value is the containing directory of the host executable</span></span> |

#### <a name="version-introduced"></a><span data-ttu-id="38699-120">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="38699-120">Version introduced</span></span>

<span data-ttu-id="38699-121">5.0</span><span class="sxs-lookup"><span data-stu-id="38699-121">5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="38699-122">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="38699-122">Recommended action</span></span>

<span data-ttu-id="38699-123">Избегайте зависимостей от расположения файлов сборок при публикации в виде одного файла.</span><span class="sxs-lookup"><span data-stu-id="38699-123">Avoid dependencies on the file location of assemblies when publishing as a single file.</span></span>

#### <a name="category"></a><span data-ttu-id="38699-124">Категория</span><span class="sxs-lookup"><span data-stu-id="38699-124">Category</span></span>

- <span data-ttu-id="38699-125">Библиотеки Core .NET</span><span class="sxs-lookup"><span data-stu-id="38699-125">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="38699-126">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="38699-126">Affected APIs</span></span>

- <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.GetFile(System.String)?displayProperty=nameWithType>
- <xref:System.Environment.GetCommandLineArgs?displayProperty=nameWithType>
- <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Reflection.Assembly.Location`
- `P:System.Reflection.Assembly.CodeBase`
- `M:System.Reflection.Assembly.GetFile(System.String)`
- `M:System.Environment.GetCommandLineArgs`
- `P:System.AppContext.BaseDirectory`

-->
