---
title: "方法: call クラスおよび transformer クラスに処理関数を提供する | Microsoft Docs"
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
  - "call クラス、例"
  - "使用 (transformer クラスを) [同時実行ランタイム]"
  - "使用 (call クラスを) [同時実行ランタイム]"
ms.assetid: df715ce4-8507-41ca-b204-636d11707a73
caps.latest.revision: 15
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: call クラスおよび transformer クラスに処理関数を提供する
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ここでは、[concurrency::call](../../parallel/concrt/reference/call-class.md) クラスおよび [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md) クラスに処理関数を提供するいくつかの方法について説明します。  
  
 最初の例では、ラムダ式を `call` オブジェクトに渡す方法を示します。  2 番目の例では、関数オブジェクトを `call` オブジェクトに渡す方法を示します。  3 番目の例では、クラス メソッドを `call` オブジェクトにバインドする方法を示します。  
  
 このトピックの説明では、すべての例で `call` クラスを使用します。  `transformer` クラスの使用例については、「[方法: データ パイプラインでトランスフォーマーを使用する](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)」を参照してください。  
  
## 使用例  
 次の例は、`call` クラスを使用する一般的な方法を示しています。  この例は、ラムダ関数を `call` コンストラクターに渡します。  
  
 [!code-cpp[concrt-call-lambda#1](../../parallel/concrt/codesnippet/CPP/how-to-provide-work-functions-to-the-call-and-transformer-classes_1.cpp)]  
  
 この例を実行すると、次の出力が生成されます。  
  
  **13 squared is 169.**   
## 使用例  
 次の例は前の例に似ていますが、関数オブジェクト \(ファンクタ\) と共に `call` クラスを使用する点が異なります。  
  
 [!code-cpp[concrt-call-functor#1](../../parallel/concrt/codesnippet/CPP/how-to-provide-work-functions-to-the-call-and-transformer-classes_2.cpp)]  
  
## 使用例  
 次の例は前の例に似ていますが、[std::bind1st](../Topic/bind1st%20Function.md) 関数と [std::mem\_fun](../Topic/mem_fun%20Function.md) 関数を使用して `call` オブジェクトをクラス メソッドにバインドする点が異なります。  
  
 この方法は、関数呼び出し演算子 `operator()` ではなく、特定のクラス メソッドに `call` オブジェクトまたは `transformer` オブジェクトをバインドする必要がある場合に使用します。  
  
 [!code-cpp[concrt-call-method#1](../../parallel/concrt/codesnippet/CPP/how-to-provide-work-functions-to-the-call-and-transformer-classes_3.cpp)]  
  
 また、次の例に示すように、`bind1st` 関数の結果を [std::ffunction](../../standard-library/function-class.md) オブジェクトに割り当てるか、`auto` キーワードを使用することもできます。  
  
 [!code-cpp[concrt-call-method#2](../../parallel/concrt/codesnippet/CPP/how-to-provide-work-functions-to-the-call-and-transformer-classes_4.cpp)]  
  
## コードのコンパイル  
 コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、`call.cpp` という名前のファイルに貼り付けてから、Visual Studio のコマンド プロンプト ウィンドウで次のコマンドを実行します。  
  
 **cl.exe \/EHsc call.cpp**  
  
## 参照  
 [非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)   
 [非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)   
 [方法: データ パイプラインでトランスフォーマーを使用する](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)   
 [call クラス](../../parallel/concrt/reference/call-class.md)   
 [transformer クラス](../../parallel/concrt/reference/transformer-class.md)