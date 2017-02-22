---
title: "方法: データ パイプラインでトランスフォーマーを使用する | Microsoft Docs"
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
  - "transformer クラス、例"
  - "データ パイプライン、使用 (トランスフォーマーを) [同時実行ランタイム]"
  - "使用 (データ パイプラインでトランスフォーマーを) [同時実行ランタイム]"
ms.assetid: ca49cb3f-4dab-4b09-a9c9-d3a109ae4c29
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# 方法: データ パイプラインでトランスフォーマーを使用する
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このトピックでは、データ パイプラインで [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md) クラスを使用する方法の基本的な例について説明します。  データ パイプラインを使用してイメージ処理を実行する方法をより詳しく示した例については、「[チュートリアル: イメージ処理ネットワークの作成](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)」を参照してください。  
  
 *データのパイプライン処理*は、同時実行プログラミングにおける一般的なパターンです。  データ パイプラインは一連のステージで構成され、各ステージで処理を実行し、その処理の結果を次のステージに渡します。  `transformer` クラスは、入力値を受け取り、その値に対して処理を実行し、別のコンポーネントで使用する結果を生成するため、データ パイプラインにおいて重要なコンポーネントとなっています。  
  
## 使用例  
 この例では、次のデータ パイプラインを使用して、渡される初期入力値に対して一連の変換を実行します。  
  
1.  最初のステージは、入力の絶対値を計算します。  
  
2.  2 番目のステージは、入力の平方根を計算します。  
  
3.  3 番目のステージは、入力の 2 乗を計算します。  
  
4.  4 番目のステージは、入力の符号を反転します。  
  
5.  5 番目のステージは、最終的な結果をメッセージ バッファーに書き込みます。  
  
 最後に、この例はパイプラインの結果をコンソールに出力します。  
  
 [!code-cpp[concrt-data-pipeline#1](../../parallel/concrt/codesnippet/CPP/how-to-use-transformer-in-a-data-pipeline_1.cpp)]  
  
 この例を実行すると、次の出力が生成されます。  
  
  **The result is \-42.** 一般に、データ パイプラインのステージは、入力値と異なる種類の値を出力します。  この例では、2 番目のステージは入力として `int` 型の値を取得し、出力としてその値の平方根 \(`double` 型\) を生成します。  
  
> [!NOTE]
>  この例のデータ パイプラインは、例示のみを目的としています。  各変換操作での処理量が少ないため、メッセージ パッシングを実行するのに必要なオーバーヘッドがデータ パイプラインを使用するメリットを上回る場合があります。  
  
## コードのコンパイル  
 コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、`data-pipeline.cpp` という名前のファイルに貼り付けてから、Visual Studio のコマンド プロンプト ウィンドウで次のコマンドを実行します。  
  
 **cl.exe \/EHsc data\-pipeline.cpp**  
  
## 参照  
 [非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)   
 [非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)   
 [チュートリアル: イメージ処理ネットワークの作成](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)