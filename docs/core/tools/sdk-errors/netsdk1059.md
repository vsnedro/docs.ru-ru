---
title: NETSDK1059. Проект содержит устаревшее средство .NET CLI
description: Устранение проблемы с проектом, содержащим устаревший инструмент .NET CLI.
author: sfoslund
ms.topic: error-reference
ms.date: 10/09/2020
f1_keywords:
- NETSDK1059
ms.openlocfilehash: 2960b9255dab9e61a84e49bc029666753d8c9a1e
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2020
ms.locfileid: "91957116"
---
# <a name="netsdk1059-project-contains-obsolete-net-cli-tool"></a>NETSDK1059. Проект содержит устаревшее средство .NET CLI

**Эта статья относится к:** ✔️ пакету SDK для .NET 2.1.100 и более поздних версий

Если пакет SDK для .NET выдает предупреждение NETSDK1059, значит, ваш проект содержит устаревшее средство .NET CLI. Начиная с .NET 2.1 эти средства включены в пакет SDK для .NET, и в проекте не требуется явная ссылка на них. Дополнительные сведения о миграции на .NET 2.1 можно найти [здесь](https://aka.ms/dotnetclitools-in-box).
