---
title: "コンパイラ エラー C2299 | Microsoft Docs"
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
  - "C2299"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2299"
ms.assetid: d001c2bc-f6fd-47aa-8e42-0eb824d6441d
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2299
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'関数' : 動作の変更: 明示的な特殊化には、コピー コンストラクターまたはコピー代入演算子を使用することはできません  
  
 このエラーは、Visual C\+\+ 2005 で行ったコンパイラ準拠作業の結果として生成されることもあります。以前のバージョンの Visual C\+\+ ではコピー コンストラクターまたはコピー代入演算子の明示的な特殊化が許可されていました。  
  
 C2299 を解決するには、コピー コンストラクターまたはコピー代入演算子をテンプレート関数にしないで、クラス型を使用する非テンプレート関数を使用します。  テンプレート引数を明示的に指定することによってコピー コンストラクターまたはコピー代入演算子を呼び出すコードでは、テンプレート引数を削除する必要があります。  
  
 次の例では警告 C2299 が生成されます。  
  
```  
// C2299.cpp  
// compile with: /c  
class C {  
   template <class T>  
   C (T t);  
  
   template <> C (const C&);   // C2299  
   C (const C&);   // OK  
};  
```