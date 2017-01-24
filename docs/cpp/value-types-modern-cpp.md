---
title: "値型 (Modern C++) | Microsoft Docs"
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
ms.assetid: f63bb62c-60da-40d5-ac14-4366608fe260
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 値型 (Modern C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+ クラスは既定で値型です。  このトピックでは、使用に関連する値型、および問題の基本的な概要を示します。  
  
## 値型と参照  
 さらに述べたように、C\+\+ クラスは既定で値型です。  これらはポリモーフィック動作はオブジェクト指向プログラミングをサポートできる参照型として指定できます。  値型は、メモリとレイアウト コントロールの観点から参照型はポリモーフィック目的のための基本クラスと仮想関数についての場合、表示されます。  コピー コンストラクターまたはコピー代入演算子を使用することを意味します既定で、値型はコピーです。  参照型の場合、クラスの非コピー \(コピー コンストラクターまたはコピー代入演算子を無効にしてください\) し、その目的のポリモーフィズムをサポートする仮想デストラクターを使用します。  値型は個別に変更できる 2 種類の個別の値を常に提供内容についてコピーするときは、です。  参照型は、識別子–について、どのようなオブジェクトにすることもできます。  したがって、「ポリモーフィック型」型」は、「と呼ばれます。  
  
 実際に参照に似た型 \(基本クラス\)、仮想関数が必要な場合は、明示的に次のコードを `MyRefType` クラスに示すように、コピーを無効にする必要があります。  
  
```cpp  
  
// cl /EHsc /nologo /W4  
  
class MyRefType {  
private:  
    MyRefType & operator=(const MyRefType &);  
    MyRefType(const MyRefType &);  
public:  
    MyRefType () {}  
};  
  
int main()  
{  
    MyRefType Data1, Data2;  
    // ...  
    Data1 = Data2;  
}  
```  
  
 上記のコードをコンパイルすると、次のエラーが発生する:  
  
  **test.cpp \(15\) : エラー: C2248 「MyRefType::operator \=」: クラス「MyRefType」で宣言されているプライベート メンバーにアクセスできません。**  
 **meow.cpp \(5\) : 参照してください「MyRefType::operator の宣言を \=」**  
 **meow.cpp \(3\) : 参照してください「MyRefType」の宣言を**   
## 値型、および移動効率  
 コピーの割り当てのオーバーヘッドが新しいコピーの最適化が避けられた原因です。  たとえば、文字列のベクターの途中で文字列を挿入すると、ベクターの開発中に生じることだけがコピーを再配分を移動できません。  たとえば、他の操作に適用し、2 個の大きいオブジェクト非常に追加の操作を実行します。  どのようにこれらの操作が最適化を評価することが可能になります。  C\+\+ コンパイラでは、コンパイラはコンパイラによってコピー コンストラクターと同様に、暗黙的な、これを自動的に生成できるようになります。  ただし、Visual C\+\+ でクラス定義の宣言で割り当ておよびコンストラクターを移動すると、クラスは「選択」を付ける必要があります。  これにより、適切なメンバー関数宣言の二重アンパサンド \(&&\) rvalue 参照を使用し、移動コンストラクターと移動割り当てのメソッドを定義することによって実現されます。ソース オブジェクトから「したり内臓」を正しいコードを挿入する必要があります。  
  
 有効な移動を必要とするかどうかを決定します。  既にわかっているディープ コピーより安い場合は、有効なコピーの構築、関連付けますが有効な移動が必要です。  ただし、確認して移動サポートが必要となるため、有効なコピーが必要なことを意味するとは限りません。  後者の場合は「移動のみ」と呼ばれます。  標準ライブラリの例は、既に `unique_ptr`です。  注釈として、古い `auto_ptr` は C\+\+ の前のバージョンの移動セマンティクス サポートがないため、`unique_ptr` と使用されなくなり、正確に置き換えられました。  
  
 移動セマンティクスを使用して戻り値渡しまたは中央に挿入できます。  コピーの最適化に移動します。  代替手段としてヒープ割り当ての必要があります。  次の擬似コードを検討する:  
  
```cpp  
  
#include <set>  
#include <vector>  
#include <string>  
using namespace std;  
  
//...  
set<widget> LoadHugeData() {  
    set<widget> ret;  
    // ... load data from disk and populate ret  
    return ret;  
}  
//...  
widgets = LoadHugeData();   // efficient, no deep copy  
  
vector<string> v = IfIHadAMillionStrings();  
v.insert( begin(v)+v.size()/2, "scott" );   // efficient, no deep copy-shuffle  
v.insert( begin(v)+v.size()/2, "Andrei" );  // (just 1M ptr/len assignments)  
//...  
HugeMatrix operator+(const HugeMatrix& , const HugeMatrix& );  
HugeMatrix operator+(const HugeMatrix& ,       HugeMatrix&&);  
HugeMatrix operator+(      HugeMatrix&&, const HugeMatrix& );  
HugeMatrix operator+(      HugeMatrix&&,       HugeMatrix&&);  
//...  
hm5 = hm1+hm2+hm3+hm4+hm5;   // efficient, no extra copies  
```  
  
### 適切な値型の移動を有効にします。  
 移動が詳細コピーよりビットという値に似たクラスについて効率の移動構築および移動割り当てを有効にします。  次の擬似コードを検討する:  
  
```cpp  
  
#include <memory>  
#include <stdexcept>  
using namespace std;  
// ...  
class my_class {  
    unique_ptr<BigHugeData> data;  
public:  
    my_class( my_class&& other )   // move construction  
        : data( move( other.data ) ) { }  
    my_class& operator=( my_class&& other )   // move assignment  
    { data = move( other.data ); return *this; }  
    // ...  
    void method() {   // check (if appropriate)  
        if( !data )   
            throw std::runtime_error("RUNTIME ERROR: Insufficient resources!");  
    }  
};  
  
```  
  
 コピーの構築と割り当てを有効にする場合は、詳細コピーより安い移動構築\/割り当てを有効にします。  
  
 ある *値* 型以外はロールアップ リソースの所有権を複製を作成する場合にのみ、移動などです。  例 : `unique_ptr`。  
  
## セクション  
 Content  
  
## 参照  
 [C\+\+ 型システム](../Topic/C++%20Type%20System%20\(Modern%20C++\).md)   
 [C\+\+ へようこそ](../Topic/Welcome%20Back%20to%20C++%20\(Modern%20C++\).md)   
 [C\+\+ 言語リファレンス](../cpp/cpp-language-reference.md)   
 [C\+\+ 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)