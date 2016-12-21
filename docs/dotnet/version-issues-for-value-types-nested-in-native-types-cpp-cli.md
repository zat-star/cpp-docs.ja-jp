---
title: "ネイティブ型に入れ子になっている値型のバージョンの問題 (C++/CLI) | Microsoft Docs"
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
  - "__nogc 型の宣言"
  - "__value キーワード, 発行 (入れ子時に)"
ms.assetid: 0a3b1a43-39c6-4b52-be2f-1074690188aa
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ネイティブ型に入れ子になっている値型のバージョンの問題 (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

クライアント アセンブリをビルドするために使用される署名済みの \(厳密な名前\) アセンブリ コンポーネントを考えます。  このコンポーネントには、クライアントでネイティブ共用体、クラス、または配列のメンバーの型として使用される値型が含まれています。  将来のバージョンのコンポーネントで値型のサイズまたはレイアウトが変更された場合は、クライアントを再コンパイルする必要があります。  
  
 [sn.exe](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md) \(`sn -k mykey.snk`\) でキーファイルを作成します。  
  
## 使用例  
 コンポーネントの例を次に示します。  
  
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
  
## 使用例  
 クライアントの例を次に示します。  
  
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
  
## 出力  
  
```  
S.i = 5  
S.i = 6  
S.i = 10  
S.i = 11  
```  
  
### コメント  
 しかし、nested\_value\_types.cpp で `struct S` に別のメンバー \(たとえば `double d;`\) を追加し、クライアントを再コンパイルせずにコンポーネントを再コンパイルすると、\(<xref:System.IO.FileLoadException?displayProperty=fullName> 型の\) 処理できない例外が発生します。  
  
## 参照  
 [マネージ型](../Topic/Managed%20Types%20\(C++-CLI\).md)