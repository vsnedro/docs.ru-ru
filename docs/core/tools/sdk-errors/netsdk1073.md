---
title: 'NETSDK1073: элемент FrameworkReference не распознан'
description: Устранение проблемы, когда не удается найти элемент FrameworkReference.
author: marcpopMSFT
ms.topic: error-reference
ms.date: 10/9/2020
f1_keywords:
- NETSDK1073
ms.openlocfilehash: 59b5f63dcfe0115feabc2d87d24a09c6a650cc62
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2020
ms.locfileid: "91957113"
---
# <a name="netsdk1073-the-frameworkreference-was-not-recognized"></a><span data-ttu-id="ecc68-103">NETSDK1073: элемент FrameworkReference не распознан</span><span class="sxs-lookup"><span data-stu-id="ecc68-103">NETSDK1073: The FrameworkReference was not recognized</span></span>

<span data-ttu-id="ecc68-104">**Эта статья относится к:** ✔️ пакету SDK для .NET 2.1.100 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="ecc68-104">**This article applies to:** ✔️ .NET 2.1.100 SDK and later versions</span></span>

<span data-ttu-id="ecc68-105">Эта ошибка обычно означает, что существует версия определенного элемента FrameworkReference, которую пакет SDK не может найти.</span><span class="sxs-lookup"><span data-stu-id="ecc68-105">This error typically means there is a version of a particular FrameworkReference that the SDK cannot find.</span></span> <span data-ttu-id="ecc68-106">Попробуйте удалить папки *obj* и *bin* и запустите `dotnet restore`, чтобы повторно скачать последние пакеты.</span><span class="sxs-lookup"><span data-stu-id="ecc68-106">Try deleting your *obj* and *bin* folders and running `dotnet restore` to redownload the latest targeting packs.</span></span>

<span data-ttu-id="ecc68-107">Кроме того, может возникнуть ошибка установки, поэтому убедитесь, что вы используете последние версии .NET и Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ecc68-107">Alternatively, there could be an issue with your install, so ensure you're on the latest versions of .NET and Visual Studio</span></span>
