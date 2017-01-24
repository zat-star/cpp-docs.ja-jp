---
title: "方法: Split メソッドを使用して文字列を解析する (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "例 [C++], 文字列"
  - "解析 (文字列を) [C++]"
  - "正規表現 [C++], 解析 (文字列を)"
  - "Split メソッド, 解析 (文字列を)"
  - "文字列 [C++], 解析"
ms.assetid: d52d2539-5ebb-4716-86b3-07314dd7e4bd
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: Split メソッドを使用して文字列を解析する (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

<xref:System.String.Split%2A?displayProperty=fullName> メソッドを使用して、文字列から各単語を抽出する方法を次のコード例に示します。  デリニエイタ リストを指定して <xref:System.String.Split%2A> を呼び出すと、複数の型のワード デリニエイタを含む文字列が構成され、解析されます。  さらに、センテンス内の各単語を個別に表示します。  
  
## 使用例  
  
```  
// regex_split.cpp  
// compile with: /clr  
using namespace System;  
  
int main()  
{  
   String^ delimStr = " ,.:\t";  
   Console::WriteLine( "delimiter : '{0}'", delimStr );  
   array<Char>^ delimiter = delimStr->ToCharArray( );  
   array<String^>^ words;  
   String^ line = "one\ttwo three:four,five six seven";  
  
   Console::WriteLine( "text : '{0}'", line );  
   words = line->Split( delimiter );  
   Console::WriteLine( "Number of Words : {0}", words->Length );  
   for (int word=0; word<words->Length; word++)  
      Console::WriteLine( "{0}", words[word] );  
  
   return 0;  
}  
```  
  
## 参照  
 [.NET Framework の正規表現](../Topic/.NET%20Framework%20Regular%20Expressions.md)   
 [C\+\+\/CLI による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)