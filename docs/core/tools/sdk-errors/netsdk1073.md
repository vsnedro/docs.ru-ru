---
title: 'NETSDK1073: элемент FrameworkReference не распознан'
description: Устранение проблемы, когда не удается найти элемент FrameworkReference.
author: marcpopMSFT
ms.topic: error-reference
ms.date: 10/9/2020
f1_keywords:
- NETSDK1073
ms.openlocfilehash: 2b2dbf2a0d3e13dca4fe634529b7951f2333ce28
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713032"
---
# <a name="netsdk1073-the-frameworkreference-was-not-recognized"></a>NETSDK1073: элемент FrameworkReference не распознан

**Эта статья относится к:** ✔️ пакету SDK для .NET Core 2.1.100 и более поздних версий

Эта ошибка обычно означает, что существует версия определенного элемента FrameworkReference, которую пакет SDK не может найти. Попробуйте удалить папки *obj* и *bin* и запустите `dotnet restore`, чтобы повторно скачать последние пакеты.

Кроме того, может возникнуть ошибка установки, поэтому убедитесь, что вы используете последние версии .NET и Visual Studio.
