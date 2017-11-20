---
title: "方法: シャット ダウンが開始されたかどうかを判断 (C + + CLI) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- .NET Framework, shutdown
- shutdown
- termination
- applications [C++], shutdown
ms.assetid: a8d39731-dea8-4f0a-96b7-2a5de09b21d7
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7f4575f212752a43df2b130fbde9aa7264186d6f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-determine-if-shutdown-has-started-ccli"></a>方法: シャットダウンが開始されたかどうかを確認する (C++/CLI)
次のコード例では、アプリケーションまたは .NET Framework が終了して現在あるかどうかを確認する方法を示します。 これは、ため、シャット ダウン中、これらの構造がシステムによって完了し、確実に使用することはできません、.NET Framework での静的な要素にアクセスするため便利です。 チェックして、<xref:System.Environment.HasShutdownStarted%2A>プロパティ最初に、これらの要素にアクセスするいないと、潜在的な障害を回避できます。  
  
## <a name="example"></a>例  
  
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
  
## <a name="see-also"></a>関連項目  
 [Windows の操作 (C + + CLI)](../dotnet/windows-operations-cpp-cli.md)   
 [C++/CLI (Visual C++) による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)