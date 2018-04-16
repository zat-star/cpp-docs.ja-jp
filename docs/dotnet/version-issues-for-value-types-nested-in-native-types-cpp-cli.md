---
title: "ネイティブ型に入れ子になった値の型のバージョンの問題 (C + + CLI) |Microsoft ドキュメント"
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
- __nogc type declarations
- __value keyword, issues when nesting
ms.assetid: 0a3b1a43-39c6-4b52-be2f-1074690188aa
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 29a5eb3a085682f243f1497e56b12a0b7d760edb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="version-issues-for-value-types-nested-in-native-types-ccli"></a>ネイティブ型に入れ子になっている値型のバージョンの問題 (C++/CLI)
署名 (厳密な名前) アセンブリ コンポーネントがクライアント アセンブリをビルドするために使用を検討してください。 コンポーネントには、ネイティブの共用体、クラス、または配列のメンバーの種類として、クライアントで使用される値の型が含まれています。 コンポーネントの将来のバージョンでは、サイズまたは値型のレイアウトを変更する場合、クライアントを再コンパイルする必要があります。  
  
 キー ファイルを作成する[sn.exe](/dotnet/framework/tools/sn-exe-strong-name-tool) (`sn -k mykey.snk`)。  
  
## <a name="example"></a>例  
 次の例は、コンポーネントです。  
  
```  
// nested_value_types.cpp  
// compile with: /clr /LD  
using namespace System::Reflection;  
[assembly:AssemblyVersion("1.0.0.*"),   
assembly:AssemblyKeyFile("mykey.snk")];  
  
public value struct S {  
   int i;  
   void Test() {  
      System::Console::WriteLine("S.i = {0}", i);  
   }  
};  
```  
  
## <a name="example"></a>例  
 このサンプルでは、クライアントです。  
  
```  
// nested_value_types_2.cpp  
// compile with: /clr  
#using <nested_value_types.dll>  
  
struct S2 {  
   S MyS1, MyS2;  
};  
  
int main() {  
   S2 MyS2a, MyS2b;  
   MyS2a.MyS1.i = 5;  
   MyS2a.MyS2.i = 6;  
   MyS2b.MyS1.i = 10;  
   MyS2b.MyS2.i = 11;  
  
   MyS2a.MyS1.Test();  
   MyS2a.MyS2.Test();  
   MyS2b.MyS1.Test();  
   MyS2b.MyS2.Test();  
}  
```  
  
## <a name="output"></a>出力  
  
```  
S.i = 5  
S.i = 6  
S.i = 10  
S.i = 11  
```  
  
### <a name="comments"></a>コメント  
 ただし、する別のメンバーを追加する場合`struct S`nested_value_types.cpp で (たとえば、 `double d;`) クライアントを再コンパイルしなくても、コンポーネントを再コンパイルし、結果は、未処理の例外 (型の<xref:System.IO.FileLoadException?displayProperty=fullName>)。  
  
## <a name="see-also"></a>参照  
 [マネージ型 (C++/CLI)](../dotnet/managed-types-cpp-cli.md)