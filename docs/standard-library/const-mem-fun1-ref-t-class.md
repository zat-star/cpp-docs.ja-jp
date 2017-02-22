---
title: "const_mem_fun1_ref_t クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::const_mem_fun1_ref_t"
  - "std.const_mem_fun1_ref_t"
  - "xfunctional/std::const_mem_fun1_ref_t"
  - "const_mem_fun1_ref_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "const_mem_fun1_ref_t クラス"
ms.assetid: 8220d373-fa1c-44be-a21d-96d49b3ea6bb
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# const_mem_fun1_ref_t クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

参照引数と初期化された場合二項関数オブジェクトとして呼び出される一つの引数を受け取り **const** メンバー関数を可能にするアダプター クラスです。  
  
## 構文  
  
```  
template<class Result, class Type, class Arg>  
   class const_mem_fun1_ref_t  
      : public binary_function<Type, Arg, Result> {  
   explicit const_mem_fun1_ref_t( Result (Type::*_Pm )( Arg ) const );  
   Result operator()(  
      const Type& _Left,  
      Arg _Right  
   ) const;  
   };  
```  
  
#### パラメーター  
 `_Pm`  
 関数オブジェクトに変換する **\[種類\]** クラスのメンバー関数へのポインター。  
  
 `_Left`  
 `_Pm` のメンバー関数を呼び出すこと **const** オブジェクト。  
  
 `_Right`  
 `_Pm`に指定する引数。  
  
## 戻り値  
 最適なバイナリ関数。  
  
## 解説  
 このテンプレート クラスは、プライベート メンバー オブジェクトのクラス **\[種類\]** のメンバー関数へのポインターである `_Pm`のコピーを保存します。  これは、返されるとメンバー関数 `operator()` を定義します \(`_Left`。 *\_Pm*\) \* \(`_Right`\) **const**。  
  
## 使用例  
 `const_mem_fun1_ref_t` のコンストラクターは、通常、直接使用できません; ヘルパー関数 `mem_fun_ref` がメンバー関数を適応させるために使用されます。  メンバー関数アダプターを使用する方法の例については [mem\_fun\_ref](../Topic/mem_fun_ref%20Function.md) を参照してください。  
  
## 必要条件  
 **ヘッダー:** \<functional\>  
  
 **名前空間:** std  
  
## 参照  
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)