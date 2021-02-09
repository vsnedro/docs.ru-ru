---
description: 'Подробнее о следующем: Практическое руководство. Запись сообщений в журнал (Visual Basic)'
title: Практическое руководство. Запись сообщений в журнал
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application.Log object, writing log messages
ms.assetid: 972a3e0c-2996-4623-a7a9-d7ebc4d207f8
ms.openlocfilehash: ed455fdb2cebda908981514bef932942adf499ce
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797306"
---
# <a name="how-to-write-log-messages-visual-basic"></a>Практическое руководство. Запись сообщений в журнал (Visual Basic)

Для записи в журнал информации о приложении можно использовать объекты `My.Application.Log` и `My.Log` . В этом примере показано использование метода `My.Application.Log.WriteEntry` для записи в журнал данных трассировки.

Для записи в журнал информации об исключениях используйте метод `My.Application.Log.WriteException`; см. раздел [Практическое руководство. Запись в журнал сведений об исключениях](how-to-log-exceptions.md).

## <a name="example"></a>Пример

В этом примере используется метод `My.Application.Log.WriteEntry` для записи данных трассировки.

[!code-vb[VbVbalrMyApplicationLog#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#11)]

## <a name="net-framework-security"></a>Безопасность .NET Framework

Убедитесь в том, что записываемые в журнал данные не включают конфиденциальных сведений, например паролей пользователей. Дополнительные сведения см. в разделе [Работа с журналами приложения](working-with-application-logs.md).

## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [Работа с журналами приложения](working-with-application-logs.md)
- [Практическое руководство. Исплючения журналов](how-to-log-exceptions.md)
- [Пошаговое руководство. Определение места записи сведений для My.Application.Log](walkthrough-determining-where-my-application-log-writes-information.md)
- [Пошаговое руководство. Изменение места записи сведений для My.Application.Log](walkthrough-changing-where-my-application-log-writes-information.md)
- [Пошаговое руководство: Фильтрация вывода My.Application.Log](walkthrough-filtering-my-application-log-output.md)
