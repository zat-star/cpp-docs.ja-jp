---
title: "方法: シャットダウンが開始されたかどうかを確認する (C++/CLI) | Microsoft Docs"
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
  - ".NET Framework, シャットダウン"
  - "アプリケーション [C++], シャットダウン"
  - "シャットダウン"
  - "終了"
ms.assetid: a8d39731-dea8-4f0a-96b7-2a5de09b21d7
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: シャットダウンが開始されたかどうかを確認する (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

アプリケーションまたは .NET Framework が現在終了中かどうかを確認する方法を次のコード例に示します。  .NET Framework 内の静的要素にアクセスする場合、この方法が便利です。シャットダウンする間、.NET Framework の構造体はシステムによって終了されていて、使用できないからです。  まず <xref:System.Environment.HasShutdownStarted%2A> プロパティを確認してこれらの要素にアクセスしないことにより、発生する可能性のあるエラーを回避できます。  
  
## 使用例  
  
```  
// check_shutdown.cpp  
// compile with: /clr  
using namespace System;  
int main()   
{  
   if (Environment::HasShutdownStarted)  
      Console::WriteLine("Shutting down.");  
   else  
      Console::WriteLine("Not shutting down.");  
   return 0;  
}  
```  
  
## 参照  
 [Windows の操作](../dotnet/windows-operations-cpp-cli.md)   
 [C\+\+\/CLI による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)