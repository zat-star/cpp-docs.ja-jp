---
title: "コンパイラ エラー C2597 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2597"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2597"
ms.assetid: 2e48127d-e3ff-4a40-8156-2863e45b1a38
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2597
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

静的でないメンバー 'identifier' への参照が正しくありません。  
  
 以下の原因が考えられます。  
  
1.  静的でないメンバーが静的メンバー関数に指定されている。  静的でないメンバーにアクセスするには、クラスのローカル インスタンスを渡すかまたは作成し、メンバー アクセス演算子 \(`.` または `->`\) を使用する必要があります。  
  
2.  指定された識別子が、クラス、構造体、または共用体のメンバーではない。  識別子のスペルを確認します。  
  
3.  メンバー アクセス演算子が非メンバー関数を参照している。  
  
4.  次の例では、C2597 を生成し、その修正方法を示しています。  
  
```  
// C2597.cpp  
// compile with: /c  
struct s1 {  
   static void func();  
   static void func2(s1&);  
   int i;  
};  
  
void s1::func() {  
   i = 1;    // C2597 - static function can't access non-static data member  
}  
  
// OK - fix by passing an instance of s1  
void s1::func2(s1& a) {  
   a.i = 1;  
}  
  
```