---
title: "コンパイラ エラー C2026 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2026"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2026"
ms.assetid: 8e64b6e1-b967-479b-be97-d12dc4a8e389
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C2026
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

文字列が大きすぎます。後ろの文字が切り捨てられました。  
  
 文字列の長さが 1 バイト文字で 16380 個の制限を超えています。  
  
 隣接する文字列を連結する場合、連結前の文字列の長さが 1 バイト文字で 16380 個を超えることはできません。  
  
 2048 文字の半分ぐらいの長さの Unicode 文字列でも、このエラーが生成されます。  
  
 文字列を次のように定義すると、C2026 エラーが生成されます。  
  
```  
char sz[] =  
"\  
imagine a really, really \  
long string here\  
";  
```  
  
 この文字列は、次のように分割できます。  
  
```  
char sz[] =  
"\  
imagine a really, really "  
"long string here\  
";  
```  
  
 例外的に大きなリテラル文字列 \(32 KB 以上\) は、カスタム リソースまたは外部ファイルに格納できます。  詳細については、「[新しいカスタム リソースまたはデータ リソースの作成](../../mfc/creating-a-new-custom-or-data-resource.md)」を参照してください。