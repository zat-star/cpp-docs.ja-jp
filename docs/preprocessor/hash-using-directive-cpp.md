---
title: "#using ディレクティブ (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "friend_as_cpp"
  - "#using"
  - "friend_as"
  - "#using_cpp"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#using ディレクティブ"
  - "LIBPATH 環境変数"
  - "プリプロセッサ, ディレクティブ"
  - "using ディレクティブ (#using)"
ms.assetid: 870b15e5-f361-40a8-ba1c-c57d75c8809a
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# #using ディレクティブ (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[\/clr](../build/reference/clr-common-language-runtime-compilation.md) でコンパイルされたプログラムにメタデータをインポートします。  
  
## 構文  
  
```  
#using file [as_friend]  
```  
  
#### パラメーター  
 `file`  
 MSIL .dll、.exe、.netmodule、または .obj。  次に例を示します。  
  
 `#using <MyComponent.dll>`  
  
 as\_friend  
 `file` のすべての型にアクセスできることを指定します。  詳細については、「[フレンド アセンブリ \(C\+\+\)](../dotnet/friend-assemblies-cpp.md)」を参照してください。  
  
## 解説  
 `file` は、マネージ データとマネージ構造のためにインポートする Microsoft Intermediate Language \(MSIL\) ファイルにすることができます。  .dll ファイルにアセンブリ マニフェストが含まれている場合、マニフェストで参照されているすべての .dll がインポートされ、ビルドしているアセンブリはメタデータ内の *file*  をアセンブリ参照としてリストにします。  
  
 `file` にアセンブリが含まれず \(`file` がモジュールであり\)、現在の \(アセンブリ\) アプリケーションのモジュールから型情報を取得する必要がない場合は、[\/ASSEMBLYMODULE](../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md) を使用して、モジュールがアセンブリの一部であることを示すこともできます。  その場合、アセンブリを参照するすべてのアプリケーションで、そのモジュール内の型を使用できます。  
  
 `#using` を使用する代わりに、[\/FU](../build/reference/fu-name-forced-hash-using-file.md) コンパイラ オプションを使用することができます。  
  
 `#using` に渡される .exe アセンブリは、**\/clr:safe** または **\/clr:pure** でコンパイルするか、他のいずれかの Visual Studio コンパイラ \(たとえば Visual Basic または Visual C\#\) でコンパイルする必要があります。  **\/clr** でコンパイルされた .exe アセンブリからメタデータをインポートしようとすると、ファイルの読み込み例外が発生します。  
  
> [!NOTE]
>  `#using` で参照されるコンポーネントは、コンパイル時にインポートされる別バージョンのファイルで実行することもできるため、クライアント アプリケーションで予期しない結果になります。  
  
 モジュールではなくアセンブリ内の型をコンパイラで認識するには、型の解決を強制する必要があります。型の解決を実行するには、たとえば、型のインスタンスを定義します。  アセンブリの型名を解決する方法は他にもあります。たとえば、アセンブリの型を継承すると、コンパイラで型名が認識されます。  
  
 [\_\_declspec\(thread\)](../cpp/thread.md) を使用したソース コードでビルドしたメタデータをインポートする場合、スレッドのセマンティクスはメタデータでは保持されません。  たとえば、**\_\_declspec\(thread\)** で宣言され、.NET Framework 共通言語ランタイム用にビルドされるプログラムでコンパイルされ、`#using` によってインポートされる変数は、変数に対する **\_\_declspec\(thread\)** セマンティクスを持たなくなります。  
  
 `#using` によって参照されるファイル内のインポートされるすべての型 \(マネージとネイティブの両方\) を使用できますが、コンパイラはネイティブ型を定義ではなく宣言として扱います。  
  
 **\/clr** でコンパイルするときには、mscorlib.dll が自動的に参照されます。  
  
 LIBPATH 環境変数は、`#using` に渡されたファイル名をコンパイラが解決しようとするときに検索されるディレクトリを指定します。  
  
 コンパイラは、次のパスに従って参照を検索します。  
  
-   `#using` ステートメントで指定されたパス。  
  
-   現在のフォルダー。  
  
-   .NET Framework のシステム ディレクトリ。  
  
-   [\/AI](../build/reference/ai-specify-metadata-directories.md) コンパイラ オプションで追加されたディレクトリ。  
  
-   LIBPATH 環境変数のディレクトリ。  
  
## 使用例  
 アセンブリ \(C\) をビルドし、他のアセンブリ \(A\) を参照しているアセンブリ \(B\) を参照する場合、C で A のいずれかの型を明示的に使用するのでない限り、アセンブリ A を明示的に参照する必要はありません。  
  
```  
// using_assembly_A.cpp  
// compile with: /clr /LD  
public ref class A {};  
```  
  
## 使用例  
  
```  
// using_assembly_B.cpp  
// compile with: /clr /LD  
#using "using_assembly_A.dll"  
public ref class B {  
public:  
   void Test(A a) {}  
   void Test() {}  
};  
  
```  
  
## 使用例  
 次の例では、using\_assembly\_A.cpp で定義されている型をプログラムが使用しないため、using\_assembly\_A.dll を参照していないことによるコンパイラ エラーは発生しません。  
  
```  
// using_assembly_C.cpp  
// compile with: /clr  
#using "using_assembly_B.dll"  
int main() {  
   B b;  
   b.Test();  
}  
```  
  
## 参照  
 [プリプロセッサ ディレクティブ](../preprocessor/preprocessor-directives.md)