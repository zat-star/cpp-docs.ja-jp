---
title: "厳密名アセンブリ (アセンブリ署名) (C++/CLI) | Microsoft Docs"
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
  - ".NET Framework [C++], アセンブリの署名"
  - "アセンブリ [C++]"
  - "アセンブリ [C++], 署名"
  - "リンカー [C++], アセンブリの署名"
  - "署名 (アセンブリに)"
  - "厳密な名前を付けたアセンブリ [C++]"
ms.assetid: c337cd3f-e5dd-4c6f-a1ad-437e85dba1cc
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 厳密名アセンブリ (アセンブリ署名) (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このトピックでは、アセンブリに署名する方法について説明します。アセンブリに署名することを、多くの場合、アセンブリに厳密名を付けるともいいます。  
  
## 解説  
 Visual C\+\+ を使用するときは、リンカー オプションを使用してアセンブリに署名することにより、アセンブリ署名の CLR 属性に関する問題を回避します。  
  
-   <xref:System.Reflection.AssemblyDelaySignAttribute>  
  
-   <xref:System.Reflection.AssemblyKeyFileAttribute>  
  
-   <xref:System.Reflection.AssemblyKeyNameAttribute>  
  
 属性を使用しない理由として、アセンブリ メタデータではキー名が参照可能であり、ファイル名に機密情報が含まれている場合にはセキュリティ上のリスクが発生することがあります。  また、Visual C\+\+ 開発環境で使用されるビルド プロセスでは、CLR 属性を使用してアセンブリに厳密名を付け、その後 mt.exe などの後処理ツールをアセンブリで実行した場合、アセンブリに署名したキーが無効化されます。  
  
 コマンド ラインで作成し、リンカー オプションを使用してアセンブリに署名し、次に後処理ツール \(mt.exe など\) を実行する場合、sn.exe でアセンブリに再度署名する必要があります。  代わりに、作成後のアセンブリの署名を後回しにし、後処理ツールを実行してから署名できます。  
  
 開発環境を構築するときに署名の属性を使用する場合は、ビルド後のイベントで sn.exe \([Sn.exe \(厳密名ツール\)](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md)\) を明示的に呼び出すと、正しくアセンブリに署名できます。  詳細については、「[ビルド イベントの指定](../ide/specifying-build-events.md)」を参照してください。  属性およびビルド後のイベントを使用すると、リンカー オプションを使用する場合と比較して、ビルドにかかる時間が短くなります。  
  
 次のリンカー オプションはアセンブリの署名をサポートしています。  
  
-   [\/DELAYSIGN \(アセンブリの部分署名\)](../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [\/KEYFILE \(アセンブリに署名するためのキーまたはキー ペアの指定\)](../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
-   [\/KEYCONTAINER \(アセンブリに署名するためのキー コンテナーの指定\)](../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
 厳密なアセンブリの詳細については、「[厳密な名前付きアセンブリの作成と使用](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md)」を参照してください。  
  
## 参照  
 [C\+\+\/CLI による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)