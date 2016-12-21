---
title: "オブジェクトの有効期間とリソースの管理 (Modern C++) | Microsoft Docs"
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
ms.assetid: 8aa0e1a1-e04d-46b1-acca-1d548490700f
caps.latest.revision: 18
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# オブジェクトの有効期間とリソースの管理 (Modern C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

マネージ言語とは異なり、C\+\+ では、プログラムの実行時に自動的に非 LONG 使用されるメモリ リソースを解放するガベージ コレクション \(GC\) はありません。  C\+\+ では、リソース管理によって、オブジェクトの有効期間に直接関連しています。  ここでは、C\+\+ オブジェクトの有効期間とそれを管理する方法に影響を与える要因について説明します。  
  
 基本的に、メモリ リソースを処理しないため、C\+\+ in GC はありません。  C\+\+ のような確定のデストラクターだけメモリと非メモリ リソースを均等に処理できます。  GC は、CPU とメモリの消費を高くオーバーヘッドなどの問題、局所性があります。  ただし、普遍性は上手に最適化によって軽減できない基本的な問題です。  
  
## 概念  
 オブジェクトの有効期間管理の重要な処理がオブジェクトを使用してリソースを一切所有するかどうかをカプセル化だれでも、そのリソースを所有するオブジェクト、またはそれらを回避方法にも何かを知る必要がありません。  この場合は、オブジェクトを破棄する必要があります。  C\+\+ のコア言語はブロックが生成されるときに、オブジェクトが適切な時刻、つまり破棄される構築の順序でできるように設計されています。  オブジェクトが破棄されると、ベースおよびメンバーは、特定の順序で破棄されます。言語が自動的にヒープ割り当てや仮引数付きの new などの特別な処理を行う、オブジェクトを破棄します。たとえば、[スマート ポインター](../cpp/smart-pointers-modern-cpp.md) は `vector`が、デストラクターを持つオブジェクトの `new`\/`delete` と `new[]`\/`delete[]` をカプセル化するように `unique_ptr` と `shared_ptr`とテンプレート ライブラリ \(STL\) 標準コンテナーを使用します。  こうした理由から、スマート ポインターと STL コンテナーを使用することがきわめて重要です。  
  
 有効期間管理のもう一つの重要な概念: デストラクター。  デストラクターはリリース リソースをカプセル化します。\(一般的にそれは RRID リソースのリリースで破棄します\)。リソースは、「System」Get、後で渡す必要があることです。メモリは、共通のリソースですが、ファイル、ソケット、テクスチャなどの非メモリ リソースが含まれます。リソースを所有することは」処理を終了するときに必要になりますが、それを解放する必要があるときに使用できることを意味します。オブジェクトが破棄されると、デストラクターは、所有するすべてのリソースを解放します。  
  
 最終的な概念は DAG \(有向非循環グラフ\) です。プログラムの所有権構造体は DAG を形成します。  オブジェクトは、事前に、本質的に無意味なそれ自体だけでなく、所有することはできません。  ただし、次の 2 種類のオブジェクトが 3 番目のオブジェクトの所有権を共有できます。複数の種類のリンクには、このような DAG で有効です: A、B のメンバー \(B は A\) の C ストアを `vector<D>` \(C D の各要素を所有する\)、オンラインのストアは `shared_ptr<F>` \(E は他のオブジェクトと F の所有権を、その共有\) などを所有します。循環参照がないと DAG のすべてのリンクがデストラクター \(生ポインター、ハンドル、またはそのほかの機能の代わりにあるオブジェクトによって表される限り、言語が問題を防ぐため、リソースのリークは不可能です。  リソースは、ガベージ コレクターを実行せずに、不要になった直後に解放されます。  有効期間の追跡は `shared_ptr`のスタック スコープ、ベース メンバー、および関連する場合にオーバーヘッドなし、小さくなります。  
  
### ヒープ ベースの有効期間  
 ヒープ オブジェクトの有効期間に、[スマート ポインター](../cpp/smart-pointers-modern-cpp.md)を使用します。  既定のポインターやアロケーターとして `shared_ptr` と `make_shared` を使用します。  サイクルを切り離すことに `weak_ptr` を使用してキャッシュを、および有効期間について何も影響を付けたり、想定しないでオブジェクトを確認します。  
  
```cpp  
void func() {  
  
auto p = make_shared<widget>(); // no leak, and exception safe  
...  
p->draw();   
  
} // no delete required, out-of-scope triggers smart pointer destructor  
  
```  
  
 *pimpl の* 表現で一意の所有権に `unique_ptr` \(たとえば、使用します。\(「[コンパイル時のカプセル化の Pimpl](../cpp/pimpl-for-compile-time-encapsulation-modern-cpp.md)」を参照\)。`new` のすべての明示的な式の `unique_ptr` にプライマリ ターゲットを実行します。  
  
```cpp  
unique_ptr<widget> p(new widget());  
```  
  
 非所有権、観測に生ポインターを使用できます。  非所有のぶら下がるし続けることはできません。  
  
```cpp  
class node {  
  ...  
  vector<unique_ptr<node>> children; // node owns children  
  node* parent; // node observes parent, which is not a concern  
  ...  
};  
node::node() : parent(...) { children.emplace_back(new node(...) ); }  
  
```  
  
 パフォーマンスの最適化が必要な場合、完全 *カプセル化* できるようにする必要があります。削除するポインターと明示的な呼び出しを所有します。  例では、独自の低レベルのデータ構造を実装する場合です。  
  
### スタック ベースの有効期間  
 新しい C\+\+ では、*スタック ベースのスコープは* 自動 *スタック有効期間を* 組み合わせて、効率の有効期間の追跡の *データ メンバーが有効期間* オーバーヘッドは主にないため、堅牢なコードを作成するための有効な手段です。  ヒープ オブジェクトの有効期間は、特に生ポインターを使用するときに入念に手動管理を必要とし、リソース リークと効率の原因となる可能性があります。  スタック ベースのスコープを説明する例を示します。、:  
  
```cpp  
class widget {  
private:  
  gadget g;   // lifetime automatically tied to enclosing object  
public:  
  void draw();  
};  
  
void functionUsingWidget () {  
  widget w;   // lifetime automatically tied to enclosing scope  
              // constructs w, including the w.g gadget member  
  …  
  w.draw();  
  …  
} // automatic destruction and deallocation for w and w.g  
  // automatic exception safety,   
  // as if "finally { w.dispose(); w.g.dispose(); }"  
  
```  
  
 問題が発生する可能性があるため、静的な有効期間を多用しないようにしてください \(グローバル静的関数、関数のローカル静的\)。  グローバル オブジェクトのコンストラクターが例外をスローするとどうなりますか。  通常、アプリケーションでは、デバッグが困難になることがある方法で使用します。  構築の順序は静的な有効期間が短いオブジェクトに問題となり、同時実行セーフではありません。  だけでなく、特にポリモーフィズムが複雑な場合にオブジェクトの構築と破棄が問題の順序複雑になる場合があります。  オブジェクトはポリモーフィックまたは変数が、順序が複雑な構築\/破棄がないように、スレッド セーフの同時実行の問題があります。  マルチスレッド アプリケーションでは、スレッド ローカル ストレージ ロック、リソース、およびそのほかの特殊な対策を開かずに安全に静的オブジェクトのデータを変更することはできません。  
  
## 参照  
 [C\+\+ へようこそ](../Topic/Welcome%20Back%20to%20C++%20\(Modern%20C++\).md)   
 [C\+\+ 言語リファレンス](../cpp/cpp-language-reference.md)   
 [C\+\+ 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)