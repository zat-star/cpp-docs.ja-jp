---
title: "コンパイル時のカプセル化の Pimpl (Modern C++) | Microsoft Docs"
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
ms.assetid: c3e8a90a-b328-4990-82bb-e1b147f76e07
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# コンパイル時のカプセル化の Pimpl (Modern C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*pimpl の表現は* 実装を非結合度を最小化し、インターフェイスを区切る最新の C\+\+ の手法です。  Pimpl は「実装へのポインターには短いです」。既に概念について理解チェシャー Cat またはコンパイラ ファイアウォール表現などの名前で指定がわからない場合があります。  
  
## 理由 pimpl を使用します。  
 ここで pimpl の表現がソフトウェア開発ライフサイクルを向上する方法です:  
  
-   コンパイル依存関係の最小化。  
  
-   インターフェイスおよび実装の分離。  
  
-   移植性。  
  
## Pimpl のヘッダー  
  
```cpp  
  
// my_class.h  
class my_class {  
   //  ... all public and protected stuff goes here ...  
private:  
   class impl; unique_ptr<impl> pimpl; // opaque type here  
};  
  
```  
  
 pimpl の表現はリビルドのカスケードと脆弱なオブジェクトのレイアウトを回避できます。  これは \(他動詞\) として使用される型の場合に適しています。  
  
## Pimpl の実装  
 .cpp ファイルで `impl` クラスを定義します。  
  
```cpp  
  
// my_class.cpp  
class my_class::impl {  // defined privately here  
  // ... all private data and functions: all of these  
  //     can now change without recompiling callers ...  
};  
my_class::my_class(): pimpl( new impl )  
{  
  // ... set impl values ...   
}  
```  
  
## ベスト プラクティス  
 検討非スローする交換の特殊化のサポートを追加するかどうか。  
  
## 参照  
 [C\+\+ へようこそ](../Topic/Welcome%20Back%20to%20C++%20\(Modern%20C++\).md)   
 [C\+\+ 言語リファレンス](../cpp/cpp-language-reference.md)   
 [C\+\+ 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)