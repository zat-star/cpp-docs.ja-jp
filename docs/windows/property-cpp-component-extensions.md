---
title: "property  (C++ Component Extensions) | Microsoft Docs"
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
  - "property_cpp"
  - "property"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "property keyword [C++]"
ms.assetid: cc79d2b2-f013-4d81-8252-eece97a18704
caps.latest.revision: 31
caps.handback.revision: 29
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# property  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*プロパティ*を宣言します。プロパティとは、データ メンバーや配列要素と同様に機能し、アクセスできるメンバー関数です。  
  
## すべてのランタイム  
 次のいずれかの種類のプロパティを宣言できます。  
  
 *シンプル プロパティ*  
 既定では、プロパティ値を割り当てる *set アクセサー*、プロパティ値を取得する *get アクセサー*、プロパティ値を含むプライベート データ メンバー \(コンパイラにより生成\) を作成します。  
  
 *プロパティ ブロック*  
 これを使用して、ユーザー定義の get アクセサーまたは set アクセサーを作成します。  get アクセサーおよび set アクセサーの両方が定義されている場合、プロパティの読み取りと書き込みを実行できます。get アクセサーのみが定義されている場合、プロパティは読み取り専用です。set アクセサーのみが定義されている場合、プロパティは書き込み専用です。  
  
 プロパティ値を格納するデータ メンバーを明示的に宣言する必要があります。  
  
 *インデックス プロパティ*  
 1 つ以上のインデックスで指定されるプロパティの値を取得し設定するために使用できるプロパティ ブロック。  
  
 ユーザー定義のプロパティ名または*既定の*プロパティ名を持つインデックス プロパティを作成できます。  既定のインデックス プロパティの名前は、プロパティが定義されているクラスの名前です。  既定のプロパティを宣言するには、プロパティ名ではなく `default` キーワードを指定します。  
  
 プロパティ値を格納するデータ メンバーを明示的に宣言する必要があります。  通常、インデックス プロパティの場合、データ メンバーは配列またはコレクションになります。  
  
### 構文  
  
```cpp  
  
property type property_name;  
  
property type property_name {  
   access-modifier type get() inheritance-modifier {property_body};  
   access-modifier void set(type value) inheritance-modifier {property_body};  
} property type property_name[index_list] {  
   access-modifier type get(index_list) inheritance-modifier {property_body};  
   access-modifier void set(index_list, value) inheritance-modifier {property_body};  
} property type default[index_list] {  
   access-modifier type get(index_list) inheritance-modifier {property_body};  
   access-modifier void set(index_list, value) inheritance-modifier {property_body};  
}  
  
```  
  
### パラメーター  
 `type`  
 プロパティ値のデータ型、つまりプロパティ自体です。  
  
 `property_name`  
 プロパティの名前です。  
  
 `access-modifier`  
 アクセス修飾子。  有効な修飾子は `static` と `virtual`です。  
  
 get アクセサーまたは set アクセサーの `virtual` 修飾子が一致する必要はありませんが、`static` 修飾子は一致する必要があります。  
  
 `inheritance-modifier`  
 継承修飾子。  有効な修飾子は `abstract` と `sealed`です。  
  
 `index_list`  
 1 つ以上のインデックスのコンマ区切りのリスト。  各インデックスは、インデックスの型と、プロパティ メソッドの本文で使用できる識別子 \(省略可能\) で構成されます。  
  
 `value`  
 set 操作でプロパティに代入される値、または get 操作で取得される値。  
  
 `property_body`  
 set アクセサーまたは get アクセサーのプロパティ メソッドの本体。  `property_body` では `index_list` を、基になるプロパティ データ メンバーにアクセスするために使用するか、ユーザー定義処理のパラメーターとして使用できます。  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 詳細については、「[プロパティ \(C\+\+\/CX\)](http://msdn.microsoft.com/library/windows/apps/hh755807.aspx)」を参照してください。  
  
### 必要条件  
 コンパイラ オプション: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **構文**  
  
```  
  
modifier property type property_name;  
  
modifier property type property_name {  
   modifier void set(type);  
   modifier type get();  
}  
modifier property type property_name[index-list, value] {  
   modifier void set(index-list, value);  
   modifier type get(index-list);  
  
modifier property type default[index];  
}  
```  
  
 **パラメーター**  
  
 *modifier*  
 プロパティの宣言または get\/set アクセサー メソッドで使用できる修飾子。  有効な値は、`static` と `virtual` です。  
  
 *型*  
 プロパティで表される値の型。  
  
 *property\_name*  
 raise メソッドのパラメーター。デリゲートのシグネチャと一致する必要があります。  
  
 *index\_list*  
 1 つ以上のインデックスのリスト \(コンマ区切り\)。角かっこ \(添字演算子 \[\]\) で囲んで指定します。  各インデックスについて型を指定し、さらに必要に応じてプロパティ メソッドの本文で使用できる識別子も指定します。  
  
 **コメント**  
  
 最初の構文サンプルでは、*シンプル プロパティ*を示しています。ここでは `set` メソッドと `get` メソッドの両方を暗黙的に宣言しています。  コンパイラは自動的にプロパティの値を格納するためのプライベート フィールドを作成します。  
  
 2 つ目の構文サンプルでは、*プロパティ ブロック*を示しています。ここでは `set` メソッドと `get` メソッドの両方を明示的に宣言しています。  
  
 3 つ目の構文サンプルでは、ユーザー定義の*インデックス プロパティ*を示しています。  インデックス プロパティは、設定または取得する値だけでなくパラメーターも受け取ります。  プロパティに名前を指定する必要があります。  シンプル プロパティとは異なり、インデックス プロパティの `set` メソッドと `get` メソッドは明示的に定義する必要があり、さらにプロパティの名前も指定する必要があります  
  
 4 つ目の構文サンプルでは、型のインスタンスに対して配列と同様にアクセスできるようにする、*既定の*プロパティを示しています。  `default` キーワードは、既定のプロパティを指定する場合にのみ使用されます。  既定のプロパティの名前は、プロパティが定義されている型の名前です。  
  
 `property` キーワードは、クラス、インターフェイス、または値の型で使用できます。  プロパティには get 関数 \(読み取り専用\)、set 関数 \(書き込み専用\)、またはその両方 \(読み取り\/書き込み\) を定義できます。  
  
 プロパティ名は、それ自身が含まれるマネージ クラスの名前と同じにすることはできません。  getter 関数の戻り値の型は、対応する setter 関数の最後のパラメーターの型と一致する必要があります。  
  
 クライアント コードに対しては、プロパティは通常のデータ メンバーと同じように扱うことができ、データ メンバーと同じ構文を使用して書き込みまたは読み取りを実行できます。  
  
 get メソッドと set メソッドの `virtual` 修飾子が一致する必要はありません。  
  
 get メソッドと set メソッドのアクセシビリティが異なっていても問題ありません。  
  
 プロパティ メソッドの定義は、通常のメソッドと同様に、クラスの本文の外でも表示できます。  
  
 プロパティの get メソッドと set メソッドの **static** 修飾子は一致していても問題ありません。  
  
 プロパティの get メソッドと set メソッドが次の説明に適合している場合、そのプロパティはスカラーです。  
  
-   get メソッドにはパラメーターがなく、戻り値の型は `T` です。  
  
-   set メソッドには `T` 型のパラメーターがあり、戻り値の型は **void** です。  
  
 同じ ID のスコープ内では、1 つのスカラー プロパティしか宣言できません。  スカラー プロパティはオーバーロードできません。  
  
 プロパティ データ メンバーを宣言すると、コンパイラはクラスにデータ メンバーを挿入します。このデータ メンバーは "バッキング ストア" とも呼ばれます。  ただし、このデータ メンバーの名前は、外側のクラスの実際のデータ メンバーであるかのように、ソース内のメンバーを参照できないような形式になっています。  型のメタデータを表示し、プロパティのバッキング ストアに対してコンパイラが生成した名前を確認するには、ildasm.exe を使用します。  
  
 プロパティ ブロック内のアクセサー メソッドについては、異なるアクセシビリティが許容されます。  つまり、set メソッドをパブリックに、get メソッドをプライベートにすることができます。  ただし、アクセサー メソッドのアクセシビリティが、プロパティ自体の宣言でのアクセシビリティよりも制限が少ない場合、エラーになります。  
  
 `property` は状況依存のキーワードです。  詳細については、「[状況依存のキーワード](../windows/context-sensitive-keywords-cpp-component-extensions.md)」を参照してください。  
  
 プロパティの詳細については、次を参照してください。  
  
-   [インデックス付きプロパティ](../misc/how-to-use-indexed-properties.md)  
  
-   [静的プロパティ](../misc/how-to-declare-and-use-static-properties.md)  
  
-   [仮想プロパティ](../misc/how-to-declare-and-use-virtual-properties.md)  
  
-   [多次元プロパティ](../Topic/How%20to:%20Use%20Multidimensional%20Properties.md)  
  
-   [プロパティ アクセサー メソッドのオーバーロード](../misc/how-to-overload-property-accessor-methods.md)  
  
-   [方法: 抽象プロパティとシール プロパティを宣言する](../misc/how-to-declare-abstract-and-sealed-properties.md)  
  
### 必要条件  
 コンパイラ オプション: **\/clr**  
  
### 使用例  
 次の例は、プロパティのデータ メンバーとプロパティ ブロックの宣言方法と使用方法を示しています。  これにより、プロパティ アクセサーがクラスから定義できることもわかります。  
  
```  
// mcppv2_property.cpp  
// compile with: /clr  
using namespace System;  
public ref class C {  
   int MyInt;  
public:  
  
   // property data member  
   property String ^ Simple_Property;  
  
   // property block  
   property int Property_Block {  
  
      int get();  
  
      void set(int value) {  
         MyInt = value;  
      }  
   }  
};  
  
int C::Property_Block::get() {  
   return MyInt;  
}  
  
int main() {  
   C ^ MyC = gcnew C();  
   MyC->Simple_Property = "test";  
   Console::WriteLine(MyC->Simple_Property);  
  
   MyC->Property_Block = 21;  
   Console::WriteLine(MyC->Property_Block);  
}  
```  
  
 **出力**  
  
  **テスト**  
 **21**   
## 参照  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)