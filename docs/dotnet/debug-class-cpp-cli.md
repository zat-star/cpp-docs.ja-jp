---
title: "Debug クラス (C + + CLI) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Trace class, Visual C++
- .NET Framework [C++], Debug class
- Debug class
ms.assetid: 076bd528-1b6f-4e8a-a372-eb5849cf969a
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 14354241c4e16e1177a5680b901a738f16036f96
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="debug-class-ccli"></a>Debug クラス (C++/CLI)
使用する場合<xref:System.Diagnostics.Debug>Visual C のアプリケーションで、動作が、デバッグとリリース ビルドの間で変更されません。  
  
## <a name="remarks"></a>コメント  
 動作は、 <xref:System.Diagnostics.Trace> Debug クラスの動作と同じですが、シンボル定義されているトレースに依存します。 つまりする必要のある`#ifdef`すべてトレースに関連するコードをリリース ビルドでのデバッグ動作を防ぐためにします。  
  
## <a name="example"></a>例  
  
### <a name="description"></a>説明  
 次の例は、常に使用してコンパイルするかどうかに関係なく、出力ステートメントを実行**/DDEBUG**または**/DTRACE**です。  
  
### <a name="code"></a>コード  
  
```  
// mcpp_debug_class.cpp  
// compile with: /clr  
#using <system.dll>  
using namespace System::Diagnostics;  
using namespace System;  
  
int main() {  
   Trace::Listeners->Add( gcnew TextWriterTraceListener( Console::Out ) );  
   Trace::AutoFlush = true;  
   Trace::Indent();  
   Trace::WriteLine( "Entering Main" );  
   Console::WriteLine( "Hello World." );  
   Trace::WriteLine( "Exiting Main" );  
   Trace::Unindent();  
  
   Debug::WriteLine("test");  
}  
```  
  
### <a name="output"></a>出力  
  
```  
    Entering Main  
Hello World.  
    Exiting Main  
test  
```  
  
## <a name="example"></a>例  
  
### <a name="description"></a>説明  
 予期しない動作を取得する (つまり、"test"が出力されない、リリース ビルド) を使用する必要があります、`#ifdef`と`#endif`ディレクティブです。 上記のコード サンプルは、この修正プログラムを示すために下に変更されます。  
  
### <a name="code"></a>コード  
  
```  
// mcpp_debug_class2.cpp  
// compile with: /clr  
#using <system.dll>  
using namespace System::Diagnostics;  
using namespace System;  
  
int main() {  
   Trace::Listeners->Add( gcnew TextWriterTraceListener( Console::Out ) );  
   Trace::AutoFlush = true;  
   Trace::Indent();  
  
#ifdef TRACE   // checks for a debug build  
   Trace::WriteLine( "Entering Main" );  
   Console::WriteLine( "Hello World." );  
   Trace::WriteLine( "Exiting Main" );  
#endif  
   Trace::Unindent();  
  
#ifdef DEBUG   // checks for a debug build  
   Debug::WriteLine("test");  
#endif   //ends the conditional block  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [C++/CLI (Visual C++) による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)