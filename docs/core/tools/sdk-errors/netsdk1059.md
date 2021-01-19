---
title: NETSDK1059. Проект содержит устаревшее средство .NET CLI
description: Устранение проблемы с проектом, содержащим устаревший инструмент .NET CLI.
author: sfoslund
ms.topic: error-reference
ms.date: 10/09/2020
f1_keywords:
- NETSDK1059
ms.openlocfilehash: bba5f4dafa346d81274541f3c40ecc5ed6fff8ab
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2021
ms.locfileid: "98190329"
---
# <a name="netsdk1059-project-contains-obsolete-net-cli-tool"></a>NETSDK1059. Проект содержит устаревшее средство .NET CLI

**Эта статья относится к:** ✔️ пакету SDK для .NET Core 2.1.100 и более поздних версий

Если пакет SDK для .NET выдает предупреждение NETSDK1059, значит, ваш проект содержит устаревшее средство .NET CLI. Начиная с .NET Core 2.1 эти средства включены в пакет SDK для .NET, и в проекте не требуется явная ссылка на них. Дополнительные сведения о переходе на .NET Core 2.1 представлены [здесь](../../migration/20-21.md).
