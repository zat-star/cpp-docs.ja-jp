---
title: "const_mem_fun_t クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "const_mem_fun_t"
  - "std.const_mem_fun_t"
  - "xfunctional/std::const_mem_fun_t"
  - "std::const_mem_fun_t"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "const_mem_fun_t クラス"
ms.assetid: f169d381-019b-4a0e-a9a3-54da6d948270
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# const_mem_fun_t クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

参照引数による初期化を行うときに、引数を使用しない const メンバー関数を単項関数オブジェクトとして呼び出せるようにするアダプター クラス。  
  
## 構文  
  
```  
template<class Result, class Type>  
   class const_mem_fun_t : public unary_function <Type *, Result>   
   {  
   explicit const_mem_fun_t( Result ( Type::* _Pm )( ) const );  
   Result operator()(  
      const Type* _Pleft  
   ) const;  
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
 このテンプレート クラスは、プライベート メンバー オブジェクトのクラス **\[種類\]** のメンバー関数へのポインターである `_Pm`のコピーを保存します。  これは、`_Pleft`\-\>`_Pm` \(\*\) \(\) **const**とメンバー関数 `operator()` を定義します。  
  
## 使用例  
 `const_mem_fun_t` のコンストラクターは、通常、直接使用できません; ヘルパー関数 `mem_fun` がメンバー関数を適応させるために使用されます。  メンバー関数アダプターを使用する方法の例については、" [mem\_fun](../Topic/mem_fun%20Function.md) を参照してください。  
  
## 必要条件  
 **ヘッダー:** \<functional\>  
  
 **名前空間:** std  
  
## 参照  
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [標準テンプレート ライブラリ](../misc/standard-template-library.md)