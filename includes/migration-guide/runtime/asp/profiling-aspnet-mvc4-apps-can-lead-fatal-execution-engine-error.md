---
ms.openlocfilehash: 2e13268d4983af5d2fdd6d12b4d9e67d61d07f3d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622130"
---
### <a name="profiling-aspnet-mvc4-apps-can-lead-to-fatal-execution-engine-error"></a>Профилирование приложений ASP.Net MVC4 может привести к неустранимой ошибке подсистемы выполнения

#### <a name="details"></a>Подробнее

Профилирование с использованием сборок NGEN /Profile может привести к сбою при запуске профилируемых приложений ASP.NET MVC4 с неустранимой ошибкой подсистемы выполнения

#### <a name="suggestion"></a>Предложение

Эта проблема решена в .NET Framework 4.5.2. Также можно избежать этой проблемы, указав <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> в маске события профилировщика.

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.5|
|Type|Среда выполнения|
