---
title: "入力ストリーム | Microsoft Docs"
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
  - "データ [C++], 読み取り (入力ストリームから)"
  - "入力ストリーム オブジェクト"
  - "入力ストリーム"
  - "読み取り (データを) [C++], 入力ストリームから"
ms.assetid: f14d8954-8f8c-4c3c-8b99-14ddb3683f94
caps.latest.revision: 11
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 入力ストリーム
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

入力ストリーム オブジェクトは、バイトのソースです。  3 個の最も重要な入力ストリーム クラスは、[istream](http://msdn.microsoft.com/ja-jp/6801779e-260e-416d-b4ec-fef5ff1b2371)[ifstream](../Topic/ifstream.md)と [istringstream](../Topic/istringstream.md)です。  
  
 `istream` クラスは順次テキスト モードの入力に使用されます。  バッファリングまたはいない操作のクラス `istream` オブジェクトを構成できます。  基本クラス、`ios`のすべての機能は `istream`に含まれています。  まれに `istream`クラスからオブジェクトを作成しません。  代わりに、一般にクラス [ostream](../standard-library/ostream.md)オブジェクトである `cin` の定義済みのなオブジェクトを使用します。  場合によっては、プログラムの起動時に後で他のストリーム オブジェクトに `cin` を割り当てることができます。  
  
 `ifstream` クラスは、ディスク ファイルの入力をサポートします。  入力だけをディスク ファイルが必要な場合は、クラス `ifstream`オブジェクトを構築します。  バイナリまたはテキストモード データを指定できます。  コンストラクターにファイル名を指定すると、ファイルは自動的にオブジェクトを作成するときに表示されます。  それ以外の場合は、既定のコンストラクターを呼び出すと `open` 関数を使用できます。  さまざまな書式指定オプションとメンバー関数は `ifstream` にオブジェクトに適用されます。  基本クラス `ios` と `istream` のすべての機能は `ifstream`に含まれます。  
  
 `sscanf_s`ライブラリ関数と同様に、`istringstream` クラスは、メモリ内の文字列の入力をサポートします。  null 終端文字を持つ文字配列からデータを取得するには、割り当て、および文字列を初期化し、`istringstream`クラスのオブジェクトを構築します。  
  
## このセクションの内容  
 [入力ストリーム オブジェクトのコンストラクト](../Topic/Constructing%20Input%20Stream%20Objects.md)  
  
 [抽出演算子の使用](../Topic/Using%20Extraction%20Operators.md)  
  
 [抽出エラーのテスト](../standard-library/testing-for-extraction-errors.md)  
  
 [入力ストリーム マニピュレーター](../standard-library/input-stream-manipulators.md)  
  
 [入力ストリームのメンバー関数](../standard-library/input-stream-member-functions.md)  
  
 [独自クラスのための \>\> 演算子のオーバーロード](../standard-library/overloading-the-input-operator-for-your-own-classes.md)  
  
## 参照  
 [iostream プログラミング](../Topic/iostream%20Programming.md)