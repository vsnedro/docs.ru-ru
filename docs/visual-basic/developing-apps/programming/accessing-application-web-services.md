---
title: Доступ к веб-службам приложения
ms.date: 07/20/2015
helpviewer_keywords:
- Web services [Visual Basic], My.WebServices object
- My.WebServices object
- applications [Visual Basic], Web services
ms.assetid: 8ad5405b-e771-42b1-82d3-ce97af2cea9e
ms.openlocfilehash: cf9a0c9840b9228b59af9959cf3a4efb9a1d1ea0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410196"
---
# <a name="accessing-application-web-services-visual-basic"></a>Доступ к веб-службам приложения (Visual Basic)

Объект `My.WebServices` предоставляет экземпляр каждой веб-службы, на которую ссылается текущий проект. Каждый экземпляр создается по запросу. Доступ к этим веб-службам можно получить через свойства объекта `My.WebServices`. Имя свойства совпадает с именем веб-службы, к которой обращается свойство. Любой класс, наследуемый от <xref:System.Web.Services.Protocols.SoapHttpClientProtocol>, является веб-службой.

## <a name="tasks"></a>Задания

В следующей таблице перечислены возможные способы доступа к веб-службам, на которые ссылается приложение.

|Чтобы|См.|
|---|---|
|Вызов веб-службы|[Объект My.WebServices](../../language-reference/objects/my-webservices-object.md)|
|Вызов веб-службы в асинхронном режиме и обработка события при его завершении|[Практическое руководство. Асинхронный вызов веб-службы](how-to-call-a-web-service-asynchronously.md)|

## <a name="see-also"></a>См. также раздел

- [Объект My.WebServices](../../language-reference/objects/my-webservices-object.md)
