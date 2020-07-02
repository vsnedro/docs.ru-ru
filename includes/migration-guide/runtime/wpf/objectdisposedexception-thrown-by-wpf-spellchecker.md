---
ms.openlocfilehash: b836b26f3f52e9d0cc78feb764629bd2fa306657
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621833"
---
### <a name="objectdisposedexception-thrown-by-wpf-spellchecker"></a>Исключение ObjectDisposedException, создаваемое средством проверки орфографии WPF

#### <a name="details"></a>Подробнее

В некоторых случаях при завершении работы приложений WPF происходит сбой с исключением <xref:System.ObjectDisposedException?displayProperty=fullName>, создаваемым средством проверки орфографии. Эта ошибка исправлена в WPF .NET Framework 4.7 за счет правильной обработки этого исключения, что позволяет исключить подобное нежелательное поведение приложений. Следует отметить, что случайные первичные исключения могут по-прежнему наблюдаться в приложениях, выполняемых в режиме отладки.

#### <a name="suggestion"></a>Предложение

Выполните обновление до .NET Framework 4.7.

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.6.1|
|Type|Среда выполнения|
