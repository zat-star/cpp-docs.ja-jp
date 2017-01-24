---
title: "方法: C# インデクサーを使用する (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C++, インデクサー"
  - "インデクサー, 利用 (C# を)"
ms.assetid: 5a11850c-a1a2-4a0a-b95e-f6dc5a87f439
caps.latest.revision: 13
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: C# インデクサーを使用する (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ にはインデクサーは含まれていませんが、インデックス付きのプロパティが用意されています。  C\# インデクサーを使用するには、インデックス付きのプロパティのようにインデクサーにアクセスします。  
  
 インデクサーの詳細については、次のトピックを参照してください。  
  
-   [インデクサー](../Topic/Indexers%20\(C%23%20Programming%20Guide\).md)  
  
-   [方法: インデックス付きプロパティを使用する](../misc/how-to-use-indexed-properties.md)  
  
## 使用例  
 次の C\# プログラムは、インデクサーを定義します。  
  
```  
// consume_cs_indexers.cs  
// compile with: /target:library  
using System;  
public class IndexerClass {  
   private int [] myArray = new int[100];   
   public int this [int index] {   // Indexer declaration  
      get {  
         // Check the index limits.  
         if (index < 0 || index >= 100)  
            return 0;  
         else  
            return myArray[index];  
      }  
      set {  
         if (!(index < 0 || index >= 100))  
            myArray[index] = value;  
      }  
   }  
}  
/*  
// code to consume the indexer  
public class MainClass {  
   public static void Main() {  
      IndexerClass b = new IndexerClass();  
  
      // Call indexer to initialize elements 3 and 5  
      b[3] = 256;  
      b[5] = 1024;  
      for (int i = 0 ; i <= 10 ; i++)   
         Console.WriteLine("Element #{0} = {1}", i, b[i]);  
   }  
}  
*/  
```  
  
## 使用例  
 この Visual C\+\+ プログラムはインデクサーを使用します。  
  
```  
// consume_cs_indexers_2.cpp  
// compile with: /clr  
#using "consume_cs_indexers.dll"  
using namespace System;  
  
int main() {  
   IndexerClass ^ ic = gcnew IndexerClass;  
   ic->default[0] = 21;  
   for (int i = 0 ; i <= 10 ; i++)  
      Console::WriteLine("Element #{0} = {1}", i, ic->default[i]);  
}  
```  
  
  **Element \#0 \= 21**  
**Element \#1 \= 0**  
**Element \#2 \= 0**  
**Element \#3 \= 0**  
**Element \#4 \= 0**  
**Element \#5 \= 0**  
**Element \#6 \= 0**  
**Element \#7 \= 0**  
**Element \#8 \= 0**  
**Element \#9 \= 0**  
**Element \#10 \= 0**   
## 参照  
 [他の .NET 言語との相互運用性](../dotnet/interoperability-with-other-dotnet-languages-cpp-cli.md)