---
title: "code_seg (__declspec) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "code_seg_cpp"
  - "code_seg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "code_seg __declspec キーワード"
ms.assetid: ad3c1105-15d3-4e08-b7b9-e4bd9d7b6aa0
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# code_seg (__declspec)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 `code_seg` 宣言属性では、.obj ファイル内で関数やクラス メンバー関数のオブジェクト コードが格納される実行可能なテキスト セグメントを指定します。  
  
## 構文  
  
```  
__declspec(code_seg("segname")) declarator  
```  
  
## 解説  
 `__declspec(code_seg(...))` 属性では、メモリ内でそれぞれページングまたはロックできる個別の名前のセグメントにコードを格納できます。  この属性を使用して、インスタンス化されたテンプレートとコンパイラによって生成されたコードの格納場所を制御できます。  
  
 *セグメント*は、.obj ファイル内でメモリへの読み込み単位となる名前付きのデータ ブロックです。  *テキスト セグメント*は、実行可能なコードが格納されるセグメントです。  *セクション*という用語はセグメントの同義語として使用されることがよくあります。  
  
 `declarator` が定義されているときに生成されるオブジェクト コードは、ナロー文字列リテラルである `segname` で指定されたテキスト セグメントに格納されます。  `segname` という名前は、宣言で使用する前に、[セクション](../preprocessor/section.md) プラグマで指定する必要はありません。  既定では、`code_seg` が指定されていないと、オブジェクト コードは .text という名前のセグメントに格納されます。  `code_seg` 属性は、既存のいずれの [\#pragma code\_seg](../preprocessor/code-seg.md) ディレクティブよりも優先されます。  メンバー関数に適用された `code_seg` 属性は、外側のクラスに適用されたいずれの `code_seg` 属性よりも優先されます。  
  
 エンティティが `code_seg` 属性を持っている場合、同じエンティティのすべての宣言と定義も同じ `code_seg` 属性を持っている必要があります。  基底クラスが `code_seg` 属性を持っている場合、派生クラスも同じ属性を持っている必要があります。  
  
 `code_seg` 属性が名前空間スコープ関数またはメンバー関数に適用されると、その関数のオブジェクト コードは、指定されたテキスト セグメント内に格納されます。  この属性がクラスに適用されると、そのクラスおよび入れ子にされたクラスのメンバー関数はすべて \(コンパイラによって生成された特殊なメンバー関数も含めて\)、指定されたセグメントに格納されます。  ローカルに定義されたクラス \(メンバー関数本体で定義されたクラスなど\) は外側のスコープの `code_seg` 属性を継承しません。  
  
 `code_seg` 属性がテンプレート クラスまたはテンプレート関数に適用されると、テンプレートの暗黙的な特殊化はすべて、指定されたセグメントに格納されます。  明示的または部分的な特殊化はプライマリ テンプレートから `code_seg` 属性を継承しません。  特殊化に指定する `code_seg` 属性はプライマリ テンプレートのものと同じでも違っていてもかまいません。  `code_seg` 属性は明示的なテンプレートのインスタンス化に適用することはできません。  
  
 既定では、コンパイラによって生成されたコード \(特殊なメンバー関数など\) は .text セグメントに格納されます。  `#pragma code_seg` ディレクティブよりも、この既定の動作が優先されます。  `code_seg` 属性をクラス、クラス テンプレート、または関数テンプレートに使用して、コンパイラによって生成されたコードの格納場所を制御します。  
  
 ラムダはその外側のスコープから `code_seg` 属性を継承します。  ラムダのセグメントを指定するには、パラメーター宣言句の後ろかつ、mutable または例外の指定、後続の戻り値の型の指定、ラムダ本体の前に、`code_seg` 属性を適用します。  詳細については、「[ラムダ式の構文](../cpp/lambda-expression-syntax.md)」を参照してください。  この例では、ラムダを PagedMem という名前のセグメントに定義しています。  
  
```cpp  
auto Sqr = [](int t) __declspec(code_seg("PagedMem")) -> int { return t*t; };  
```  
  
 特定のメンバー関数 \(特に仮想メンバー関数\) を異なるセグメントに格納するときには注意が必要です。  ページング セグメントに存在する派生クラスの仮想関数を定義する場合、基底クラスのメソッドが非ページング セグメントに存在すると、他の基底クラスのメソッドやユーザー コードは、仮想メソッドの呼び出しによりページ フォールトがトリガーされないと見なすことがあります。  
  
## 使用例  
 この例では、暗黙的および明示的なテンプレート特殊化の使用時に `code_seg` 属性により格納セグメントを制御する方法を示しています。  
  
```  
// code_seg.cpp  
// Compile: cl /EHsc /W4 code_seg.cpp  
  
// Base template places object code in Segment_1 segment  
template<class T>  
class __declspec(code_seg("Segment_1")) Example  
{  
public:  
   virtual void VirtualMemberFunction(T /*arg*/) {}  
};  
  
// bool specialization places code in default .text segment  
template<>  
class Example<bool>   
{  
public:  
   virtual void VirtualMemberFunction(bool /*arg*/) {}  
};  
  
// int specialization places code in Segment_2 segment  
template<>  
class __declspec(code_seg("Segment_2")) Example<int>   
{  
public:  
   virtual void VirtualMemberFunction(int /*arg*/) {}  
};  
  
// Compiler warns and ignores __declspec(code_seg("Segment_3"))  
// in this explicit specialization  
__declspec(code_seg("Segment_3")) Example<short>; // C4071  
  
int main()  
{  
   // implicit double specialization uses base template's  
   // __declspec(code_seg("Segment_1")) to place object code  
   Example<double> doubleExample{};  
   doubleExample.VirtualMemberFunction(3.14L);  
  
   // bool specialization places object code in default .text segment  
   Example<bool> boolExample{};  
   boolExample.VirtualMemberFunction(true);  
  
   // int specialization uses __declspec(code_seg("Segment_2"))  
   // to place object code  
   Example<int> intExample{};  
   intExample.VirtualMemberFunction(42);  
}  
```  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)