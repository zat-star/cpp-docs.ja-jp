---
title: "複合ステートメント (ブロック) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "}"
  - "{"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ブロック, ブロックの概要"
  - "compound ステートメント"
ms.assetid: 23855939-7430-498e-8936-0c70055ea701
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 複合ステートメント (ブロック)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

複合ステートメントは、中かっこ \(**{}**\) で囲まれたゼロ個以上のステートメントから構成されます。  複合ステートメントは、ステートメントが想定される場所で使用できます。  複合ステートメントは一般に "ブロック" と呼ばれます。  
  
## 構文  
  
```  
  
{ [ statement-list ] }  
```  
  
## 解説  
 次の例は **if** ステートメントの *statement* 部分として複合ステートメントを使用します \(構文の詳細については「[IF ステートメント](../cpp/if-else-statement-cpp.md)」を参照\)。  
  
```  
if( Amount > 100 )  
{  
    cout << "Amount was too large to handle\n";  
    Alert();  
}  
else  
    Balance -= Amount;  
```  
  
> [!NOTE]
>  宣言はステートメントであるため、宣言は *statement\-list* のステートメントの 1 つです。  その結果、複合ステートメント内で宣言されているが、明示的に静的として宣言されていない名前には、ローカルなスコープと \(オブジェクトの場合\) 有効期間があります。  ローカル スコープの名前を処理する方法の詳細については、「[スコープ](../cpp/scope-visual-cpp.md)」を参照してください。  
  
## 参照  
 [C\+\+ ステートメントの概要](../cpp/overview-of-cpp-statements.md)