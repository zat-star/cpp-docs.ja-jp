---
title: "メッセージ パッシング関数 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "メッセージ パッシング関数"
ms.assetid: 42477c9e-a8a6-4dc4-a98e-93c6dc8c4dd0
caps.latest.revision: 23
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# メッセージ パッシング関数
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

非同期エージェント ライブラリには、コンポーネント間でメッセージを渡すことのできる関数がいくつか用意されてします。  
  
 これらのメッセージ パッシング関数は、さまざまなメッセージ ブロックで使用されます。  同時実行ランタイムで定義されているメッセージ ブロックの種類の詳細については、「[非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)」を参照してください。  
  
##  <a name="top"></a> セクション  
 このトピックでは、次のメッセージ パッシング関数について説明します。  
  
-   [send および asend](#send)  
  
-   [receive および try\_receive](#receive)  
  
-   [例](#examples)  
  
##  <a name="send"></a> send および asend  
 [concurrency::send](../Topic/send%20Function.md) 関数は指定されたターゲットにメッセージを同期的に送信し、[concurrency::asend](../Topic/asend%20Function.md) 関数は指定されたターゲットにメッセージを非同期的に送信します。  `send` 関数と `asend` 関数は、いずれもターゲットがメッセージを最終的に受け入れるか拒否することを示すまで待機します。  
  
 `send` 関数は、ターゲットがメッセージを受け入れるか拒否するまで待機してから制御を返します。  `send` 関数は、メッセージが配信された場合は `true` を返し、それ以外の場合は `false` を返します。  `send` 関数は同期的に動作するため、`send` 関数は、ターゲットがメッセージを受信するのを待ってから制御を返します。  
  
 一方、`asend` 関数は、ターゲットがメッセージを受け入れるか拒否するのを待つことなく制御を返します。  代わりに、`asend` 関数は、ターゲットがメッセージを受け入れ、最終的にそれを受け取る場合に `true` を返します。  それ以外の場合、`asend` は `false` を返し、ターゲットがメッセージを拒否したか、メッセージを受け取るかどうかの決定を延期したことを示します。  
  
 \[[トップ](#top)\]  
  
##  <a name="receive"></a> receive および try\_receive  
 [concurrency::receive](../Topic/receive%20Function.md) と [concurrency::try\_receive](../Topic/try_receive%20Function.md) 関数が特定のソースからデータを読み取ります。  `receive` 関数はデータが使用できるようになるのを待ちますが、`try_receive` 関数は即座に制御を返します。  
  
 `receive` 関数は、データの処理を継続する必要がある場合に使用します。  `try_receive` 関数は、現在のコンテキストをブロックしてはならないか、データの処理を継続する必要がない場合に使用します。  
  
 \[[トップ](#top)\]  
  
##  <a name="examples"></a> 例  
 `send`、`asend`、および `receive` の各関数の使用例については、次のトピックを参照してください。  
  
-   [非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)  
  
-   [方法: さまざまなプロデューサー\/コンシューマー パターンを実装する](../../parallel/concrt/how-to-implement-various-producer-consumer-patterns.md)  
  
-   [方法: call クラスおよび transformer クラスに処理関数を提供する](../../parallel/concrt/how-to-provide-work-functions-to-the-call-and-transformer-classes.md)  
  
-   [方法: データ パイプラインでトランスフォーマーを使用する](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)  
  
-   [方法: 完了したタスクから選択する](../../parallel/concrt/how-to-select-among-completed-tasks.md)  
  
-   [方法: メッセージを定期的に送信する](../../parallel/concrt/how-to-send-a-message-at-a-regular-interval.md)  
  
-   [方法: メッセージ ブロック フィルターを使用する](../../parallel/concrt/how-to-use-a-message-block-filter.md)  
  
 \[[トップ](#top)\]  
  
## 参照  
 [非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)   
 [非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)   
 [send 関数](../Topic/send%20Function.md)   
 [asend 関数](../Topic/asend%20Function.md)   
 [receive 関数](../Topic/receive%20Function.md)   
 [try\_receive 関数](../Topic/try_receive%20Function.md)