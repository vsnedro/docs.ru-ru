---
title: 'Устранение рисков: управление версиями продукта'
description: В этой статье приводятся сведения о том, чем управление версиями продукта в .NET Framework 4.6 и более поздних версиях отличается от управления в предыдущих выпусках.
ms.date: 03/30/2017
ms.assetid: 1c4de9d7-9aba-427a-8f38-0ab9bfb8f85e
ms.openlocfilehash: 442c06446e763758d3a150ee9ff884a616541c07
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475402"
---
# <a name="mitigation-product-versioning"></a><span data-ttu-id="1c67a-103">Устранение рисков. Управление версиями продукта</span><span class="sxs-lookup"><span data-stu-id="1c67a-103">Mitigation: Product Versioning</span></span>

<span data-ttu-id="1c67a-104">В .NET Framework 4.6 и более поздних версиях управление версиями продукта отличается от предыдущих выпусков платформы .NET Framework (.NET Framework 4, 4.5, 4.5.1 и 4.5.2).</span><span class="sxs-lookup"><span data-stu-id="1c67a-104">In the .NET Framework 4.6 and later, product versioning has changed from the previous releases of the .NET Framework (the .NET Framework 4, 4.5, 4.5.1, and 4.5.2).</span></span>

## <a name="product-versioning-changes"></a><span data-ttu-id="1c67a-105">Изменения управления версиями продукта</span><span class="sxs-lookup"><span data-stu-id="1c67a-105">Product versioning changes</span></span>

<span data-ttu-id="1c67a-106">Ниже приведено подробное описание изменений.</span><span class="sxs-lookup"><span data-stu-id="1c67a-106">The following are the detailed changes:</span></span>

- <span data-ttu-id="1c67a-107">Значение записи `Version` в разделе `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` изменилось на `4.6.`*xxxxx* в .NET Framework 4.6 и ее доработанных версиях и на `4.7.`*xxxxx* в .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="1c67a-107">The value of the `Version` entry in the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` key has changed to `4.6.`*xxxxx* for the .NET Framework 4.6 and its point releases, and to `4.7.`*xxxxx* for the .NET Framework 4.7.</span></span> <span data-ttu-id="1c67a-108">В .NET Framework 4.5, 4.5.1 и 4.5.2 использовался формат `4.5.`*xxxxx*.</span><span class="sxs-lookup"><span data-stu-id="1c67a-108">In the .NET Framework 4.5, 4.5.1, and 4.5.2, it had the format `4.5.`*xxxxx*.</span></span>

- <span data-ttu-id="1c67a-109">Управление версиями файлов и продукта для файлов .NET Framework было изменено с более ранней схемы управления версиями `4.0.30319.x` на `4.6.X.0` для .NET Framework 4.6 и ее доработанных выпусков, а также на `4.7.X.0` для .NET Framework 4.7 и ее доработанных выпусков.</span><span class="sxs-lookup"><span data-stu-id="1c67a-109">The file and product versioning for .NET Framework files has changed from the earlier versioning scheme of `4.0.30319.x` to `4.6.X.0` for the .NET Framework 4.6 and its point releases, and to `4.7.X.0` for the .NET Framework 4.7 and its point releases.</span></span> <span data-ttu-id="1c67a-110">Вы можете увидеть эти новые значения в **свойствах** файла, щелкнув файл правой кнопкой мыши.</span><span class="sxs-lookup"><span data-stu-id="1c67a-110">You can see these new values when you view the file's **Properties** after right-clicking on a file.</span></span>

- <span data-ttu-id="1c67a-111">Атрибуты <xref:System.Reflection.AssemblyFileVersionAttribute> и <xref:System.Reflection.AssemblyInformationalVersionAttribute> для управляемых сборок имеют значения <xref:System.Version> в виде `4.6.X.0` на платформе .NET Framework 4.6 и в ее доработанных выпусках или `4.7.X.0` на платформе .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="1c67a-111">The <xref:System.Reflection.AssemblyFileVersionAttribute> and <xref:System.Reflection.AssemblyInformationalVersionAttribute> attributes for managed assemblies have <xref:System.Version> values in the form `4.6.X.0` for the .NET Framework 4.6 and its point releases, and `4.7.X.0` for the .NET Framework 4.7.</span></span>

- <span data-ttu-id="1c67a-112">Начиная с .NET Framework 4.6, свойство <xref:System.Environment.Version%2A?displayProperty=nameWithType> возвращает исправленную строку версии `4.0.30319.42000`.</span><span class="sxs-lookup"><span data-stu-id="1c67a-112">Starting with .NET Framework 4.6, the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property returns the fixed version string `4.0.30319.42000`.</span></span> <span data-ttu-id="1c67a-113">В .NET Framework 4, 4.5, 4.5.1 и 4.5.2 оно возвращает строки версии в формате `4.0.30319.xxxxx`, где `xxxxx` меньше 42000 (например, 4.0.30319.18010).</span><span class="sxs-lookup"><span data-stu-id="1c67a-113">In the .NET Framework 4, 4.5, 4.5.1, and 4.5.2, it returns version strings in the format `4.0.30319.xxxxx` where `xxxxx` is less than 42000 (for example, "4.0.30319.18010").</span></span> <span data-ttu-id="1c67a-114">Обратите внимание, что создание в свойстве <xref:System.Environment.Version%2A?displayProperty=nameWithType> новых зависимостей от кода приложения не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="1c67a-114">Note that we do not recommend application code taking any new dependency on the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property.</span></span>

### <a name="handling-the-product-versioning-changes"></a><span data-ttu-id="1c67a-115">Обработка изменений управления версиями продукта</span><span class="sxs-lookup"><span data-stu-id="1c67a-115">Handling the product versioning changes</span></span>

<span data-ttu-id="1c67a-116">В общем случае приложения для обнаружения таких сведений, как версия среды выполнения .NET Framework и каталог установки, должны использовать следующие рекомендуемые методы:</span><span class="sxs-lookup"><span data-stu-id="1c67a-116">In general, applications should depend on the recommended techniques for detecting such things as the runtime version of the .NET Framework and the installation directory:</span></span>

- <span data-ttu-id="1c67a-117">Чтобы определить версию среды выполнения .NET Framework, см. статью [Практическое руководство. Определение установленных версий платформы .NET Framework](how-to-determine-which-versions-are-installed.md).</span><span class="sxs-lookup"><span data-stu-id="1c67a-117">To detect the runtime version of the .NET Framework, see [How to: Determine Which .NET Framework Versions Are Installed](how-to-determine-which-versions-are-installed.md).</span></span>

- <span data-ttu-id="1c67a-118">Чтобы определить путь установки платформы .NET Framework, используйте значение записи `InstallPath` в ключе `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full`.</span><span class="sxs-lookup"><span data-stu-id="1c67a-118">To determine the installation path for the .NET Framework, use the value of the `InstallPath` entry in the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` key.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="1c67a-119">Имя подраздела — `NET Framework Setup`, а не `.NET Framework Setup`.</span><span class="sxs-lookup"><span data-stu-id="1c67a-119">The subkey name is `NET Framework Setup`, not `.NET Framework Setup`.</span></span>

- <span data-ttu-id="1c67a-120">Чтобы определить путь к каталогу общеязыковой среды выполнения .NET Framework, вызовите метод <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeDirectory%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1c67a-120">To determine the directory path to the .NET Framework common language runtime, call the <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeDirectory%2A?displayProperty=nameWithType> method.</span></span>

- <span data-ttu-id="1c67a-121">Чтобы получить версию среды CLR, вызовите метод <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetSystemVersion%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1c67a-121">To get the CLR version, call the <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetSystemVersion%2A?displayProperty=nameWithType> method.</span></span>   <span data-ttu-id="1c67a-122">Для .NET Framework 4 и ее доработанных выпусков (.NET Framework 4.5, 4.5.1, 4.5.2 и .NET Framework 4.6, 4.6.1, 4.6.2 и 4.7) возвращается строка `v4.0.30319`.</span><span class="sxs-lookup"><span data-stu-id="1c67a-122">For the .NET Framework 4 and its point releases (the .NET Framework 4.5, 4.5.1, 4.5.2, and .NET Framework 4.6, 4.6.1, 4.6.2, and 4.7), it returns the string `v4.0.30319`.</span></span>

## <a name="see-also"></a><span data-ttu-id="1c67a-123">См. также</span><span class="sxs-lookup"><span data-stu-id="1c67a-123">See also</span></span>

- [<span data-ttu-id="1c67a-124">Совместимость приложений</span><span class="sxs-lookup"><span data-stu-id="1c67a-124">Application compatibility</span></span>](application-compatibility.md)
