---
title: "方法: マップ操作と縮小操作を並列実行する | Microsoft Docs"
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
  - "parallel_transform 関数の使用例"
  - "parallel_map および使用例を削減します。"
  - "parallel_reduce 関数の使用例"
ms.assetid: 9d19fac0-4ab6-4380-a375-3b18eeb87720
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# 方法: マップ操作と縮小操作を並列実行する
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

この例は、使用する方法を示しています。、 [:parallel_transform](../Topic/parallel_transform%20Function.md) と [concurrency::parallel_reduce](../Topic/parallel_reduce%20Function.md) アルゴリズムと [concurrency::concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md) ファイル内の単語の出現回数をカウントするクラス。  
  
 A *マップ* 操作は、シーケンス内の各値には、関数を適用します。 A *削減* 操作が単一の値のシーケンスの要素を連結します。 標準テンプレート ライブラリ (STL) を使用する [std::transform](../Topic/transform.md)[:accumulate](../Topic/accumulate.md) クラスをマップを実行し、操作を減らすためです。 ただし、多くの問題のパフォーマンスを向上させるために、`parallel_transform` アルゴリズムを使用して map 操作を並列実行し、`parallel_reduce` アルゴリズムを使用して reduce 操作を並列実行することができます。 場合によっては、`concurrent_unordered_map` を使用して、1 つの操作で map と reduce を実行できます。  
  
## <a name="example"></a>例  
 次の例では、ファイル内の単語の出現回数をカウントします。 使用して [std::vector](../../standard-library/vector-class.md) を 2 つのファイルの内容を表します。 map 操作は、各ベクター内の各単語の出現回数を計算します。 reduce 操作は、両方のベクターのワード カウントを累積します。  
  
 [!code-cpp[concrt-parallel-map-reduce#1](../../parallel/concrt/codesnippet/CPP/how-to-perform-map-and-reduce-operations-in-parallel_1.cpp)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 コードをコンパイルするコピーし、Visual Studio プロジェクトに貼り付けるかという名前のファイルに貼り付ける `parallel-map-reduce.cpp` Visual Studio コマンド プロンプト ウィンドウで、次のコマンドを実行します。  
  
 **cl.exe/EHsc 並列-マップ-reduce.cpp**  
  
## <a name="robust-programming"></a>信頼性の高いプログラミング  
 この例では、concurrent_unordered_map.h で定義されている `concurrent_unordered_map` クラスを使用して、1 つの操作で map と reduce を実行できます。  
  
 [!code-cpp[concrt-parallel-map-reduce#2](../../parallel/concrt/codesnippet/CPP/how-to-perform-map-and-reduce-operations-in-parallel_2.cpp)]  
  
 通常、外側または内側のループのみ並列化します。 比較的ファイル数が少なく、各ファイルに含まれる単語が多い場合は、内側のループを並列化します。 比較的ファイル数が多く、各ファイルに含まれる単語が少ない場合は、外側のループを並列化します。  
  
## <a name="see-also"></a>「  
 [並列アルゴリズム](../Topic/Parallel%20Algorithms.md)   
 [parallel_transform 関数](../Topic/parallel_transform%20Function.md)   
 [parallel_reduce 関数](../Topic/parallel_reduce%20Function.md)   
 [concurrent_unordered_map クラス](../../parallel/concrt/reference/concurrent-unordered-map-class.md)
