---
description: Дополнительные сведения о надежных сеансах
title: Надежные сеансы
ms.date: 03/30/2017
f1_keywords:
- Windows Communication Foundation, sessions and instances
- WCF, sessions and instances
- sessions and instances [WCF]
helpviewer_keywords:
- instances [WCF]
- sessions [WCF]
ms.assetid: 143951b3-3aa0-4540-b4b7-d33e77e874a1
ms.openlocfilehash: 86df4ccf9c1fd52d162ad7272ece5591f0ca7482
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99632884"
---
# <a name="reliable-sessions"></a>Надежные сеансы

В этом разделе описывается, что такое надежный сеанс Windows Communication Foundation (WCF), что он использует, как и когда использовать его, какие конфигурации привязки поддерживаются, а также указатели на рекомендации. В следующей таблице собраны сведения о ключевых вопросах и связанных разделах.

WCF надежного сеанса предоставляет функции, гарантирующие передачу сообщений между конечными точками через протоколы SOAP или транспортные посредники и доставляемые только один раз и, при необходимости, в том же порядке, в котором они были отправлены.

Чтобы использовать надежный сеанс с приложением WCF, либо используйте одну из предоставляемых системой привязок в WCF, которая поддерживает надежный сеанс по умолчанию или как вариант, либо создайте собственную настраиваемую привязку, которая поддерживает этот сеанс.

## <a name="in-this-section"></a>В этом разделе

[Обзор надежных сеансов](reliable-sessions-overview.md) Описывает надежные сеансы, когда их использовать, различные привязки, которые поддерживают надежные сеансы и как они работают.

[Как обмениваться сообщениями в надежном сеансе](how-to-exchange-messages-within-a-reliable-session.md) Описывает, как создать надежный сеанс по протоколу HTTP с помощью пользовательской привязки, заданной в конфигурации.

[Как защитить сообщения в надежных сеансах](how-to-secure-messages-within-reliable-sessions.md) Описывает, как защитить надежный сеанс.

[Как создать настраиваемую привязку надежного сеанса с помощью HTTPS](how-to-create-a-custom-reliable-session-binding-with-https.md) Описывает, как создать надежный сеанс по протоколу HTTPS.

Рекомендации [по надежным сеансам](best-practices-for-reliable-sessions.md) Описывает некоторые рекомендации, связанные с использованием надежного сеанса.

## <a name="reference"></a>Справочник

<xref:System.ServiceModel.ReliableSession>

## <a name="see-also"></a>См. также

- [Очереди и надежные сеансы](queues-and-reliable-sessions.md)
- [Сеансы, экземпляры и параллелизм](sessions-instancing-and-concurrency.md)
