---
ms.openlocfilehash: 5c949b79eefa68ea6f8d4ad27c716c438e24f170
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620559"
---
### <a name="deserialization-of-objects-across-appdomains-can-fail"></a>Десериализация объектов между доменами приложений может завершиться сбоем

#### <a name="details"></a>Подробнее

В некоторых случаях, когда приложение использует два или большее количество доменов с разными базовыми папками приложения, при попытке выполнить десериализацию объектов в логическом контексте вызова между доменами приложения возникнет исключение.

#### <a name="suggestion"></a>Предложение

См. статью [Устранение рисков: десериализация объектов между доменами приложений](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.5.1|
|Type|Среда выполнения|
