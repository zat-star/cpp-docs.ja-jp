---
title: "コンパイラの警告 (レベル 1) C4944 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4944"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4944"
ms.assetid: e2905eb1-2e3b-4fab-a48b-c0cae0fd997f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラの警告 (レベル 1) C4944
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbol': 'assembly1' からシンボルをインポートできません: 'symbol' は既に現在のスコープに存在します  
  
 シンボルがソース コード ファイル内で定義されています。\#using ステートメントはアセンブリを参照しますが、そのアセンブリもシンボルを定義しています。 アセンブリ内のシンボルは無視されます。  
  
## 使用例  
 ClassA という型を使用してコンポーネントを作成する例を次に示します。  
  
```  
// C4944.cs // compile with: /target:library // C# source code to create a dll public class ClassA { public int i; }  
```  
  
## 使用例  
 次の例では C4944 が生成されます。  
  
```  
// C4944b.cpp // compile with: /clr /W1 class ClassA { public: int u; }; #using "C4944.dll"   // C4944 ClassA also defined C4944.dll int main() { ClassA * x = new ClassA(); x->u = 9; System::Console::WriteLine(x->u); }  
```