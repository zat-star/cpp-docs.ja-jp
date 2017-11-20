---
title: "方法: .NET Framework のバージョンの取得 (C + + CLI) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- .NET Framework, version
- Version property, retrieving .NET Framework version
ms.assetid: fc786fbc-c915-4b15-bcad-0d68cf2c44bd
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6b5ac441e7fa91d73c4605a39585d2e293318417
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-retrieve-the-net-framework-version-ccli"></a>方法: .NET Framework のバージョンを取得する (C++/CLI)
次のコード例を使用して、現在インストールされている .NET Framework のバージョンを確認する方法を示しています、<xref:System.Environment.Version%2A>ポインターであるプロパティを<xref:System.Version>バージョン情報を含むオブジェクト。  
  
## <a name="example"></a>例  
  
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
  
## <a name="see-also"></a>関連項目  
 [Windows の操作 (C + + CLI)](../dotnet/windows-operations-cpp-cli.md)   
 [C++/CLI (Visual C++) による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)