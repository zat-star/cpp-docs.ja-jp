---
title: "コンパイラ エラー C2970 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2970"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2970"
ms.assetid: 21d90348-20d3-438c-b278-efdbfb93a7d2
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C2970
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class' : テンプレート パラメーター 'param' : 'arg' : 内部リンケージがあるオブジェクトを含む表現を、非型引数として使用することはできません。  
  
 **static** 変数の名前またはアドレスは、テンプレートの引数に使用できません。  テンプレート クラスには、コンパイル時に評価できる定数値を渡す必要があります。  
  
 次の例では警告 C2970 が生成されます。  
  
```  
// C2970.cpp  
// compile with: /c  
static int si;  
// could declare nonstatic to resolve all errors  
// int si;  
  
template <int i>   
class X {};  
  
template <int *pi>   
class Y {};  
  
X<si> anX;   // C2970 cannot use static variable in templates  
  
// this would also work  
const int i = 10;  
X<i> anX2;  
```