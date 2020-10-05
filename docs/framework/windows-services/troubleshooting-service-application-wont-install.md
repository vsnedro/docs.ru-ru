---
title: 'Устранение неполадок: невозможно установить приложение-службу'
description: Устраните неполадки, если невозможно установить приложение-службу. Убедитесь, что свойству ServiceName для класса службы задано правильное значение.
ms.date: 03/30/2017
helpviewer_keywords:
- troubleshooting service applications
- services, troubleshooting
- services, debugging
- Windows NT services, troubleshooting
- troubleshooting NT services
- Windows Service applications, troubleshooting
ms.assetid: 45c48e2e-b97d-44bc-8896-14f328e0ce33
ms.openlocfilehash: d606adc7fddeb9f7e76a6974699c2455eda084b2
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2020
ms.locfileid: "91608885"
---
# <a name="troubleshooting-service-application-wont-install"></a>Устранение неполадок: невозможно установить приложение-службу
Если приложение-служба не устанавливается надлежащим образом, убедитесь, что для свойства <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> класса службы задано значение, которое отображается в установщике этой службы. Для правильной установки службы необходимо, чтобы эти значения совпадали.  
  
> [!NOTE]
> Сведения о ходе установки также можно найти в журналах установки.  
  
 Также убедитесь, что у вас не установлена другая служба с таким же именем. Для успешной установки необходимо, чтобы у каждой службы было уникальное имя.  
  
## <a name="see-also"></a>См. также

- [Знакомство с приложениями служб Windows](introduction-to-windows-service-applications.md)
