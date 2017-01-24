---
title: "mem_fun_t クラス | Microsoft Docs"
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
  - "mem_fun_t"
  - "xfunctional/std::mem_fun_t"
  - "std::mem_fun_t"
  - "std.mem_fun_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "mem_fun_t クラス"
ms.assetid: 242566d4-750c-4c87-9d63-2e2c9d19ca2a
caps.latest.revision: 19
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# mem_fun_t クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ポインター引数による初期化を行うときに、引数を使用しない **non\_const** メンバー関数を単項関数オブジェクトとして呼び出せるようにするアダプター クラス。  
  
## 構文  
  
```  
template<class Result, class Type>  
   class mem_fun_t : public unary_function<Type *, Result> {  
      explicit mem_fun_t(Result ( Type::*_Pm )( ) );  
      Result operator()( Type* _Pleft ) const;  
   };  
```  
  
#### パラメーター  
 `_Pm`  
 関数オブジェクトに変換する **\[種類\]** クラスのメンバー関数へのポインター。  
  
 `_Pleft`  
 `_Pm` のメンバー関数が要求するオブジェクト。  
  
## 戻り値  
 最適な単項関数。  
  
## 解説  
 このテンプレート クラスは、プライベート メンバー オブジェクトのクラス **\[種類\]** のメンバー関数へのポインターである `_Pm`のコピーを保存します。  これは、返されるとメンバー関数 `operator()` を定義します \(`_Pleft`\-\>\* `_Pm`\) \(\)。  
  
## 使用例  
 `mem_fun_t` のコンストラクターは、通常、直接使用できません; ヘルパー関数 `mem_fun` がメンバー関数を適応させるために使用されます。  メンバー関数アダプターを使用する方法の例については、" [mem\_fun](../Topic/mem_fun%20Function.md) を参照してください。  
  
## 必要条件  
 **ヘッダー:** \<functional\>  
  
 **名前空間:** std  
  
## 参照  
 [\<functional\>](../standard-library/functional.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)