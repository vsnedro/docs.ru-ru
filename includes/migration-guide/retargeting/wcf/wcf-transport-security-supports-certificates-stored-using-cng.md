---
ms.openlocfilehash: 5c09bee92f679cd7e7a95cd23d5ce0ca9b57170c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614741"
---
### <a name="wcf-transport-security-supports-certificates-stored-using-cng"></a>Защита транспорта WCF поддерживает сертификаты, сохраненные с помощью CNG

#### <a name="details"></a>Подробнее

Начиная с приложений, предназначенных для .NET Framework 4.6.2, защита транспорта WCF поддерживает сертификаты, сохраненные с использованием библиотеки шифрования Windows (CNG). Эта поддержка ограничивается сертификатами с открытым ключом, длина экспоненты которого не превышает 32 бита. Если приложение предназначено для .NET Framework 4.6.2, эта функция включена по умолчанию. В более ранних версиях платформы .NET Framework попытка использовать сертификаты X509 с поставщиком хранилища ключей CSG вызывала исключение.

#### <a name="suggestion"></a>Предложение

Для приложений, которые предназначены для .NET Framework 4.6.1 и более ранних версий, но работают в .NET Framework 4.6.2, можно включить поддержку сертификатов CNG, добавив следующую строку в раздел `<runtime>` файла app.config или web.config:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.ServiceModel.DisableCngCertificates=false" />
</runtime>
```

Это также можно сделать программно с помощью следующего кода:

```csharp
private const string DisableCngCertificates = @"Switch.System.ServiceModel.DisableCngCertificate";

AppContext.SetSwitch(disableCngCertificates, false);
```

```vb
Const DisableCngCertificates As String = "Switch.System.ServiceModel.DisableCngCertificates"
AppContext.SetSwitch(disableCngCertificates, False)
```

Обратите внимание, что из-за этого изменения любой код обработки исключений, который зависит от неудачной попытки инициировать защищенное взаимодействие с сертификатом CNG, больше не будет выполняться.

| name    | Значение       |
|:--------|:------------|
| Область   | Дополнительный номер       |
| Version | 4.6.2       |
| Type    | Изменение целевой платформы |
