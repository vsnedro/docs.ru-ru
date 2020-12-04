---
title: NETSDK1059. Проект содержит устаревшее средство .NET CLI
description: Устранение проблемы с проектом, содержащим устаревший инструмент .NET CLI.
author: sfoslund
ms.topic: error-reference
ms.date: 10/09/2020
f1_keywords:
- NETSDK1059
ms.openlocfilehash: b80f42495e1aff8d37008946f10f68c195d5a9ec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713123"
---
# <a name="netsdk1059-project-contains-obsolete-net-cli-tool"></a>NETSDK1059. Проект содержит устаревшее средство .NET CLI

**Эта статья относится к:** ✔️ пакету SDK для .NET Core 2.1.100 и более поздних версий

Если пакет SDK для .NET выдает предупреждение NETSDK1059, значит, ваш проект содержит устаревшее средство .NET CLI. Начиная с .NET Core 2.1 эти средства включены в пакет SDK для .NET, и в проекте не требуется явная ссылка на них. Дополнительные сведения о переходе на .NET Core 2.1 представлены [здесь](https://aka.ms/dotnetclitools-in-box).
