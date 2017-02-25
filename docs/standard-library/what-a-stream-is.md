---
title: "ストリームとは何か | Microsoft Docs"
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
  - "データ [C++], 読み取り"
  - "読み取り (データを) [C++], iostream プログラミング"
  - "ストリーム [C++]"
  - "ストリーム [C++], iostream クラス内"
ms.assetid: a7e661e9-6cd1-4543-a9a4-c58ee9fd32f3
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# ストリームとは何か
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C のように、C\+\+ に組み込み入出力機能はありません。  ただし、すべての C\+\+ コンパイラは iostream クラスと呼ばれる体系的に、オブジェクト指向 I\/O パッケージと束ねられてされます。  ストリームは、iostream クラスの中間概念です。  バイトのソースとターゲットとして機能するスマート ファイルとしてストリーム オブジェクトと考えることができます。  ストリームの特性はクラスでカスタマイズされた挿入および抽出の演算子によって決まります。  
  
 デバイス ドライバーを通じて、ディスクのオペレーティング システムがキーボード、画面、プリンターや拡張ファイルとして通信ポートが処理されます。  iostream クラスは、これらの拡張ファイルと対話します。  組み込みクラスは、Stream クラスを派生するメソッドを使用すると、ディスク I\/O の場合と同じ構文でメモリに対する読み取りと書き込みをサポートします。  
  
## このセクションの内容  
 [入出力の代替手段](../standard-library/input-output-alternatives.md)  
  
## 参照  
 [iostream プログラミング](../Topic/iostream%20Programming.md)