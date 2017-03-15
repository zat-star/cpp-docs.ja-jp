---
title: "コンパイラの警告 (レベル 1) C4788 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4788"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4788"
ms.assetid: 47d75bda-f833-4bdd-93a0-a134df0cd303
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# コンパイラの警告 (レベル 1) C4788
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'識別子' : 識別子は '数値' 文字に切り詰められました  
  
 コンパイラによって、関数名に使用できる最大文字数が制限されます。  コンパイラは EH\/SEH コードの funclet を生成するときに、関数名とテキスト \("\_\_catch"、"\_\_unwind"、その他の文字列など\) を先頭に付けて funclet 名を作成します。  
  
 作成された funclet 名が長すぎる場合、コンパイラはこれを切り捨てて C4788 を生成します。  
  
 この警告を解決するには、元の関数名を短くします。  関数が C\+\+ テンプレート関数またはメソッドの場合は、名前の一部に typedef を使用します。  たとえば、次のようになります。  
  
```  
C1<x, y, z<T>>::C2<a,b,c>::f  
```  
  
 これは次のように置換されます。  
  
```  
typedef C1<x, y, z<T>>::C2<a,b,c> new_class ;  
new_class::f  
```  
  
 この警告は [!INCLUDE[vcprx64](../Token/vcprx64_md.md)] コンパイラでのみ出力されます。