---
title: "value_compare クラス (&lt;map&gt;) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::value_compare"
  - "std.value_compare"
  - "map/std::value_compare"
  - "value_compare"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "value_compare クラス"
ms.assetid: ea97c1d0-04b2-4d42-8d96-23522c04cc41
caps.latest.revision: 21
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# value_compare クラス (&lt;map&gt;)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

マップの相対順序を決定するためのキーの値を比較してマップ要素を比較できる関数オブジェクトを提供します。  
  
## 構文  
  
```  
class value_compare : public binary_function<value_type, value_type, bool>  
{  
public:  
   bool operator()(const value_type& _Left, const value_type& _Right) const;  
   value_compare(key_compare _Pred) : comp(_Pred);  
   protected:  
      key_compare comp;  
};  
```  
  
## 解説  
 マップに含まれる要素全体の **value\_types** 間の `value_compare` に用意されている比較の条件は、補助クラスの構築によって各要素のキーの違いから強制的に実行されます。  メンバー関数の演算子は 2 要素の主要部分を比較するに `value_compare` に用意されている関数オブジェクトに格納されている型 `key_compare` オブジェクト **コンポーネント** を使用します。  
  
 キー値が要素の値と同一の単純なコンテナーのマルチセット、設定については、`value_compare` は `key_compare`;と同じです。マップと multimaps 用には型の `pair` 要素の値が要素のキー値と一致しないため、ありません。  
  
## 使用例  
 `value_compare`を宣言および使用する方法の例に [value\_comp](../Topic/map::value_comp.md) "の例を参照してください。  
  
## 必要条件  
 **ヘッダー:** \<map\>  
  
 **名前空間:** std  
  
## 参照  
 [binary\_function 構造体](../Topic/binary_function%20Struct.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)