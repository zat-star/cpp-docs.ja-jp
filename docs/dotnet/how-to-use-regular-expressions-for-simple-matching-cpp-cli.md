---
title: "方法: 正規表現を使用して単純検索を行う (C++/CLI) | Microsoft Docs"
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
  - "IsMatch メソッド"
  - "正規表現 [C++], 単純な一致"
  - "検索, 部分文字列の正確な一致"
  - "文字列 [C++], 部分文字列の正確な一致"
  - "部分文字列, 単純な一致"
ms.assetid: 4661f6f3-0f6d-48f2-abe4-cb4770bf9bd5
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: 正規表現を使用して単純検索を行う (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

正規表現を使用して部分文字列の完全一致を検索するコード例を次に示します。  この検索は、静的な <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> メソッドで実行されます。このメソッドは、入力として 2 つの文字列を受け取ります。  1 つ目は検索文字列で、2 つ目は、検索パターンです。  
  
## 使用例  
  
```  
// regex_simple.cpp  
// compile with: /clr  
#using <System.dll>  
  
using namespace System;  
using namespace System::Text::RegularExpressions;  
  
int main()  
{  
   array<String^>^ sentence =   
   {  
      "cow over the moon",  
      "Betsy the Cow",  
      "cowering in the corner",  
      "no match here"  
   };  
  
   String^ matchStr = "cow";  
   for (int i=0; i<sentence->Length; i++)  
   {  
      Console::Write( "{0,24}", sentence[i] );  
      if ( Regex::IsMatch( sentence[i], matchStr,  
                     RegexOptions::IgnoreCase ) )  
         Console::WriteLine("  (match for '{0}' found)", matchStr);  
      else  
         Console::WriteLine("");  
   }  
   return 0;  
}  
```  
  
## 参照  
 [.NET Framework の正規表現](../Topic/.NET%20Framework%20Regular%20Expressions.md)   
 [C\+\+\/CLI による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)