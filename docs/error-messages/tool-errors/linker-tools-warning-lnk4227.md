---
title: "リンカー ツールの警告 LNK4227 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4227"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4227"
ms.assetid: 941a0414-9964-4e02-8487-f9daa42ef7f9
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リンカー ツールの警告 LNK4227
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

メタデータ演算警告 \(HRESULT\) : warning\_message  
  
 次の項目をマージするときに、メタデータの違いが検出されました。  
  
-   ビルド中のアセンブリがある 1 つ以上の参照先アセンブリ  
  
-   コンパイルする 1 つ以上のソース コード ファイル  
  
 たとえば、LNK4227 は、名前が同じだが宣言されているパラメーター情報が異なる \(宣言がすべてのコンパイル単位で一致していない\)  2 つのグローバル関数があることが原因で発生することがあります。  各 .obj ファイルで ildasm.exe \/TEXT \/METADATA `object_file` を使用して、型の違いを調べる必要があります。  
  
 LNK4227 は、別のツールで発生した問題も報告します。  たとえば、al.exe などのツールです。「[Al.exe ツールのエラーと警告](http://msdn.microsoft.com/ja-jp/7f125d49-0a03-47a6-9ba9-d61a679a7d4b)」を参照してください。  
  
 この警告を解決するには、メタデータの問題を解決する必要があります。  
  
 たとえば、LNK4227 は、参照先アセンブリで参照元アセンブリとは異なる署名が行われた場合に生成されます。  
  
 次の例では警告 LNK4227 が生成されます。  
  
```  
// LNK4227.cpp  
// compile with: /clr  
using namespace System::Reflection;  
  
[assembly:AssemblyDelaySignAttribute(false)];  
  
int main() {}  
```  
  
 次に、以下のコードを実行します。  
  
```  
// LNK4227b.cpp  
// compile with: /clr LNK4227.cpp /FeLNK4227b.exe  
using namespace System::Reflection;  
using namespace System::Runtime::CompilerServices;  
  
[assembly:AssemblyDelaySignAttribute(true)];  
// Try the following line instead  
// [assembly:AssemblyDelaySignAttribute(false)];  
  
ref class MyClass  
{  
};  
```  
  
 次の例では警告 LNK4227 が生成されます。  
  
```  
// LNK4227c.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System::Reflection;  
  
[assembly:AssemblyDelaySignAttribute(false)];  
  
int main() {}  
```  
  
 次に、以下のコードを実行します。  
  
```  
// LNK4227d.cpp  
// compile with: /clr:oldSyntax LNK4227c.cpp /FeLNK4227d.exe  
#using <mscorlib.dll>  
using namespace System::Reflection;  
using namespace System::Runtime::CompilerServices;  
  
[assembly:AssemblyDelaySignAttribute(true)];  
  
__gc class MyClass  
{  
};  
```  
  
 LNK4227 は、誤った書式のバージョン番号がアセンブリ属性に渡された場合にも生成されることがあります。'\*' は、AssemblyVersionAttribute 固有の表記です。この警告を解決するには、AssemblyVersionAttribute 以外のバージョン属性で数字だけを使用します。  
  
 次の例では警告 LNK4227 が生成されます。  
  
```  
// LNK4227e.cpp  
// compile with: /clr /LD /W1  
using namespace System::Reflection;  
[assembly:AssemblyVersionAttribute("2.3.*")];   // OK  
[assembly:AssemblyFileVersionAttribute("2.3.*")];   // LNK4227  
// try the following line instead  
// [assembly:AssemblyFileVersionAttribute("2.3")];  
```