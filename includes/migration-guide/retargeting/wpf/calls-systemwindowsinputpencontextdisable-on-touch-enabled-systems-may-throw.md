---
ms.openlocfilehash: a44458484ea09c566defeabc9b604bd55d994e93
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617548"
---
### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a>Вызовы System.Windows.Input.PenContext.Disable в системах с поддержкой сенсорного ввода могут вызвать исключение ArgumentException

#### <a name="details"></a>Подробнее

В некоторых случаях вызовы внутреннего метода **System.Windows.Intput.PenContext.Disable** в системах с поддержкой сенсорного ввода могут вызывать необработанное исключение `T:System.ArgumentException` из-за повторного входа.

#### <a name="suggestion"></a>Предложение

Эта проблема была устранена в .NET Framework 4.7. Чтобы это исключение не возникало, выполните обновление до версии платформы .NET Framework 4.7 или более поздней.

| name    | Значение       |
|:--------|:------------|
| Область   | Пограничный случай        |
| Version | 4.6.1       |
| Type    | Изменение целевой платформы |
