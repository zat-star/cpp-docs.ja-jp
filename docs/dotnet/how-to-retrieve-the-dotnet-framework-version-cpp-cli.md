---
title: "方法: .NET Framework のバージョンを取得する (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - ".NET Framework, version"
  - "Version プロパティ, 取得 (.NET Framework のバージョンを)"
ms.assetid: fc786fbc-c915-4b15-bcad-0d68cf2c44bd
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: .NET Framework のバージョンを取得する (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

現在インストールされている .NET Framework のバージョンを <xref:System.Environment.Version%2A> プロパティを使用して確認する方法を次のコード例に示します。このプロパティは、バージョン情報を含んだ <xref:System.Version> オブジェクトへのポインターです。  
  
## 使用例  
  
```  
// dotnet_ver.cpp  
// compile with: /clr  
using namespace System;  
int main()   
{  
   Version^ version = Environment::Version;  
   if (version)  
   {  
      int build = version->Build;  
      int major = version->Major;  
      int minor = version->Minor;  
      int revision = Environment::Version->Revision;  
      Console::Write(".NET Framework version: ");  
      Console::WriteLine("{0}.{1}.{2}.{3}",   
            build, major, minor, revision);  
   }  
   return 0;  
}  
```  
  
## 参照  
 [Windows の操作](../dotnet/windows-operations-cpp-cli.md)   
 [C\+\+\/CLI による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)