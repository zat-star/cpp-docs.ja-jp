---
title: "Arrays (C++ Component Extensions) | Microsoft Docs"
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
  - "cli::array"
  - "details::array"
  - "lang::array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "array keyword [C++]"
  - "declaring arrays, about declaring arrays"
  - "arrays [C++], multidimensional"
  - "multidimensional arrays"
  - "arrays [C++]"
ms.assetid: 49445812-d775-4db1-a231-869598dbb955
caps.latest.revision: 34
caps.handback.revision: 34
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Arrays (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`Platform::Array<T>` は [!INCLUDE[cppwrt_short](../Token/cppwrt_short_md.md)]の型、または [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)]の `array` キーワードは、指定した型と初期値の配列を宣言します。  
  
## すべてのプラットフォーム  
 配列は、右山かっこの後に \(\>\) を使用する宣言でハンドルにオブジェクト \(^\) 修飾子を宣言する必要があります。  
  
 配列の要素数は、型の一部ではありません。  1 種類の配列変数には異なるサイズの配列を指定できます。  
  
 標準 C\+\+ とは異なり、大きなはポインター演算のシノニム、シグネチャ性ではありません。  
  
 配列に関する詳細については、参照します:  
  
-   [配列の共変性](../misc/array-covariance.md)  
  
-   [方法: C\+\+\/CLI で配列を使用する](../dotnet/how-to-use-arrays-in-cpp-cli.md)  
  
-   [方法: 多次元配列を作成する](../misc/how-to-create-multidimension-arrays.md)  
  
-   [方法: マネージ配列の配列を作成する \(ジャグ配列\)](../misc/how-to-create-arrays-of-managed-arrays-jagged-arrays.md)  
  
-   [方法: マネージ配列の Typedef を作成する](../misc/how-to-make-typedefs-for-managed-arrays.md)  
  
-   [方法: マネージ配列をテンプレート型パラメーターとして使用する](../misc/how-to-use-managed-arrays-as-template-type-parameters.md)  
  
-   [Variable Argument Lists \(...\) \(C\+\+\/CLI\)](../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md)  
  
-   [方法: 配列を並べ替える](../misc/how-to-sort-arrays.md)  
  
-   [方法: カスタム条件を使用して配列を並べ替える](../misc/how-to-sort-arrays-using-custom-criteria.md)  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 配列は `Platform` の名前空間のメンバーです。  配列は、1 次元となります。  
  
 **構文**  
  
 構文の最初の例では、配列を割り当てるに `ref new` の集計のキーワードを使用します。  2 番目の例は、ローカル配列を宣言します。  
  
```  
  
        [qualifiers] [Platform::]Array<[qualifiers] array-type [,rank]>^ identifier = ref new [Platform::]Array< initialization-type > [{initialization-list [,...]}]  
  
[qualifiers] [Platform::]Array<[qualifiers] array-type [,rank]>^ identifier = {initialization-list [,...]}  
  
```  
  
 *qualifiers* \[省略可能\]  
 これらのストレージ クラスの指定子の一つ以上: [変更可能](../cpp/mutable-data-members-cpp.md)、[volatile](../cpp/volatile-cpp.md)、[定数](../cpp/const-cpp.md)、[外部](../cpp/using-extern-to-specify-linkage.md)、[静的](../misc/static-cpp.md)。  
  
 `array-type`  
 配列変数の型を指定します。  有効な型は [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] クラスと基本型、ref クラスおよび構造体、値クラスおよび構造体とネイティブ ポインター \(`type``*`\) です。  
  
 `rank` \[省略可能\]  
 配列の次元の数。  1 にする必要があります。  
  
 `identifier`  
 配列変数の名前。  
  
 `initialization-type`  
 配列を初期化する値の型。  通常、`array-type` と `initialization-type` は同じ型です。  ただし、型は、— `initialization-type` が `array-type`から派生されれば例の場合 `initialization-type` から `array-type`への変換には異なります。  
  
 `initialization-list` \[省略可能\]  
 配列の要素を初期化する向きかっこの値のコンマ区切りのリスト。  たとえば、`rank-size-list` が `(3)`、3 個の要素の 1 次元配列を宣言し、`initialization list` は `{1,2,3}`になる可能性があります。  
  
 **解説**  
  
 型が `__is_ref_array(``type``)`の参照カウント配列かどうかコンパイル時に検出できます。  詳細については、「[Compiler Support for Type Traits](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)」を参照してください。  
  
### 要件  
 コンパイラ オプション: **\/ZW**  
  
### 例  
 次の例では、三つの要素を持つ 100 1 次元配列を作成します。  
  
```  
// cwr_array.cpp  
// compile with: /ZW  
using namespace Platform;  
ref class MyClass {};  
int main() {  
   // one-dimensional array  
   Array<MyClass^>^ My1DArray = ref new Array<MyClass^>(100);  
   My1DArray[99] = ref new MyClass();  
}  
```  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **構文**  
  
 構文の最初の例では、配列を割り当てるに `gcnew` キーワードを使用します。  2 番目の例は、ローカル配列を宣言します。  
  
```  
  
        [qualifiers] [cli::]array<[qualifiers] array-type [,rank] >^ identifier = gcnew [cli::]array< initialization-type [,rank] >(rank-size-list[,...]) [{initialization-list [,...]}]  
  
[qualifiers] [cli::]array<[qualifiers] array-type [,rank] >^ identifier = {initialization-list [,...]}  
  
```  
  
 *qualifiers* \[省略可能\]  
 これらのストレージ クラスの指定子の一つ以上: [変更可能](../cpp/mutable-data-members-cpp.md)、[volatile](../cpp/volatile-cpp.md)、[定数](../cpp/const-cpp.md)、[外部](../cpp/using-extern-to-specify-linkage.md)、[静的](../misc/static-cpp.md)。  
  
 `array-type`  
 配列変数の型を指定します。  有効な型は [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] クラスであり、基本型、ref クラスおよび構造体、値クラスおよび構造体、ネイティブ ポインター \(`type``*`\)、およびネイティブ POD \(plain old data\) を選択します。  
  
 `rank` \[省略可能\]  
 配列の次元の数。  既定は 1; 最大値は 32 です。  配列の各次元自体は配列です。  
  
 `identifier`  
 配列変数の名前。  
  
 `initialization-type`  
 配列を初期化する値の型。  通常、`array-type` と `initialization-type` は同じ型です。  ただし、型は、— `initialization-type` が `array-type`から派生されれば例の場合 `initialization-type` から `array-type`への変換には異なります。  
  
 `rank-size-list`  
 配列の各次元のサイズのコンマ区切りのリスト。  また `initialization-list` パラメーターを指定した場合、各次元のサイズを推論、`rank-size-list` は省略できます。  詳細については、「[方法: 多次元配列を作成する](../misc/how-to-create-multidimension-arrays.md)」を参照してください。  
  
 `initialization-list` \[省略可能\]  
 配列の要素を初期化する向きかっこの値のコンマ区切りのリスト。  または多次元配列要素を初期化する *initialization\-list* 入れ子になった項目のコンマ区切りのリスト。  
  
 たとえば、`rank-size-list` が `(3)`、3 個の要素の 1 次元配列を宣言し、`initialization list` は `{1,2,3}`になる可能性があります。  `rank-size-list` が `(3,2,4)`、最初の次元の二つの要素の 3 次元配列を宣言している要素は 2 個目、2 つ目の要素は 4 個、`initialization-list` は `{{1,2,3},{0,0},{-5,10,-21,99}}`style\=Bold など\)  
  
 **解説**  
  
 `array` は [Platform, default, and cli Namespaces](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md) の名前空間にあります。  
  
 標準 C\+\+ の場合と同様に、配列のインデックスはインデックス番号が 0 から始まるであり、配列は角かっこを使用して subscripted \(\[\]\)。  標準 C\+\+ とは異なり、多次元配列のインデックスは、一連の角かっこ \(\[\]\) 演算子ではなく、各次元に対してインデックス ボックスの一覧で、各次元に対して指定します。  たとえば、*identifier*\[\]*index1*の代わりに *identifier**index1*、*index2*\[\] \[\] *index2*。  
  
 すべてのマネージ配列には `System::Array`から継承します。  `System::Array` のメソッドやプロパティは、配列変数に直接適用できます。  
  
 要素の型は、マネージ クラス ポインターの配列を代入すると、要素は 0 初期化されます。  
  
 要素の型は値型である `V`配列を代入すると、`V` の既定のコンストラクターは、各配列要素に適用されます。  詳細については、「[C\+\+ ネイティブ型と等価な .NET Framework ネイティブ型](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md)」を参照してください。  
  
 コンパイル時に、型が `__is_ref_array(``type``)`の共通言語ランタイム \(CLR\) の配列であるかどうかを確認できます。  詳細については、「[Compiler Support for Type Traits](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)」を参照してください。  
  
### 要件  
 コンパイラ オプション: **\/clr**  
  
### 例  
 次の例では、三つの要素を持つ 100 次元で、最初の三つの要素を持つ 3 次元配列は、5 個の要素 2 番目、および 6 番目の二つの要素が 1 次元配列を作成します。  
  
```  
// clr_array.cpp  
// compile with: /clr  
ref class MyClass {};  
int main() {  
   // one-dimensional array  
   array<MyClass ^> ^ My1DArray = gcnew array<MyClass ^>(100);  
   My1DArray[99] = gcnew MyClass();  
  
   // three-dimensional array  
   array<MyClass ^, 3> ^ My3DArray = gcnew array<MyClass ^, 3>(3, 5, 6);  
   My3DArray[0,0,0] = gcnew MyClass();  
}  
```  
  
## 参照  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)