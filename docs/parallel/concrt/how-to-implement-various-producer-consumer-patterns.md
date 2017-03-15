---
title: "方法: さまざまなプロデューサー/コンシューマー パターンを実装する | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "プロデューサー/コンシューマー パターン、実装 [同時実行ランタイム]"
  - "実装 (プロデューサー/コンシューマー パターンを) [同時実行ランタイム]"
ms.assetid: 75f2c7cc-5399-49ea-98eb-847fe6747169
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# 方法: さまざまなプロデューサー/コンシューマー パターンを実装する
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ここでは、アプリケーションにプロデューサー\/コンシューマー パターンを実装する方法について説明します。  このパターンでは、*プロデューサー*がメッセージをメッセージ ブロックに送信し、*コンシューマー*がそのブロックからメッセージを読み取ります。  
  
 このトピックでは、2 つのシナリオに従って説明します。  最初のシナリオでは、コンシューマーはプロデューサーが送信した各メッセージを受信する必要があります。  2 番目のシナリオでは、コンシューマーは定期的にデータをポーリングします。そのため、各メッセージを受信する必要はありません。  
  
 このトピックのどちらの例も、エージェント、メッセージ ブロック、およびメッセージ パッシング関数を使用して、メッセージをプロデューサーからコンシューマーに転送します。  プロデューサー エージェントは、[concurrency::send](../Topic/send%20Function.md) 関数を使用して、メッセージを [concurrency::ITarget](../../parallel/concrt/reference/itarget-class.md) オブジェクトに書き込みます。  コンシューマー エージェントは、[concurrency::receive](../Topic/receive%20Function.md) 関数を使用して、[concurrency::ISource](../../parallel/concrt/reference/isource-class.md) オブジェクトからメッセージを読み取ります。  どちらのエージェントにも、処理の終了を調整するための sentinel 値が保持されます。  
  
 非同期エージェントの詳細については、「[非同期エージェント](../../parallel/concrt/asynchronous-agents.md)」を参照してください。  メッセージ ブロックおよびメッセージ パッシング関数の詳細については、「[非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)」および「[メッセージ パッシング関数](../../parallel/concrt/message-passing-functions.md)」を参照してください。  
  
## 使用例  
 この例では、プロデューサー エージェントは一連の数字をコンシューマー エージェントに送信します。  コンシューマーはこれらの各数字を受け取り、その平均を計算します。  アプリケーションはその平均をコンソールに出力します。  
  
 この例では、[concurrency::unbounded\_buffer](../Topic/unbounded_buffer%20Class.md) オブジェクトを使用して、プロデューサーがメッセージをキューに配置できるようにします。  `unbounded_buffer` クラスに、`ITarget` および `ISource` を実装して、プロデューサーおよびコンシューマーと共有バッファーとの間でメッセージを送受信できるようにします。  `send` 関数および `receive` 関数で、プロデューサーからコンシューマーにデータを伝達するタスクを調整します。  
  
 [!code-cpp[concrt-producer-consumer-average#1](../../parallel/concrt/codesnippet/CPP/how-to-implement-various-producer-consumer-patterns_1.cpp)]  
  
 この例を実行すると、次の出力が生成されます。  
  
  **The average is 50.**   
## 使用例  
 この例では、プロデューサー エージェントは一連の株式相場をコンシューマー エージェントに送信します。  コンシューマー エージェントは定期的に現在の相場を読み取り、それをコンソールに出力します。  
  
 この例は前の例に似ていますが、[concurrency::overwrite\_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) オブジェクトを使用して、プロデューサーがコンシューマーと 1 つのメッセージを共有できるようにする点が異なります。  前の例と同様に、`overwrite_buffer` クラスに、`ITarget` および `ISource` を実装して、プロデューサーおよびコンシューマーが共有メッセージ バッファーを操作できるようにします。  
  
 [!code-cpp[concrt-producer-consumer-quotes#1](../../parallel/concrt/codesnippet/CPP/how-to-implement-various-producer-consumer-patterns_2.cpp)]  
  
 この例では、次のサンプル出力が生成されます。  
  
  **Current quote is 24.44.**  
**Current quote is 24.44.**  
**Current quote is 24.65.**  
**Current quote is 24.99.**  
**Current quote is 23.76.**  
**Current quote is 22.30.**  
**Current quote is 25.89.** `unbounded_buffer` オブジェクトとは異なり、`receive` 関数によって、`overwrite_buffer` オブジェクトからメッセージが削除されることはありません。  プロデューサーがメッセージを上書きする前に、コンシューマーがメッセージ バッファーから 2 回以上読み取りを行った場合、コンシューマーは毎回同じメッセージを取得します。  
  
## コードのコンパイル  
 コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、`producer-consumer.cpp` という名前のファイルに貼り付けてから、Visual Studio のコマンド プロンプト ウィンドウで次のコマンドを実行します。  
  
 **cl.exe \/EHsc producer\-consumer.cpp**  
  
## 参照  
 [非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)   
 [非同期エージェント](../../parallel/concrt/asynchronous-agents.md)   
 [非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)   
 [メッセージ パッシング関数](../../parallel/concrt/message-passing-functions.md)