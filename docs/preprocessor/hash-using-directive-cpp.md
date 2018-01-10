---
title: "#<a name=\"using-directive-cclr--microsoft-docs\"></a>using ディレクティブ (C + + CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- friend_as_cpp
- '#using'
- friend_as
- '#using_cpp'
dev_langs: C++
helpviewer_keywords:
- using directive (#using)
- '#using directive'
- LIBPATH environment variable
- preprocessor, directives
ms.assetid: 870b15e5-f361-40a8-ba1c-c57d75c8809a
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a8a73eb8e9b5c3f3ba67e4466a6e7138010fd430
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="using-directive-cclr"></a>#using ディレクティブ (C + + CLR)
コンパイルされたプログラムにメタデータをインポート[/clr](../build/reference/clr-common-language-runtime-compilation.md)です。  
  
## <a name="syntax"></a>構文  
  
```  
#using file [as_friend]  
```  
  
#### <a name="parameters"></a>パラメーター  
 `file`  
 MSIL .dll、.exe、.netmodule、または .obj。たとえば、オブジェクトに適用された  
  
 `#using <MyComponent.dll>`  
  
 as_friend  
 `file` のすべての型にアクセスできることを指定します。  詳細については、次を参照してください。[フレンド アセンブリ (C++)](../dotnet/friend-assemblies-cpp.md)です。  
  
## <a name="remarks"></a>コメント  
 `file` は、マネージ データとマネージ構造のためにインポートする Microsoft Intermediate Language (MSIL) ファイルにすることができます。 .Dll ファイルには、アセンブリ マニフェストが含まれてし、マニフェストで参照されているすべての .dll ファイルがインポートされており、アセンブリを作成するには一覧表示場合*ファイル*アセンブリ参照としてメタデータにします。  
  
 場合`file`アセンブリが含まれていない (場合`file`モジュール) だけモジュールが一部であることを示すオプションが、現在の (アセンブリ) アプリケーションで、モジュールから型情報を使用する予定がない場合は、アセンブリ;を使用して[/ASSEMBLYMODULE](../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)です。 その場合、アセンブリを参照するすべてのアプリケーションで、そのモジュール内の型を使用できます。  
  
 使用する代わりに`#using`は、 [/FU](../build/reference/fu-name-forced-hash-using-file.md)コンパイラ オプション。  
  
 渡される .exe アセンブリ`#using`をコンパイルするか、.NET の Visual Studio コンパイラ (Visual Basic または Visual C# の場合、たとえば) のいずれかを使用します。  コンパイルされた .exe アセンブリからメタデータをインポートしようとしています。 **/clr**ファイルの読み込み例外が発生します。  
  
> [!NOTE]
>  `#using` で参照されるコンポーネントは、コンパイル時にインポートされる別バージョンのファイルで実行することもできるため、クライアント アプリケーションで予期しない結果になります。  
  
 モジュールではなくアセンブリ内の型をコンパイラで認識するには、型の解決を強制する必要があります。型の解決を実行するには、たとえば、型のインスタンスを定義します。 アセンブリの型名を解決する方法は他にもあります。たとえば、アセンブリの型を継承すると、コンパイラで型名が認識されます。  
  
 使用するソース コードでビルドしたメタデータをインポートするときに[_declspec](../cpp/thread.md)メタデータでは、スレッドのセマンティクスは保持されません。 たとえば、変数を使用して宣言**_declspec**、.NET Framework 共通言語ランタイム用にビルドし、経由でインポートするプログラムでコンパイルされた`#using`がなくなる**_ _declspec (スレッド)**セマンティクス、変数にします。  
  
 `#using` によって参照されるファイル内のインポートされるすべての型 (マネージとネイティブの両方) を使用できますが、コンパイラはネイティブ型を定義ではなく宣言として扱います。  
  
 コンパイルすると、mscorlib.dll が自動的に参照**/clr**です。  
  
 LIBPATH 環境変数は、`#using` に渡されたファイル名をコンパイラが解決しようとするときに検索されるディレクトリを指定します。  
  
 コンパイラは、次のパスに従って参照を検索します。  
  
-   `#using` ステートメントで指定されたパス。  
  
-   現在のフォルダー。  
  
-   .NET Framework のシステム ディレクトリ。  
  
-   追加されたディレクトリ、 [/AI](../build/reference/ai-specify-metadata-directories.md)コンパイラ オプション。  
  
-   LIBPATH 環境変数のディレクトリ。  
  
## <a name="example"></a>例  
 アセンブリ (C) をビルドし、他のアセンブリ (A) を参照しているアセンブリ (B) を参照する場合、C で A のいずれかの型を明示的に使用するのでない限り、アセンブリ A を明示的に参照する必要はありません。  
  
```  
// using_assembly_A.cpp  
// compile with: /clr /LD  
public ref class A {};  
```  
  
## <a name="example"></a>例  
  
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
  
## <a name="example"></a>例  
 次の例では、using_assembly_A.cpp で定義されている型をプログラムが使用しないため、using_assembly_A.dll を参照していないことによるコンパイラ エラーは発生しません。  
  
```  
// using_assembly_C.cpp  
// compile with: /clr  
#using "using_assembly_B.dll"  
int main() {  
   B b;  
   b.Test();  
}  
```  
  
## <a name="see-also"></a>参照  
 [プリプロセッサ ディレクティブ](../preprocessor/preprocessor-directives.md)