---
ms.openlocfilehash: b371525c9f4e57c6a09e5bb9232884e5c5e707e0
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602768"
---

<span data-ttu-id="0f1bb-101">Если для установки используется диспетчер пакетов, эти библиотеки устанавливаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="0f1bb-101">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="0f1bb-102">Но если вы устанавливаете .NET Core вручную или публикуете автономное приложение, вам потребуется установить эти библиотеки:</span><span class="sxs-lookup"><span data-stu-id="0f1bb-102">But, if you manually install .NET Core or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="0f1bb-103">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="0f1bb-103">lttng-ust</span></span>
- <span data-ttu-id="0f1bb-104">libcurl</span><span class="sxs-lookup"><span data-stu-id="0f1bb-104">libcurl</span></span>
- <span data-ttu-id="0f1bb-105">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="0f1bb-105">openssl-libs</span></span>
- <span data-ttu-id="0f1bb-106">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="0f1bb-106">krb5-libs</span></span>
- <span data-ttu-id="0f1bb-107">libicu</span><span class="sxs-lookup"><span data-stu-id="0f1bb-107">libicu</span></span>
- <span data-ttu-id="0f1bb-108">zlib</span><span class="sxs-lookup"><span data-stu-id="0f1bb-108">zlib</span></span>
- <span data-ttu-id="0f1bb-109">libunwind</span><span class="sxs-lookup"><span data-stu-id="0f1bb-109">libunwind</span></span>
- <span data-ttu-id="0f1bb-110">libuuid</span><span class="sxs-lookup"><span data-stu-id="0f1bb-110">libuuid</span></span>

<span data-ttu-id="0f1bb-111">Если в целевой среде выполнения установлена версия OpenSSL 1.1 или более поздняя, необходимо установить **compat-openssl10**.</span><span class="sxs-lookup"><span data-stu-id="0f1bb-111">If the target runtime environment's OpenSSL version is 1.1 or newer, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="0f1bb-112">Дополнительные сведения о зависимостях см. в статье об [автономных приложениях Linux](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span><span class="sxs-lookup"><span data-stu-id="0f1bb-112">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="0f1bb-113">Для приложений .NET Core, использующих сборку *System.Drawing.Common*, необходима также следующая зависимость:</span><span class="sxs-lookup"><span data-stu-id="0f1bb-113">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- [<span data-ttu-id="0f1bb-114">libgdiplus (версии 6.0.1 или выше)</span><span class="sxs-lookup"><span data-stu-id="0f1bb-114">libgdiplus (version 6.0.1 or later)</span></span>](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > <span data-ttu-id="0f1bb-115">Вы можете установить последнюю версию *libgdiplus*, добавив в систему репозиторий Mono.</span><span class="sxs-lookup"><span data-stu-id="0f1bb-115">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="0f1bb-116">Для получения дополнительной информации см. <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="0f1bb-116">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>
