---
title: "ADO.NET によるデータ アクセス (C++/CLI) | Microsoft Docs"
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
  - ".NET Framework [C++], データ アクセス"
  - "ADO.NET [C++]"
  - "データ [C++], ADO.NET"
  - "データ アクセス [C++], ADO.NET"
  - "データベース [C++], アクセス (C++ での)"
ms.assetid: b0cd987d-1ea7-4f76-ba01-cbd52503d06d
caps.latest.revision: 12
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ADO.NET によるデータ アクセス (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ADO.NET はデータ アクセス用の .NET Framework API で、これまでのデータ アクセス ソリューションにはないパワーと使いやすさを提供します。  ここでは、ネイティブ型のマーシャリングなど、ADO.NET に関する Visual C\+\+ ユーザー固有のいくつかの問題について説明します。  
  
 ADO.NET は、共通言語ランタイム \(CLR\) で実行されます。  したがって、ADO.NET とやり取りするアプリケーションは CLR も対象とする必要があります。  しかし、ネイティブなアプリケーションが ADO.NET を使用できないわけではありません。  ネイティブ コードから ADO.NET データベースとやり取りする方法を次の例に示します。  
  
## このセクションの内容  
 [方法: ADO.NET の ANSI 文字列をマーシャリングする](../dotnet/how-to-marshal-ansi-strings-for-adonet-cpp-cli.md)  
  
 [方法: ADO.NET の BSTR 文字列をマーシャリングする](../dotnet/how-to-marshal-bstr-strings-for-adonet-cpp-cli.md)  
  
 [方法: ADO.NET の Unicode 文字列をマーシャリングする](../dotnet/how-to-marshal-unicode-strings-for-adonet-cpp-cli.md)  
  
 [方法: ADO.NET の VARIANT をマーシャリングする](../dotnet/how-to-marshal-a-variant-for-adonet-cpp-cli.md)  
  
 [方法: ADO.NET の SAFEARRAY をマーシャリングする](../dotnet/how-to-marshal-a-safearray-for-adonet-cpp-cli.md)  
  
## 関連項目  
  
|セクション|説明|  
|-----------|--------|  
|[ADO.NET](../Topic/ADO.NET.md)|.NET プログラマにデータ アクセス サービスを公開する一連のクラスがまとめられた、ADO.NET の概要を説明します。|  
|[Creating SQL Server 2005 Objects In Managed Code](http://msdn.microsoft.com/ja-jp/5358a825-e19b-49aa-8214-674ce5fed1da)|Visual C\+\+ などの .NET 言語を使用して、データベース オブジェクト \(ストアド プロシージャ、集計、トリガー、ユーザー定義関数、ユーザー定義型など\) を作成する方法のほか、Microsoft SQL Server 2005 データベースのデータを取得したり更新したりする方法について説明します。|  
  
## 参照  
 [C\+\+\/CLI による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)   
 [ネイティブと .NET の相互運用性](../Topic/Native%20and%20.NET%20Interoperability.md)