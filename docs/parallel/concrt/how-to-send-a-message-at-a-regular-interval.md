---
title: "方法: メッセージを定期的に送信する | Microsoft Docs"
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
  - "timer クラス、例"
  - "送信 (メッセージを定期的に) [同時実行ランタイム]"
ms.assetid: 4b60ea6c-97c8-4d69-9f7b-ad79f3548026
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# 方法: メッセージを定期的に送信する
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

この例は、同時実行を使用する方法を示します::[timer クラス](../../parallel/concrt/reference/timer-class.md) 一定の間隔でメッセージを送信します。  
  
## <a name="example"></a>例  
 次の例では、`timer` オブジェクトを使用して、時間のかかる操作中に進行状況を報告します。 この例のリンク、 `timer` オブジェクトを [concurrency::call](../../parallel/concrt/reference/call-class.md) オブジェクトです。 `call` オブジェクトは、プログレス インジケーターをコンソールに定期的に出力します。  [::Start](../Topic/timer::start%20Method.md) メソッドは、タイマーを独立したコンテキストで実行します。  `perform_lengthy_operation` 関数呼び出し、 [concurrency::wait](../Topic/wait%20Function.md) 時間のかかる操作をシミュレートするために、メインのコンテキストで機能します。  
  
 [!code-cpp[concrt-report-progress#1](../../parallel/concrt/codesnippet/CPP/how-to-send-a-message-at-a-regular-interval_1.cpp)]  
  
 この例では、次のサンプル出力が生成されます。  
  
```Output  
Performing a lengthy operation..........done.  
```  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 コード例をコピーし、Visual Studio プロジェクトに貼り付けるかという名前のファイルに貼り付けます `report-progress.cpp` Visual Studio コマンド プロンプト ウィンドウで、次のコマンドを実行します。  
  
 **cl.exe/EHsc report-progress.cpp**  
  
## <a name="see-also"></a>関連項目  
 [非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)   
 [非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)   
 [メッセージ パッシング関数](../../parallel/concrt/message-passing-functions.md)
