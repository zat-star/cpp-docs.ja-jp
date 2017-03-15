---
title: "Partial (C++ コンポーネント拡張) | Microsoft Docs"
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
  - "partial_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "partial"
  - "C + +/CX、partial"
ms.assetid: 43adf1f5-10c5-44aa-a66f-7507e2bdabf8
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Partial (C++ コンポーネント拡張)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`partial` キーワードを使用して、同じ ref クラスの別々の部分を個別に作成したり、別々のファイル内に作成したりできます。  
  
## すべてのランタイム  
 \(この言語機能は [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]にのみ適用されます。\)  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 2 個の部分定義がある ref クラスの場合、`partial` キーワードは最初に出現した定義に適用されます。通常、これは自動生成されたコードによって実行されるため、人間の作成者はこのキーワードをそれほど使用しません。  クラス内の以後の部分定義については、*class\-key* キーワードとクラス ID から `partial` 修飾子を省略します。  コンパイラが定義済み ref クラスおよびクラス ID を検出したときに、`partial` キーワードが指定されていない場合には、ref クラスのすべての部分定義が内部的に 1 つの定義に統合されます。  
  
### 構文  
  
```cpp  
  
partial class-key identifier {  
   /* The first part of the partial class definition. This is typically auto-generated*/  
}  
// ...  
class-key identifier {  
   /* The subsequent part(s) of the class definition. The same identifier is specified, but the "partial" keyword is omitted. */  
}  
  
```  
  
### パラメーター  
 *class\-key*  
 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]でサポートされるクラスまたは構造体を宣言するキーワード。  `ref class`、`value class`、`ref struct`、`value struct` のいずれかになります。  
  
 *identifier*  
 定義される型の名前。  
  
### 解説  
 部分クラスは、1 つのファイル内のクラス定義の一部分を変更するシナリオをサポートします。XAML デザイナーなどの自動コード生成ソフトウェアは、別のファイル内の同じクラスを変更します。  部分クラスを使用することにより、自動コード生成ソフトウェアがコードを上書きすることを防ぐことができます。  Visual Studio プロジェクトでは、生成されたファイルに `partial` 修飾子が自動的に適用されます。  
  
 内容: `partial` キーワードを省略した場合、完全なクラス定義に指定できるすべての要素を 1 つの部分定義で指定することができますが、例外が 2 つあります。  ただし、クラスのアクセシビリティ \(たとえば、`public partial class X {…};`\)、または `declspec`を指定できません。  
  
 *identifier* に部分クラス定義で使用するアクセス指定子は *identifier*の後続の部分的または完全なクラス定義の既定のアクセシビリティには影響しません。  静的データ メンバーはインライン定義できます。  
  
 宣言: *identifier* クラスの部分定義は、名前 *identifier*のみがありますが、*identifier* はクラス定義を必要とする方法では使用できません。  名前 *identifier* が *identifier*のサイズがわかっているときは使用できません。または *identifier* の基本クラスまたはメンバーをコンパイラの後までを使用するように *identifier*の完全な定義が発生します。  
  
 数と順序: *identifier*のゼロことも、より多くの部分クラス定義。  *identifier* のすべての部分クラス定義 \(完全な定義がある構文によって *identifier* の 1 種類の完全な定義を記述する必要があります。; それ以外の場合、クラスは前方宣言\)、*identifier*の事前の宣言に指定する必要がある場合は、以外は使用できません。  すべての class\-key が同じである必要があります。  
  
 完全な定義: *identifier*クラスの定義の時点で、動作は *identifier* の定義が見つかり、部分クラスで定義された順序ですべての基本クラスなど、メンバーを宣言する場合と同じです。  
  
 テンプレート: 部分クラスはテンプレートにできません。  
  
 ジェネリック: 完全な定義をジェネリックにできる場合、部分クラスをジェネリックにできます。  ただし、すべての部分クラスと完全なクラスのジェネリック パラメーターが、仮パラメーター名を含めて厳密に同じであることが必要です。  
  
 この方法の詳細については `partial` キーワードを使用して参照します [Partial Classes \(C\+\+\/CX\)](http://go.microsoft.com/fwlink/p/?LinkId=249023)。  
  
### 要件  
 コンパイラ オプション: **\/ZW**  
  
## 共通言語ランタイム  
 \(この言語機能は共通言語ランタイムには適用されません。\)  
  
## 参照  
 [Partial Classes \(C\+\+\/CX\)](http://go.microsoft.com/fwlink/p/?LinkId=249023)