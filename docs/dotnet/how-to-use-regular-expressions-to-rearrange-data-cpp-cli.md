---
title: "方法: 正規表現を使用してデータを再配置する (C++/CLI) | Microsoft Docs"
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
  - "データ [C++], 再配置"
  - "正規表現 [C++], 再配置 (データを)"
ms.assetid: 5f91e777-9471-424e-ba75-dca3d1b49e42
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: 正規表現を使用してデータを再配置する (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

.NET Framework の正規表現サポートを使用して、データを再配置または再フォーマットする方法を次のコード例に示します。  次のコード例では、<xref:System.Text.RegularExpressions.Regex> クラスと <xref:System.Text.RegularExpressions.Match> クラスを使用して、文字列から最初の名前と最後の名前を抽出し、これらの名前要素を逆順に表示します。  
  
 <xref:System.Text.RegularExpressions.Regex> クラスを使用して、データの現在の書式を記述する正規表現を構成します。  2 つの名前はコンマで区切ります。また、コンマの前後には任意の数の空白文字を入れることができます。  次に、<xref:System.Text.RegularExpressions.Match> メソッドを使用して、各文字列を解析します。  正常に処理されると、<xref:System.Text.RegularExpressions.Match> オブジェクトから最初の名前と最後の名前が取得され、表示されます。  
  
## 使用例  
  
```  
// regex_reorder.cpp  
// compile with: /clr  
#using <System.dll>  
using namespace System;  
using namespace Text::RegularExpressions;  
  
int main()  
{  
   array<String^>^ name =   
   {  
      "Abolrous, Sam",   
      "Berg,Matt",   
      "Berry , Jo",  
      "www.contoso.com"  
   };  
  
   Regex^ reg = gcnew Regex("(?<last>\\w*)\\s*,\\s*(?<first>\\w*)");  
  
   for ( int i=0; i < name->Length; i++ )  
   {  
      Console::Write( "{0,-20}", name[i] );  
      Match^ m = reg->Match( name[i] );  
      if ( m->Success )  
      {  
         String^ first = m->Groups["first"]->Value;  
         String^ last = m->Groups["last"]->Value;  
         Console::WriteLine("{0} {1}", first, last);  
      }  
      else  
         Console::WriteLine("(invalid)");  
   }  
   return 0;  
}  
```  
  
## 参照  
 [.NET Framework の正規表現](../Topic/.NET%20Framework%20Regular%20Expressions.md)   
 [C\+\+\/CLI による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)