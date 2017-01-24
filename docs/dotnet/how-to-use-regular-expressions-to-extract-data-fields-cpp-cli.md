---
title: "方法: 正規表現を使用してデータ フィールドを抽出する (C++/CLI) | Microsoft Docs"
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
  - "データ [C++], 抽出 (文字列から)"
  - "書式付き文字列 [C++]"
  - "正規表現 [C++], 抽出 (データ フィールドを)"
  - "文字列 [C++], 抽出 (データの)"
ms.assetid: b581d9b6-630e-48fa-94fe-20b0f7b89b06
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: 正規表現を使用してデータ フィールドを抽出する (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

正規表現を使用して、書式設定された文字列からデータを抽出する方法を次のコード例に示します。  次のコード例では、<xref:System.Text.RegularExpressions.Regex> クラスを使用して、電子メール アドレスに対応するパターンを指定します。  このパターンには、各電子メール アドレスのユーザー名とホスト名の部分を取得するために使用するフィールド識別子が含まれます。  <xref:System.Text.RegularExpressions.Match> クラスを使用すると、実際のパターン一致を実行できます。  指定された電子メール アドレスが有効な場合、ユーザー名とホスト名が抽出され、表示されます。  
  
## 使用例  
  
```  
// Regex_extract.cpp  
// compile with: /clr  
#using <System.dll>  
  
using namespace System;  
using namespace System::Text::RegularExpressions;  
  
int main()  
{  
    array<String^>^ address=  
    {  
        "jay@southridgevideo.com",  
        "barry@adatum.com",  
        "treyresearch.net",  
        "karen@proseware.com"  
    };  
  
    Regex^ emailregex = gcnew Regex("(?<user>[^@]+)@(?<host>.+)");  
  
    for (int i=0; i<address->Length; i++)  
    {  
        Match^ m = emailregex->Match( address[i] );  
        Console::Write("\n{0,25}", address[i]);  
  
        if ( m->Success )   
        {  
            Console::Write("   User='{0}'",   
            m->Groups["user"]->Value);  
            Console::Write("   Host='{0}'",   
            m->Groups["host"]->Value);  
        }  
        else   
            Console::Write("   (invalid email address)");  
        }  
  
    Console::WriteLine("");  
    return 0;  
}  
```  
  
## 参照  
 [.NET Framework の正規表現](../Topic/.NET%20Framework%20Regular%20Expressions.md)   
 [C\+\+\/CLI による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)