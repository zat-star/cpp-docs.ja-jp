---
title: "コンパイラ エラー C2086 | Microsoft Docs"
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
  - "C2086"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2086"
ms.assetid: 4329bf72-90c8-444c-8524-4ef75e6b2139
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2086
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 再定義されました。  
  
 識別子が 2 回以上定義されているか、この識別子の 2 つ以上の宣言が互いに異なっています。  
  
 C\# 参照アセンブリをインクリメンタル ビルドしたことが原因で C2086 が発生することもあります。  このエラーを解決するには、C\# アセンブリをビルドし直します。  
  
 次の例では警告 C2086 が生成されます。  
  
```  
// C2086.cpp  
main() {  
  int a;  
  int a;   // C2086 not an error in ANSI C  
}  
```