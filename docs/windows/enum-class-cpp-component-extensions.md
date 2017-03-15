---
title: "enum クラス (C++ コンポーネント拡張) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
ms.assetid: 8010fa8c-bad6-45b4-8214-b4db64d7ffe1
caps.latest.revision: 23
caps.handback.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# enum クラス (C++ コンポーネント拡張)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

名前空間スコープで列挙型を宣言します。列挙型とは、列挙子と呼ばれる一連の名前付き定数で構成されるユーザー定義型です。  
  
## すべてのランタイム  
 **解説**  
  
 C\+\+\/CX および C\+\+\/CLI は、`public enum class` と `private enum class` をサポートします。これは標準の C\+\+ `enum class` と似ていますが、アクセシビリティ指定子が追加されている点が異なります。**\/clr** では、C\+\+11 `enum class` 型を使用できますが、C\+\+\/CX および C\+\+\/CLI の型ではなく ISO の列挙型でよいかどうかを確認する警告 C4472 が生成されます。 ISO 標準の C\+\+ の `enum` キーワードについて詳しくは、「[列挙体](../cpp/enumerations-cpp.md)」をご覧ください。  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 **構文**  
  
```  
  
access  
enum class  
enumeration-identifier  
[:underlying-type] { enumerator-list } [var]; accessenum structenumeration-identifier[:underlying-type] { enumerator-list } [var];  
```  
  
 **パラメーター**  
  
 *access*  
 列挙型のアクセシビリティ。`public` または `private` を指定できます。  
  
 *enumeration\-identifier*  
 列挙型の名前。  
  
 *underlying\-type*  
 \(省略可能\) 列挙型の基になる型。  
  
 \(省略可能、[!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]のみ\) 列挙型の基になる型。`bool`、`char`、`char16`、`int16`、`uint16`、`int`、`uint32`、`int64`、`uint64` のいずれかを指定できます。  
  
 *enumerator\-list*  
 列挙子名のコンマ区切りのリスト。  
  
 それぞれの列挙子の値は、コンパイラによって暗黙的に定義された定数式か、"*enumerator* `=` *constant\-expression*" という表記で明示的に定義された定数式になります。 既定では、最初の列挙子が暗黙的に定義されている場合、その値は 0 です。 それ以降の暗黙的に定義された列挙子の値は、前の列挙子の値に 1 を加算した値になります。  
  
 *var*  
 \(省略可能\) 列挙型の変数の名前。  
  
 **解説**  
  
 使用例を含む詳細については、「[列挙型](http://msdn.microsoft.com/%20library/windows/apps/hh755820.aspx)」をご覧ください。  
  
 列挙子の値を定義する定数式が *underlying\-type* で表すことができない場合、コンパイラはエラー メッセージを生成します。  ただし、基になる型に対して値が不適切であるというエラーは生成されません。 例:  
  
-   *underlying\-type* が数値であり、列挙子がその型の最大値を指定する場合は、次に暗黙的に定義されている列挙型の値は表すことができません。  
  
-   *underlying\-type* が `bool` であり、3 つ以上の列挙子が暗黙的に定義されている場合、最初の 2 つの列挙子より後の列挙子は表すことができません。  
  
-   *underlying\-type* が `char16` であり、列挙型の値が 0xD800 から 0xDFFF の範囲にある場合、その値を表すことができます。 この値は Unicode サロゲート ペアの一方を表していますが、このペアは分離して表すことができないため、論理的にはこの値は正しくありません。  
  
### 要件  
 コンパイラ オプション: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **構文**  
  
```  
  
access  
enum class  
name [:type] { enumerator-list } var; accessenum structname [:type] { enumerator-list } var;  
```  
  
 **パラメーター**  
  
 `access`  
 列挙型のアクセシビリティ。**public** または `private` を指定できます。  
  
 `enumerator-list`  
 列挙型に含まれる識別子 \(列挙子\) のコンマ区切りのリスト。  
  
 `name`  
 列挙型の名前。  匿名のマネージ列挙型は使用できません。  
  
 `type` \(省略可能\)  
 *識別子*の基になる型。  符号付きまたは符号なしの int、short、long など、任意のスカラー型を指定できます。`bool` または `char` も使用できます。  
  
 `var` \(省略可能\)  
 列挙型の変数の名前。  
  
 **解説**  
  
 **enum class** と **enum struct** は同等の宣言です。  
  
 列挙型には、マネージ \(C\+\+\/CX\) 列挙型と標準列挙型の 2 種類があります。  
  
 マネージ \(C\+\+\/CX\) 列挙型は、たとえば次のように定義されます。  
  
```cpp  
public enum class day {sun, mon };  
```  
  
 これは、次のコードと同じ意味です。  
  
```cpp  
ref class day { public: static const int sun = 0; static const int mon = 1; };  
```  
  
 標準列挙型は、たとえば次のように定義されます。  
  
```cpp  
enum day2 { sun, mon };  
```  
  
 これは、次のコードと同じ意味です。  
  
```cpp  
static const int sun = 0; static const int mon = 1;  
```  
  
 マネージ列挙子の名前 \(*識別子*\) は、列挙型が定義されるスコープに挿入されません。列挙子へのすべての参照が完全修飾名であることが必要です \(*名前*`::`*識別子*\)。  そのため、匿名のマネージ列挙型は定義できません。  
  
 標準列挙型の列挙子は外側のスコープに厳密に挿入されます。  そのため、列挙子と同じ名前を持つ別のシンボルが外側のスコープにある場合、コンパイラはエラーを生成します。  
  
 Visual C\+\+ 2002 と Visual C\+\+ 2003 では、列挙子は弱く挿入されていました \(同じ名前の別の識別子が存在していない限り外側のスコープで参照可能\)。  
  
 C\+\+ 標準列挙型が定義されている \(**class** も `struct` も指定されていない\) 場合、**\/clr** を指定してコンパイルすると、列挙型がマネージ列挙型としてコンパイルされます。  この列挙型のセマンティクスはアンマネージ列挙型のままです。  コンパイラはその列挙型をネイティブ列挙型にするというプログラマの意図を示すために、Visual C\+\+ コンパイラが認識する [Microsoft::VisualC::NativeEnumAttribute](assetId:///Microsoft::VisualC::NativeEnumAttribute?qualifyHint=False&autoUpgrade=True) 属性を挿入します。  他のコンパイラは、標準列挙型を単にマネージ列挙型として認識します。  
  
 \/clr を指定してコンパイルされた名前付きの標準列挙型は、アセンブリでマネージ列挙型として参照可能であり、他のマネージ コンパイラでも実行できます。   ただし、名前のない標準列挙体は、アセンブリからパブリックに参照することができません。  
  
 Visual C\+\+ 2002 と Visual C\+\+ 2003 では、標準列挙型は関数のパラメーターの型として使用されていました。  
  
```cpp  
// mcppv2_enum.cpp // compile with: /clr enum E { a, b }; void f(E) {System::Console::WriteLine("hi");} int main() { E myi = b; f(myi); }  
```  
  
 これは、関数のシグネチャに対応して MSIL に次の出力を行います。  
  
```  
void f(int32);  
```  
  
 ただし、現在のバージョンのコンパイラでは、\[NativeEnumAttribute\] を指定すると標準列挙型がマネージ列挙型として出力され、関数のシグネチャに対応して MSIL に次の出力を行います。  
  
```  
void f(E)  
```  
  
 ネイティブ列挙型の詳細については、「[C\+\+ 列挙体の宣言](../cpp/enumerations-cpp.md)」を参照してください。  
  
 CLR 列挙型の詳細については、次のページを参照してください。  
  
-   [Underlying Type of an Enum \(列挙型の基になる型\)](../Topic/How%20to:%20Define%20and%20consume%20enums%20in%20C++-CLI.md)  
  
-   [Managed and Standard Enumerations \(マネージ列挙型と標準列挙型\)](../misc/how-to-convert-between-managed-and-standard-enumerations.md)  
  
-   [Operators and Enumerations \(演算子と列挙型\)](../Topic/Operators%20and%20Enumerations.md)  
  
### 必要条件  
 コンパイラ オプション: **\/clr**  
  
### 例  
 **例**  
  
 説明  
  
```cpp  
// mcppv2_enum_2.cpp // compile with: /clr // managed enum public enum class m { a, b }; // standard enum public enum n { c, d }; // unnamed, standard enum public enum { e, f } o; int main() { // consume managed enum m mym = m::b; System::Console::WriteLine("no automatic conversion to int: {0}", mym); System::Console::WriteLine("convert to int: {0}", (int)mym); // consume standard enum n myn = d; System::Console::WriteLine(myn); // consume standard, unnamed enum o = f; System::Console::WriteLine(o); }   
```  
  
 **出力**  
  
```Output  
no automatic conversion to int: b  
 convert to int: 1  
 1  
 1  
  
```  
  
## 参照  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)