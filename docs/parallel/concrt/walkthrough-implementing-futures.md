---
title: "チュートリアル: フューチャの実装 | Microsoft Docs"
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
  - "実装 (フューチャを) [同時実行ランタイム]"
  - "フューチャ、実装 [同時実行ランタイム]"
ms.assetid: 82ea75cc-aaec-4452-b10d-8abce0a87e5b
caps.latest.revision: 25
caps.handback.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# チュートリアル: フューチャの実装
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このトピックでは、アプリケーションにフューチャを実装する方法について説明します。 このトピックでは、同時実行ランタイムの既存の機能を組み合わせて、より効果的に使用する方法を示します。  
  
> [!IMPORTANT]
>  このトピックでは、デモンストレーションのために、将来の概念について説明します。 使用することをお勧め [std::future](../../standard-library/future-class.md) または [concurrency::task](../../parallel/concrt/reference/task-class-concurrency-runtime.md) 、後で使用できる値を計算する非同期タスクを必要とする場合。  
  
 A *タスク* が追加より細かい計算に分解しを計算します。 A *将来* 後で使用できる値を計算する非同期タスクです。  
  
 フューチャを実装するために、このトピックでは `async_future` クラスを定義します。  `async_future` クラスは同時実行ランタイムのこれらのコンポーネントを使用して: [concurrency::task_group](../Topic/task_group%20Class.md) クラスおよび [concurrency::single_assignment](../../parallel/concrt/reference/single-assignment-class.md) クラスです。 `async_future` クラスは、`task_group` クラスを使用して非同期的に値を計算し、`single_assignment` クラスを使用して計算結果を格納します。 `async_future` クラスのコンストラクターは、結果を計算する処理関数を受け取り、`get` メソッドが結果を取得します。  
  
### <a name="to-implement-the-asyncfuture-class"></a>async_future クラスを実装するには  
  
1.  計算結果の型でパラメーター化された `async_future` という名前のテンプレート クラスを宣言します。 このクラスに `public` セクションと `private` セクションを追加します。  
  
 [!code-cpp[concrt-futures#2](../../parallel/concrt/codesnippet/CPP/walkthrough-implementing-futures_1.cpp)]  
  
2.  `private` クラスの `async_future` セクションで、`task_group` と `single_assignment` データ メンバーを宣言します。  
  
 [!code-cpp[concrt-futures#3](../../parallel/concrt/codesnippet/CPP/walkthrough-implementing-futures_2.cpp)]  
  
3.  `public` クラスの `async_future` セクションで、コンストラクターを実装します。 コンストラクターは、結果を計算する処理関数でパラメーター化されたテンプレートです。 コンス トラクターに処理関数を非同期的に実行する、 `task_group` 使用してデータ メンバー、 [concurrency::send](../Topic/send%20Function.md) 関数に結果の書き込み、 `single_assignment` データ メンバーです。  
  
 [!code-cpp[concrt-futures#4](../../parallel/concrt/codesnippet/CPP/walkthrough-implementing-futures_3.cpp)]  
  
4.  `public` クラスの `async_future` セクションで、デストラクターを実装します。 デストラクターはタスクが完了するまで待機します。  
  
 [!code-cpp[concrt-futures#5](../../parallel/concrt/codesnippet/CPP/walkthrough-implementing-futures_4.cpp)]  
  
5.  `public` クラスの `async_future` セクションで、`get` メソッドを実装します。 このメソッドを使用して、 [concurrency::receive](../Topic/receive%20Function.md) 処理関数の結果を取得します。  
  
 [!code-cpp[concrt-futures#6](../../parallel/concrt/codesnippet/CPP/walkthrough-implementing-futures_5.cpp)]  
  
## <a name="example"></a>例  
  
### <a name="description"></a>説明  
 完全な `async_future` クラスとその使用例を次に示します。  `wmain` 関数を作成、std::[ベクトル](../../standard-library/vector-class.md) 10,000 個のランダムな整数値を格納しているオブジェクト。 次に `async_future` オブジェクトを使用して、`vector` オブジェクト内の最小値と最大値を見つけます。  
  
### <a name="code"></a>コード  
 [!code-cpp[concrt-futures#1](../../parallel/concrt/codesnippet/CPP/walkthrough-implementing-futures_6.cpp)]  
  
### <a name="comments"></a>コメント  
 この例を実行すると、次の出力が生成されます。  
  
```Output  
smallest: 0  
largest:  9999  
average:  4981  
```  
  
 この例では `async_future::get` メソッドを使用して、計算の結果を取得しています。 `async_future::get` メソッドは、計算がアクティブな場合は、計算が完了するまで待機します。  
  
## <a name="robust-programming"></a>信頼性の高いプログラミング  
 拡張する、 `async_future` 処理関数によってスローされる例外を処理する、変更するクラス、 `async_future::get` メソッドを呼び出す、 [:wait](../Topic/task_group::wait%20Method.md) メソッドです。 `task_group::wait` メソッドは、処理関数によって生成されたすべての例外をスローします。  
  
 `async_future` クラスを変更した例を次に示します。  `wmain` 関数は、 `try`-`catch` ブロックの結果を出力する、 `async_future` オブジェクトまたは処理関数によって生成される例外の値を出力します。  
  
 [!code-cpp[concrt-futures-with-eh#1](../../parallel/concrt/codesnippet/CPP/walkthrough-implementing-futures_7.cpp)]  
  
 この例を実行すると、次の出力が生成されます。  
  
```Output  
caught exception: error  
```  
  
 同時実行ランタイムで例外処理モデルの詳細については、次を参照してください。 [例外処理](../Topic/Exception%20Handling%20in%20the%20Concurrency%20Runtime.md)します。  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 コード例をコピーし、Visual Studio プロジェクトに貼り付けるかという名前のファイルに貼り付けます `futures.cpp` Visual Studio コマンド プロンプト ウィンドウで、次のコマンドを実行します。  
  
 **cl.exe/EHsc futures.cpp**  
  
## <a name="see-also"></a>関連項目  
 [同時実行ランタイムのチュートリアル](../Topic/Concurrency%20Runtime%20Walkthroughs.md)   
 [例外処理](../Topic/Exception%20Handling%20in%20the%20Concurrency%20Runtime.md)   
 [task_group クラス](../Topic/task_group%20Class.md)   
 [single_assignment クラス](../../parallel/concrt/reference/single-assignment-class.md)
