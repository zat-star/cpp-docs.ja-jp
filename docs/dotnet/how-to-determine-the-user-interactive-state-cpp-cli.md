---
title: "方法: ユーザー インタラクティブな状態を確認する (C++/CLI) | Microsoft Docs"
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
  - "ユーザー対話状態"
  - "Visual C++, ユーザー対話状態"
ms.assetid: 9f52323e-38b8-4a41-9b1d-052012ad839b
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: ユーザー インタラクティブな状態を確認する (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ユーザー インタラクティブなコンテキストで実行中のコードであるかどうかを確認する方法を次のコード例に示します。  <xref:System.Environment.UserInteractive%2A> が false の場合、コードはサービス プロセスとして、または Web アプリケーション内部から実行されています。この場合、ユーザーとは対話できません。  
  
## 使用例  
  
```  
// user_interactive.cpp  
// compile with: /clr  
using namespace System;  
  
int main()   
{  
   if ( Environment::UserInteractive )  
      Console::WriteLine("User interactive");  
   else  
      Console::WriteLine("Noninteractive");  
   return 0;  
}  
```  
  
## 参照  
 [Windows の操作](../dotnet/windows-operations-cpp-cli.md)   
 [C\+\+\/CLI による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)