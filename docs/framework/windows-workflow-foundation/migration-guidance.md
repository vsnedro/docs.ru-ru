---
title: Руководство по миграции
description: 'Дополнительные сведения: руководство по миграции'
ms.date: 03/30/2017
ms.assetid: cb65c132-58c9-4028-b3d4-1efc71d5e60e
ms.openlocfilehash: 83c6af4d8eed396501aafc568de8e64d30ae7cfe
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2021
ms.locfileid: "102104865"
---
# <a name="migration-guidance"></a>Руководство по миграции

В платформа .NET Framework 4 корпорация Майкрософт выпустила вторую основную версию Windows Workflow Foundation (WF). [!INCLUDE[wf1](../../../includes/wf1-md.md)] был выпущен в WinFX (он включал в себя типы в System. Workflow. \* пространства имен, теперь НАЗЫВАЕТСЯ WF3) и улучшен в платформа .NET Framework 3,5. WF3 также является частью платформа .NET Framework 4, но она существует вместе с новой технологией рабочих процессов (типы в System. Activitys. \* пространство_именs; называются WF4). При принятии решения об использовании WF4 важно помнить, что управление временем осуществляет пользователь.

- WF3 является полностью поддерживаемой частью платформа .NET Framework 4.

- Приложения WF3 работают на платформа .NET Framework 4 без изменений и по прежнему поддерживаются полностью.

- Можно создавать новые приложения WF3, а существующие приложения можно редактировать в Visual Studio 2012 и полностью поддерживаются.

Таким решением, решение о принятии платформа .NET Framework 4 отделено от вашего решения о переходе на WF4 (System. Activity. \* ) из WF3 (System. Workflow. \* ). В этом разделе приведены ссылки на руководство по миграции в WF, в котором описывается работа с WF3 и WF4.

## <a name="wf-migration-white-papers-and-cookbooks"></a>Технические документы и справочники по переносу WF

 [Общие сведения о миграции WF](https://download.microsoft.com/download/5/9/9/599CF8A9-5FE2-426A-A536-A83F84D38BF9/WF%20Migration%20Overview.docx)\
 Описывает связь между WF3 и WF4, а также возможные варианты в качестве пользователя или потенциального пользователя технологии рабочего процесса в платформа .NET Framework 4.

 [Миграция WF. рекомендации по разработке WF3](https://download.microsoft.com/download/5/9/9/599CF8A9-5FE2-426A-A536-A83F84D38BF9/WF%20Migration%20Best%20Practices.docx)\
 Описывается разработка артефактов WF3 с учетом возможностей упрощения миграции на WF4.

 [Руководство по WF: правила](https://download.microsoft.com/download/5/9/9/599CF8A9-5FE2-426A-A536-A83F84D38BF9/WF4%20Rules%20Guidance.docx)\
 Описывает, как перенести связанные с правилами инвестиции в решения платформа .NET Framework 4.

 [Руководство по WF: конечный автомат](https://download.microsoft.com/download/5/9/9/599CF8A9-5FE2-426A-A536-A83F84D38BF9/WF4%20State%20Machine%20Guidance.doc) Обсуждается моделирование потока управления WF4 при отсутствии действия State-Machine. Это руководство применимо только к проектам рабочих процессов, предназначенным для платформа .NET Framework 4. Рабочие процессы конечного автомата были добавлены в платформа .NET Framework 4.0.1 с выпуском обновления 1 для платформы и включены в состав платформа .NET Framework 4,5. Дополнительные сведения о рабочих процессах конечного автомата в платформа .NET Framework 4.0.1-4.0.3 и платформа .NET Framework 4,5 см. в разделе [Обновление 4.0.1 для компонентов Microsoft .NET Framework 4](/previous-versions/dotnet/netframework-4.0/hh290669(v=vs.100)) и [рабочих процессов конечного автомата](state-machine-workflows.md).

 [Cookbook миграции WF. пользовательские действия](https://download.microsoft.com/download/5/9/9/599CF8A9-5FE2-426A-A536-A83F84D38BF9/WF%20Migration%20Cookbook%20Custom%20Activities.docx)\
 Обеспечивает примеры и инструкции по изменению структуры настраиваемых действий WF3 в WF4.

 [Cookbook миграции WF. Расширенные пользовательские действия](https://download.microsoft.com/download/5/9/9/599CF8A9-5FE2-426A-A536-A83F84D38BF9/WF%20Migration%20Cookbook%20Advanced%20Custom%20Activities.docx)\
 Предоставляет рекомендации по перепроектированию расширенных пользовательских действий WF3, использующих очереди WF3 и планирование дочерних действий в виде пользовательских действий WF4.
%20 [Миграция WF Cookbook: рабочие процессы](https://download.microsoft.com/download/5/9/9/599CF8A9-5FE2-426A-A536-A83F84D38BF9/WF%20Migration%20Cookbook%20Workflows.docx)\
 Обеспечивает примеры и инструкции по изменению структуры рабочих процессов WF3 в WF4.

 [Cookbook миграции WF. размещение рабочих процессов](https://download.microsoft.com/download/5/9/9/599CF8A9-5FE2-426A-A536-A83F84D38BF9/WF%20Migration%20Cookbook%20Workflow%20Hosting.docx)\
 Предоставляет рекомендации по перепроектированию кода размещения WF3 как кода размещения для WF4. Цель - описать ключевые различия процессов размещения рабочего процесса в WF3 и WF4.

 [Cookbook миграции WF. Отслеживание рабочих процессов](https://download.microsoft.com/download/5/9/9/599CF8A9-5FE2-426A-A536-A83F84D38BF9/WF%20Migration%20Cookbook%20Workflow%20Tracking.docx)\
 Предоставляет рекомендации по перепроектированию кода отслеживания и конфигурации WF3 при помощи эквивалентного кода отслеживания и конфигурации для WF4.

 [Руководство по WF. службы рабочих процессов](https://download.microsoft.com/download/5/9/9/599CF8A9-5FE2-426A-A536-A83F84D38BF9/WF4%20Workflow%20Services%20Guidance.docx)\
 Предоставляет построенные на примерах пошаговые инструкции по перепроектированию часто используемых рабочих процессов, которые реализуют веб-службы Windows Communication Foundation (WCF) (называемые службами рабочих процессов), созданные в WF3, для использования средств WF4.

## <a name="see-also"></a>См. также раздел

- <xref:System.Activities.Statements.Interop>
