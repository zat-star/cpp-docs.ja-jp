---
title: "方法: 正規表現を使用して検索と置換を行う (C++/CLI) | Microsoft Docs"
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
  - "正規表現 [C++], 検索と置換"
  - "Replace メソッド"
  - "検索と置換"
ms.assetid: 12fe3e18-fe10-4b25-a221-19dc5eab3821
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: 正規表現を使用して検索と置換を行う (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

正規表現クラス <xref:System.Text.RegularExpressions.Regex> を使用して、検索と置換を行う方法を次のコード例に示します。  これらの処理を行うには、<xref:System.Text.RegularExpressions.Regex.Replace%2A> メソッドを使用します。  使用する構文は、入力として 2 つの文字列を使用します。それは、変更する文字列、および <xref:System.Text.RegularExpressions.Regex> オブジェクトに指定されるパターンに一致するセクションがある場合にその代わりに挿入する文字列です。  
  
 このコードは、文字列のすべての桁をアンダースコア \(\_\) で置き換え、さらに空の文字列で置き換えることにより、効率的に文字列のすべての桁を削除します。  1 つの手順で同じ効果を実現することもできますが、デモンストレーションの目的を考慮して、ここでは 2 つの手順を使用します。  
  
## 使用例  
  
```  
// regex_replace.cpp  
// compile with: /clr  
#using <System.dll>  
using namespace System::Text::RegularExpressions;  
using namespace System;  
  
int main()  
{  
   String^ before = "The q43uick bro254wn f0ox ju4mped";  
   Console::WriteLine("original  : {0}", before);  
  
   Regex^ digitRegex = gcnew Regex("(?<digit>[0-9])");  
   String^ after = digitRegex->Replace(before, "_");  
   Console::WriteLine("1st regex : {0}", after);  
  
   Regex^ underbarRegex = gcnew Regex("_");  
   String^ after2 = underbarRegex->Replace(after, "");  
   Console::WriteLine("2nd regex : {0}", after2);  
  
   return 0;  
}  
```  
  
## 参照  
 [.NET Framework の正規表現](../Topic/.NET%20Framework%20Regular%20Expressions.md)   
 [C\+\+\/CLI による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)