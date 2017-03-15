---
title: "コンパイラの警告 (レベル 1) C4364 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4364"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4364"
ms.assetid: 1477634c-d60f-4570-ad16-1aaeae24ac7f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラの警告 (レベル 1) C4364
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#using for assembly 'ファイル' の \#using は、以前に  location\(line\_number\) で as\_friend 属性なしに使用されました。as\_friend は適用されません  
  
 `#using` ディレクティブは指定されたメタデータ ファイルに対して繰り返し使用されましたが、`as_friend` 修飾子は初回時に使用されませんでした。このためコンパイラは 2 回目の `as_friend` を無視します。  
  
 詳細については、「[フレンド アセンブリ \(C\+\+\)](../../dotnet/friend-assemblies-cpp.md)」を参照してください。  
  
## 使用例  
 コンポーネントを作成する例を次に示します。  
  
```  
// C4364.cpp  
// compile with: /clr /LD  
ref class A {};  
```  
  
## 使用例  
 次の例では C4364 エラーが生成されます。  
  
```  
// C4364_b.cpp  
// compile with: /clr /W1 /c  
#using " C4364.dll"  
#using " C4364.dll" as_friend   // C4364  
```