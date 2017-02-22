---
title: "mem_fun1_ref_t クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "xfunctional/std::mem_fun1_ref_t"
  - "std::mem_fun1_ref_t"
  - "mem_fun1_ref_t"
  - "std.mem_fun1_ref_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "mem_fun1_ref_t クラス"
ms.assetid: 7d6742f6-19ba-4523-b3c8-0e5b8f11464f
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# mem_fun1_ref_t クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

参照引数による初期化を行うときに、1 つの引数を使用する **non\_const** メンバー関数を二項関数オブジェクトとして呼び出せるようにするアダプター クラス。  
  
## 構文  
  
```  
template<class Result, class Type, class Arg>  
   class mem_fun1_ref_t : public binary_function<Type, Arg, Result> {  
      explicit mem_fun1_ref_t(  
         Result (Type::* _Pm )( Arg )  
      );  
      Result operator()(  
         Type& _Left,   
         Arg _Right  
      ) const;  
   };  
```  
  
#### パラメーター  
 `_Pm`  
 関数オブジェクトに変換する **\[種類\]** クラスのメンバー関数へのポインター。  
  
 `_Left`  
 `_Pm` のメンバー関数が要求するオブジェクト。  
  
 `_Right`  
 `_Pm`に指定する引数。  
  
## 戻り値  
 最適なバイナリ関数。  
  
## 解説  
 このテンプレート クラスは、プライベート メンバー オブジェクトのクラス **\[種類\]** のメンバー関数へのポインターである `_Pm`のコピーを保存します。  これは、返されるとメンバー関数 `operator()` を定義します \(**\_Left**。`_Pm`\) \* \(**\_Right**\)。  
  
## 使用例  
 `mem_fun1_ref_t` のコンストラクターは、通常、直接使用できません; ヘルパー関数 `mem_fun_ref` がメンバー関数を適応させるために使用されます。  メンバー関数アダプターを使用する方法の例については、" [mem\_fun\_ref](../Topic/mem_fun_ref%20Function.md) を参照してください。  
  
## 必要条件  
 **ヘッダー:** \<functional\>  
  
 **名前空間:** std  
  
## 参照  
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)