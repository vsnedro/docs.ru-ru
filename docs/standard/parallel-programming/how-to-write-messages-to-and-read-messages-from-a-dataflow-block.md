---
title: Практическое руководство. Запись и чтение сообщений в блоке потока данных
ms.date: 09/10/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, reading and writing messages
ms.assetid: 1a9bf078-aa82-46eb-b95a-f87237f028c5
ms.openlocfilehash: be0e78989105cc59bd041ceb8c6f31073a702f83
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94820791"
---
# <a name="how-to-write-and-read-messages-from-a-dataflow-block"></a>Практическое руководство. Запись и чтение сообщений в блоке потока данных

В этой статье описываются способы использования библиотеки потоков данных TPL для записи сообщений в блок потока данных и считывания сообщений из него. Библиотека потоков данных TPL предоставляет как синхронные, так и асинхронные методы для записи сообщений в блок потока данных и чтения сообщений из него. В этой статье показано, как использовать класс <xref:System.Threading.Tasks.Dataflow.BufferBlock%601?displayProperty=nameWithType>. Класс <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> помещает сообщения в буфер и работает и в качестве источника сообщений, и как адресат сообщения.

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="writing-and-reading-synchronously"></a>Синхронные запись и чтение

В следующем примере используется метод <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> для записи в блок потока данных <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> и метод <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A> для чтения из того же объекта.

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs" id="2":::
:::code language="vb" source="../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb" id="2":::

Можно также использовать метод <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> для чтения из блока потока данных, как показано в следующем примере. Метод <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> не блокирует текущий поток и удобен, если необходимо периодически запрашивать данные.

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs" id="3":::
:::code language="vb" source="../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb" id="3":::

Поскольку метод <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> действует синхронно, объект <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> в предыдущих примерах получает все данные, прежде чем второй цикл считывает данные. Следующий пример расширяет первый пример путем использования <xref:System.Threading.Tasks.Task.WhenAll(System.Threading.Tasks.Task[])?displayProperty=nameWithType> для чтения и записи в блок сообщений в параллельном режиме. Поскольку <xref:System.Threading.Tasks.Task.WhenAll%2A> выполняет действия параллельно, значения не записываются в объект <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> в каком-либо определенном порядке.

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs" id="4":::
:::code language="vb" source="../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb" id="4":::

## <a name="writing-and-reading-asynchronously"></a>Асинхронные запись и чтение

В следующем примере используется метод <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A> для асинхронной записи в объект <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> и метод <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A> для асинхронного чтения из того же объекта. В этом образце используются операторы [async](../../csharp/language-reference/keywords/async.md) и [await](../../csharp/language-reference/operators/await.md) ([Async](../../visual-basic/language-reference/modifiers/async.md) и [Await](../../visual-basic/language-reference/operators/await-operator.md) в Visual Basic) для асинхронной передачи данных и считывания их из блока целевого объекта. Метод <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A> рекомендуется, если необходимо обеспечить возможность использования отложенных сообщений для потока данных. Метод <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A> полезен для использования, если вы собираетесь работать с данными, когда они становятся доступны. Дополнительные сведения о распространении сообщений среди блоков сообщений см. в разделе "Передача сообщений" документа [Поток данных](dataflow-task-parallel-library.md).

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs" id="5":::
:::code language="vb" source="../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb" id="5":::

## <a name="a-complete-example"></a>Полный пример

В следующем примере показан весь код для этой статьи.

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs" id="1":::
:::code language="vb" source="../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb" id="1":::

## <a name="next-steps"></a>Дальнейшие шаги

В этом примере показано, как считывать и записывать в блок сообщений напрямую. Можно также подключить блоки потока данных для создания *конвейеров*, которые являются линейными последовательностями блоков потока данных, или *сетей*, являющихся графами блоков потоков данных. Конвейеры или сети асинхронно распространяют исходные данные целевым объектам, когда данные становятся доступны. Пример, в котором создается базовый конвейер потока данных, см. в разделе [Пошаговое руководство. Создание конвейера потока данных](walkthrough-creating-a-dataflow-pipeline.md). Пример создания более комплексной сети потока данных см. в разделе [Пошаговое руководство. Использование потоков данных в приложении Windows Forms](walkthrough-using-dataflow-in-a-windows-forms-application.md).

## <a name="see-also"></a>См. также раздел

- [Поток данных (библиотека параллельных задач)](dataflow-task-parallel-library.md)
