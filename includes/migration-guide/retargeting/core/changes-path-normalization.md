---
ms.openlocfilehash: 04c4fb4c8e9da8c58a5e26f78a7b13aa6a0df4a0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614688"
---
### <a name="changes-in-path-normalization"></a><span data-ttu-id="b3b8c-101">Изменения нормализации путей</span><span class="sxs-lookup"><span data-stu-id="b3b8c-101">Changes in path normalization</span></span>

#### <a name="details"></a><span data-ttu-id="b3b8c-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="b3b8c-102">Details</span></span>

<span data-ttu-id="b3b8c-103">Начиная с приложений, предназначенных для .NET Framework 4.6.2, был изменен способ нормализации путей в среде выполнения. Нормализация пути включает в себя изменение строки, обозначающей путь или файл, чтобы эта строка соответствовала допустимому пути в целевой операционной системе.</span><span class="sxs-lookup"><span data-stu-id="b3b8c-103">Starting with apps that target the .NET Framework 4.6.2, the way in which the runtime normalizes paths has changed.Normalizing a path involves modifying the string that identifies a path or file so that it conforms to a valid path on the target operating system.</span></span> <span data-ttu-id="b3b8c-104">Нормализация обычно включает в себя:</span><span class="sxs-lookup"><span data-stu-id="b3b8c-104">Normalization typically involves:</span></span>

- <span data-ttu-id="b3b8c-105">канонизацию разделителей компонентов и каталогов;</span><span class="sxs-lookup"><span data-stu-id="b3b8c-105">Canonicalizing component and directory separators.</span></span>
- <span data-ttu-id="b3b8c-106">применение текущего каталога к относительному пути;</span><span class="sxs-lookup"><span data-stu-id="b3b8c-106">Applying the current directory to a relative path.</span></span>
- <span data-ttu-id="b3b8c-107">оценку относительного каталога (.) или родительского каталога (..) в пути;</span><span class="sxs-lookup"><span data-stu-id="b3b8c-107">Evaluating the relative directory (.) or the parent directory (..) in a path.</span></span>
- <span data-ttu-id="b3b8c-108">обрезку указанных символов.</span><span class="sxs-lookup"><span data-stu-id="b3b8c-108">Trimming specified characters.</span></span>
<span data-ttu-id="b3b8c-109">Начиная с приложений, предназначенных для .NET Framework 4.6.2, следующие изменения в нормализации пути включены по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="b3b8c-109">Starting with apps that target the .NET Framework 4.6.2, the following changes in path normalization are enabled by default:</span></span>
  - <span data-ttu-id="b3b8c-110">Среда выполнения перекладывает нормализацию путей на функцию [GetFullPathName](https://docs.microsoft.com/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamew) операционной системы.</span><span class="sxs-lookup"><span data-stu-id="b3b8c-110">The runtime defers to the operating system's [GetFullPathName](https://docs.microsoft.com/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamew) function to normalize paths.</span></span>
- <span data-ttu-id="b3b8c-111">Нормализация больше не предусматривает обрезки окончания сегментов каталогов (например, пробела в конце имени каталога).</span><span class="sxs-lookup"><span data-stu-id="b3b8c-111">Normalization no longer involves trimming the end of directory segments (such as a space at the end of a directory name).</span></span>
- <span data-ttu-id="b3b8c-112">Поддержка синтаксиса пути устройства в режиме полного доверия, включая `\\.\` и (для API-интерфейсов файлового ввода-вывода в mscorlib.dll) `\\?\`.</span><span class="sxs-lookup"><span data-stu-id="b3b8c-112">Support for device path syntax in full trust, including `\\.\` and, for file I/O APIs in mscorlib.dll, `\\?\`.</span></span>
- <span data-ttu-id="b3b8c-113">Среда выполнения не проверяет пути с синтаксисом устройства.</span><span class="sxs-lookup"><span data-stu-id="b3b8c-113">The runtime does not validate device syntax paths.</span></span>
- <span data-ttu-id="b3b8c-114">Поддерживается использование синтаксиса устройства для доступа к альтернативным потокам данных.</span><span class="sxs-lookup"><span data-stu-id="b3b8c-114">The use of device syntax to access alternate data streams is supported.</span></span>
<span data-ttu-id="b3b8c-115">Эти изменения улучшают производительность, позволяя методам получать доступ к ранее недоступным путям.</span><span class="sxs-lookup"><span data-stu-id="b3b8c-115">These changes improve performance while allowing methods to access previously inaccessible paths.</span></span> <span data-ttu-id="b3b8c-116">Это изменение не влияет на приложения, предназначенные для .NET Framework 4.6.1 и более ранних версий, но работающие на платформе .NET Framework 4.6.2 или более новой версии.</span><span class="sxs-lookup"><span data-stu-id="b3b8c-116">Apps that target the .NET Framework 4.6.1 and earlier versions but are running under the .NET Framework 4.6.2 or later are unaffected by this change.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b3b8c-117">Предложение</span><span class="sxs-lookup"><span data-stu-id="b3b8c-117">Suggestion</span></span>

<span data-ttu-id="b3b8c-118">В приложениях, предназначенных для .NET Framework 4.6.2 или более поздней версии, данное изменение можно отключить и использовать устаревшую нормализацию, добавив следующее в раздел `<runtime>` файла конфигурации приложения:</span><span class="sxs-lookup"><span data-stu-id="b3b8c-118">Apps that target the .NET Framework 4.6.2 or later can opt out of this change and use legacy normalization by adding the following to the `<runtime>` section of the application configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />
</runtime>
```

<span data-ttu-id="b3b8c-119">В приложениях, предназначенных для .NET Framework 4.6.1 или более ранней версии, но работающих на платформе .NET Framework 4.6.2 или более поздней версии, можно включить изменения в нормализацию пути, добавив следующее в раздел `<runtime>` файла конфигурации приложения:</span><span class="sxs-lookup"><span data-stu-id="b3b8c-119">Apps that target the .NET Framework 4.6.1 or earlier but are running on the .NET Framework 4.6.2 or later can enable the changes to path normalization by adding the following line to the `<runtime>` section of the application .configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=false" />
</runtime>
```

| <span data-ttu-id="b3b8c-120">name</span><span class="sxs-lookup"><span data-stu-id="b3b8c-120">Name</span></span>    | <span data-ttu-id="b3b8c-121">Значение</span><span class="sxs-lookup"><span data-stu-id="b3b8c-121">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b3b8c-122">Область</span><span class="sxs-lookup"><span data-stu-id="b3b8c-122">Scope</span></span>   | <span data-ttu-id="b3b8c-123">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="b3b8c-123">Minor</span></span>       |
| <span data-ttu-id="b3b8c-124">Version</span><span class="sxs-lookup"><span data-stu-id="b3b8c-124">Version</span></span> | <span data-ttu-id="b3b8c-125">4.6.2</span><span class="sxs-lookup"><span data-stu-id="b3b8c-125">4.6.2</span></span>       |
| <span data-ttu-id="b3b8c-126">Type</span><span class="sxs-lookup"><span data-stu-id="b3b8c-126">Type</span></span>    | <span data-ttu-id="b3b8c-127">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="b3b8c-127">Retargeting</span></span> |
