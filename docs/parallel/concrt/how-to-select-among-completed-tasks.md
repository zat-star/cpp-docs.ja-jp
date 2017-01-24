---
title: "方法: 完了したタスクから選択する | Microsoft Docs"
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
  - "選択 (完了したタスクを) [同時実行ランタイム]"
  - "完了したタスク、選択 [同時実行ランタイム]"
ms.assetid: c8ccc160-043f-4599-847b-32ed270bb257
caps.latest.revision: 17
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: 完了したタスクから選択する
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

この例では、[concurrency::choice](../../parallel/concrt/reference/choice-class.md) クラスおよび [concurrency::join](../Topic/join%20Class.md) クラスを使用して、最初のタスクを選択して検索アルゴリズムを完了する方法について説明します。  
  
## 使用例  
 次の例では 2 つの検索アルゴリズムを並列で実行し、最初のアルゴリズムを選択して完了します。  この例では、従業員の数値 ID と給与を格納する `employee` 型を定義します。  `find_employee` 関数は、指定された ID と指定された給与に該当する最初の従業員を検索します。  また、`find_employee` 関数は、指定された ID または指定された給与に該当する従業員がいない場合の処理も行います。  `wmain` 関数は、`employee` オブジェクトの配列を作成して複数の ID および給与の値を検索します。  
  
 次の例では、`choice` オブジェクトを使用して、次の事例を選択します。  
  
1.  指定された ID を持つ従業員。  
  
2.  指定された給与の従業員。  
  
3.  指定された ID または給与に該当しない従業員。  
  
 最初の 2 つの事例の場合、この例は [concurrency::single\_assignment](../../parallel/concrt/reference/single-assignment-class.md) オブジェクトを使用して ID を保持し、別の `single_assignment` オブジェクトを使用して給与を保持します。  この例は、3 番目の事例に対して `join` オブジェクトを使用します。  `join` オブジェクトは、2 つの別の `single_assignment` オブジェクトで構成されます。1 つは、指定された ID を持つ従業員がいない事例に使用し、もう 1 つは指定された給与に該当する従業員がいない事例に使用します。  `join` オブジェクトは、その各メンバーがメッセージを受信したときにメッセージを送信します。  この例では、`join` オブジェクトは、指定された ID または給与に該当する従業員がいない場合にメッセージを送信します。  
  
 この例は、[concurrency::structured\_task\_group](../../parallel/concrt/reference/structured-task-group-class.md) オブジェクトを使用して両方の検索アルゴリズムを並列で実行します。  各検索タスクが、指定された従業員が存在するかどうかを示す値を `single_assignment` オブジェクトの 1 つに書き込みます。  この例は、[concurrency::receive](../Topic/receive%20Function.md) 関数を使用して、メッセージおよび結果を出力する `switch` ブロックを格納する最初のバッファーのインデックスを取得します。  
  
 [!code-cpp[concrt-find-employee#1](../../parallel/concrt/codesnippet/CPP/how-to-select-among-completed-tasks_1.cpp)]  
  
 この例を実行すると、次の出力が生成されます。  
  
  **Employee with id 14758 has salary 27780.00.**  
**Employee with salary 29150.00 has id 84345.**  
**Employee with id 61935 has salary 29905.00.**  
**No employee has id 899 or salary 31223.00.** この例は、[concurrency::make\_choice](../Topic/make_choice%20Function.md) ヘルパー関数を使用して `choice` オブジェクトを作成し、[concurrency::make\_join](../Topic/make_join%20Function.md) ヘルパー関数を使用して `join` オブジェクトを作成します。  
  
## コードのコンパイル  
 コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、`find-employee.cpp` という名前のファイルに貼り付けてから、Visual Studio のコマンド プロンプト ウィンドウで次のコマンドを実行します。  
  
 **cl.exe \/EHsc find\-employee.cpp**  
  
## 参照  
 [非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)   
 [非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)   
 [メッセージ パッシング関数](../../parallel/concrt/message-passing-functions.md)   
 [choice クラス](../../parallel/concrt/reference/choice-class.md)   
 [join クラス](../Topic/join%20Class.md)