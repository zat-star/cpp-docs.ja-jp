---
title: "Platform, default, and cli Namespaces  (C++ Component Extensions) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "lang"
  - "cli"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "lang namespace"
  - "cli namespace"
ms.assetid: 9d38bd1e-dc78-47d1-a84b-9b4683e52c9c
caps.latest.revision: 19
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Platform, default, and cli Namespaces  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

言語要素の名前は名前空間によって修飾されるため、それ以外は同じである名前と、ソース コードの別の部分で競合することはありません。  たとえば、名前が競合すると、コンパイラで[状況依存のキーワード](../windows/context-sensitive-keywords-cpp-component-extensions.md)を認識できなくなる場合があります。  名前空間はコンパイラによって使用されますが、コンパイルされたアセンブリでは保持されません。  
  
## すべてのランタイム  
 Visual C\+\+ では、プロジェクトの作成時に、既定の名前空間がプロジェクトに与えられます。  名前空間の名前は手動で変更できますが、[!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] では、.winmd ファイルの名前が、ルート名前空間の名前と一致する必要があります。  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 詳細については、「[名前空間と型の参照範囲 \(C\+\+\/CX\)](http://msdn.microsoft.com/library/windows/apps/hh969551.aspx)」を参照してください。  
  
### 必要条件  
 コンパイラ オプション: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **構文**  
  
```  
using namespace cli;  
```  
  
 **コメント**  
  
 [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)] は `cli` 名前空間をサポートしています。  **\/clr** を指定してコンパイルする場合、Syntax セクションの `using` ステートメントが適用されます。  
  
 次の言語機能は、`cli` 名前空間に含まれます。  
  
-   [Arrays](../windows/arrays-cpp-component-extensions.md)  
  
-   [interior\_ptr \(C\+\+\/CLI\)](../windows/interior-ptr-cpp-cli.md)  
  
-   [pin\_ptr \(C\+\+\/CLI\)](../Topic/pin_ptr%20\(C++-CLI\).md)  
  
-   [safe\_cast](../windows/safe-cast-cpp-component-extensions.md)  
  
### 必要条件  
 コンパイラ オプション: **\/clr**  
  
### 使用例  
 **例**  
  
 次のコード例は、`cli` 名前空間のシンボルをユーザー定義シンボルとしてコードで使用できることを示します。  ただし、この場合は、同じ名前の `cli` 言語要素への参照を明示的または暗黙的に修飾する必要があります。  
  
```  
// cli_namespace.cpp  
// compile with: /clr  
using namespace cli;  
int main() {  
   array<int> ^ MyArray = gcnew array<int>(100);  
   int array = 0;  
  
   array<int> ^ MyArray2 = gcnew array<int>(100);   // C2062  
  
   // OK  
   cli::array<int> ^ MyArray2 = gcnew cli::array<int>(100);  
   ::array<int> ^ MyArray3 = gcnew ::array<int>(100);  
}  
```  
  
## 参照  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)