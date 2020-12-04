---
title: Правила документации (анализ кода)
description: Дополнительные сведения о правилах анализа кода
ms.date: 09/16/2019
ms.topic: reference
f1_keywords:
- vs.codeanalysis.documentationrules
helpviewer_keywords:
- documentation rules
- managed code analysis rules, documentation rules
- warnings, documentation
author: mavasani
ms.author: mavasani
ms.openlocfilehash: 29d1734eec29bd00d456b4b00c48c2e8ef223441
ms.sourcegitcommit: 2e4adc490c1d2a705a0592b295d606b10b9f51f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2020
ms.locfileid: "96592665"
---
# <a name="documentation-rules"></a>Правила документирования

Правила документации поддерживают написание хорошо документированных библиотек посредством правильного использования [комментариев XML-документации](../../../csharp/codedoc.md) для внешних видимых интерфейсов API.

## <a name="in-this-section"></a>В этом разделе

| Правило | Описание |
| - | - |
| [CA1200: Избегайте использования тегов cref с префиксом](ca1200.md) | Атрибут [cref](../../../csharp/programming-guide/xmldoc/cref-attribute.md) в ТЕГЕ документации XML означает "ссылка на код". Он указывает, что текст внутри тега представляет собой элемент кода, например тип, метод или свойство. Старайтесь не использовать `cref` теги с префиксами, так как это не позволяет компилятору проверять ссылки. Это также предотвращает Поиск и обновление этих ссылок на символы во время рефакторинга в интегрированной среде разработки (IDE) Visual Studio. |
