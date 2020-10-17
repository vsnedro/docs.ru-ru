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
# <a name="netsdk1073-the-frameworkreference-was-not-recognized"></a>NETSDK1073: элемент FrameworkReference не распознан

**Эта статья относится к:** ✔️ пакету SDK для .NET 2.1.100 и более поздних версий

Эта ошибка обычно означает, что существует версия определенного элемента FrameworkReference, которую пакет SDK не может найти. Попробуйте удалить папки *obj* и *bin* и запустите `dotnet restore`, чтобы повторно скачать последние пакеты.

Кроме того, может возникнуть ошибка установки, поэтому убедитесь, что вы используете последние версии .NET и Visual Studio.
