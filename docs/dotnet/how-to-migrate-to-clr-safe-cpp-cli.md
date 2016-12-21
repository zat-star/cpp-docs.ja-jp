---
title: "方法: /clr:safe に移行する (C++/CLI) | Microsoft Docs"
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
  - "/clr コンパイラ オプション [C++], 移行 (/clr:safe に)"
  - "移行 [C++], 検証可能なアセンブリ"
  - "アップグレード (Visual C++ アプリケーションの), 検証可能なアセンブリ"
  - "検証可能なアセンブリ [C++], 移行"
ms.assetid: 75f9aae9-1dcc-448a-aa11-2d96f972f9d2
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: /clr:safe に移行する (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ では、**\/clr:safe** を使用して検証可能なコンポーネントを生成できます。この場合、コンパイラは、検証可能でないコード コンストラクターを検出するたびにエラーを生成します。  
  
## 解説  
 次の問題により、検証可能性エラーが生成されます。  
  
-   ネイティブ型。  ネイティブ型を使用していない場合でも、ネイティブ クラス、構造体、ポインター、または配列の宣言によりコンパイルできなくなります。  
  
-   グローバル変数  
  
-   共通言語ランタイム関数呼び出しなどの任意のアンマネージ ライブラリへの関数呼び出し  
  
-   検証可能な関数には、ダウンキャストのために [static\_cast 演算子](../cpp/static-cast-operator.md) を含めることはできません。  プリミティブ型どうしのキャストには、[static\_cast 演算子](../cpp/static-cast-operator.md) を使用できますが、ダウンキャストには、[safe\_cast](../windows/safe-cast-cpp-component-extensions.md) または C スタイルのキャスト \(これは、[safe\_cast](../windows/safe-cast-cpp-component-extensions.md) として実装される\) を使用する必要があります。  
  
-   検証可能な関数には、[reinterpret\_cast 演算子](../cpp/reinterpret-cast-operator.md) \(または同等の C スタイル キャスト\) を含めることができません。  
  
-   検証可能な関数は、[interior\_ptr \(C\+\+\/CLI\)](../windows/interior-ptr-cpp-cli.md) 上で数値型を実行できません。  可能なのは、代入と逆参照だけです。  
  
-   検証可能な関数は、参照型へのポインターだけをスローまたはキャッチします。このため、値型はスローする前にボックス化する必要があります。  
  
-   検証可能な関数は、検証可能な関数しか呼び出すことができません。`AtEntry` や `AtExit` を含む共通言語ランタイムの呼び出しが許可されないため、グローバル コンストラクターも使用できません。  
  
-   検証可能なクラスは、<xref:System.Runtime.InteropServices.LayoutKind> を使用できません。  
  
-   EXE をビルドする場合、main 関数はパラメーターを宣言できないため、<xref:System.Environment.GetCommandLineArgs%2A> を使用してコマンド ライン引数を取得する必要があります。  
  
-   仮想関数への非仮想呼び出しを行います。  たとえば、次のようになります。  
  
    ```  
    // not_verifiable.cpp  
    // compile with: /clr  
    ref struct A {  
       virtual void Test() {}  
    };  
  
    ref struct B : A {};  
  
    int main() {  
       B^ b1 = gcnew B;  
       b1->A::Test();   // Non-virtual call to virtual function  
    }  
    ```  
  
 また、次のキーワードは検証可能なコードで使用できません。  
  
-   [unmanaged](../preprocessor/managed-unmanaged.md) プラグマと [pack](../preprocessor/pack.md) プラグマ  
  
-   [naked](../Topic/naked%20\(C++\).md) 修飾子と [align](../cpp/align-cpp.md) [\_\_declspec](../cpp/declspec.md) 修飾子  
  
-   [\_\_asm](../assembler/inline/asm.md)  
  
-   [\_\_based](../cpp/based-grammar.md)  
  
-   [\_\_try](../cpp/try-except-statement.md) と `__except`  
  
## 参照  
 [純粋なコードと検証可能なコード](../dotnet/pure-and-verifiable-code-cpp-cli.md)