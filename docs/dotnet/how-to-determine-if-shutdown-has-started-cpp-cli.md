---
title: "方法: シャット ダウンが開始されたかどうかを判断 (C + + CLI) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- .NET Framework, shutdown
- shutdown
- termination
- applications [C++], shutdown
ms.assetid: a8d39731-dea8-4f0a-96b7-2a5de09b21d7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4d89fa475c997e0842ef9de5a21c26e664f25d78
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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
  
## <a name="see-also"></a>参照  
 [Windows の操作 (C + + CLI)](../dotnet/windows-operations-cpp-cli.md)   
 [C++/CLI (Visual C++) による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)