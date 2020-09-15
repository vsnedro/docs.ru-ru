---
ms.openlocfilehash: 416590c7bd959eea011b7e7c5db48f22d349d0f5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615748"
---
### <a name="apps-published-with-clickonce-that-use-a-sha-256-code-signing-certificate-may-fail-on-windows-2003"></a><span data-ttu-id="20b22-101">Приложения, опубликованные с помощью ClickOnce с использованием сертификата подписи кода SHA-256, могут завершиться ошибкой в Windows 2003</span><span class="sxs-lookup"><span data-stu-id="20b22-101">Apps published with ClickOnce that use a SHA-256 code-signing certificate may fail on Windows 2003</span></span>

#### <a name="details"></a><span data-ttu-id="20b22-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="20b22-102">Details</span></span>

<span data-ttu-id="20b22-103">Исполняемый файл подписывается с помощью SHA256.</span><span class="sxs-lookup"><span data-stu-id="20b22-103">The executable is signed with SHA256.</span></span> <span data-ttu-id="20b22-104">Ранее он подписывался с помощью SHA1 независимо от того, какой использовался сертификат подписи кода: SHA-1 или SHA-256.</span><span class="sxs-lookup"><span data-stu-id="20b22-104">Previously, it was signed with SHA1 regardless of whether the code-signing certificate was SHA-1 or SHA-256.</span></span> <span data-ttu-id="20b22-105">Применение:</span><span class="sxs-lookup"><span data-stu-id="20b22-105">This applies to:</span></span>

- <span data-ttu-id="20b22-106">Все приложения, собранные с помощью Visual Studio 2012 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="20b22-106">All applications built with Visual Studio 2012 or later.</span></span>
- <span data-ttu-id="20b22-107">Приложения, собранные с помощью Visual Studio 2010 или более ранней версии в системах с установленной платформой .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="20b22-107">Applications built with Visual Studio 2010 or earlier on systems with the .NET Framework 4.5 present.</span></span>
<span data-ttu-id="20b22-108">Кроме того, при наличии .NET Framework 4.5 или более поздней версии манифест ClickOnce также подписывается с помощью SHA-256 для сертификатов SHA-256 независимо от версии .NET Framework, в которой проводилась компиляция.</span><span class="sxs-lookup"><span data-stu-id="20b22-108">In addition, if the .NET Framework 4.5 or later is present, the ClickOnce manifest is also signed with SHA-256 for SHA-256 certificates regardless of the .NET Framework version against which it was compiled.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="20b22-109">Предложение</span><span class="sxs-lookup"><span data-stu-id="20b22-109">Suggestion</span></span>

<span data-ttu-id="20b22-110">Изменение подписи исполняемого файла ClickOnce влияет только на системы Windows Server 2003; потребуется установка компонента из статьи базы знаний 938397.</span><span class="sxs-lookup"><span data-stu-id="20b22-110">The change in signing the ClickOnce executable affects only Windows Server 2003 systems; they require that KB 938397 be installed.</span></span> <span data-ttu-id="20b22-111">Изменение подписи манифеста с SHA-256, даже если целевая платформа приложения — .NET Framework 4.0 или более ранней версии, вводит зависимость среды выполнения для .NET Framework 4.5 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="20b22-111">The change in signing the manifest with SHA-256 even when an app targets the .NET Framework 4.0 or earlier versions introduces a runtime dependency on the .NET Framework 4.5 or a later version.</span></span>

| <span data-ttu-id="20b22-112">name</span><span class="sxs-lookup"><span data-stu-id="20b22-112">Name</span></span>    | <span data-ttu-id="20b22-113">Значение</span><span class="sxs-lookup"><span data-stu-id="20b22-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="20b22-114">Область</span><span class="sxs-lookup"><span data-stu-id="20b22-114">Scope</span></span>   | <span data-ttu-id="20b22-115">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="20b22-115">Edge</span></span>        |
| <span data-ttu-id="20b22-116">Version</span><span class="sxs-lookup"><span data-stu-id="20b22-116">Version</span></span> | <span data-ttu-id="20b22-117">4.5</span><span class="sxs-lookup"><span data-stu-id="20b22-117">4.5</span></span>         |
| <span data-ttu-id="20b22-118">Type</span><span class="sxs-lookup"><span data-stu-id="20b22-118">Type</span></span>    | <span data-ttu-id="20b22-119">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="20b22-119">Retargeting</span></span> |
