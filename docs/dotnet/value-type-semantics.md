---
title: "値の型のセマンティクス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- interior_ptr keyword [C++]
- virtual functions, value types
- inheritance, value types
- pinning pointers
- pin_ptr keyword [C++]
- __pin keyword
ms.assetid: 7f065589-ad25-4850-baf1-985142e35e52
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 21a7d6bcba2fca3fddd6f5e234663d6791398f5d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="value-type-semantics"></a>値型セマンティクス
値型のセマンティクスは、Visual C に C++ のマネージ拡張から変更されました。  
  
 C++ の仕様のマネージ拡張で使用される標準的な値型を次に示します。  
  
```  
__value struct V { int i; };  
__gc struct R { V vr; };  
```  
  
 マネージ拡張であっても、値の型の 4 つの構文バリアント (フォーム 2 および 3 が同じ意味的)。  
  
```  
V v = { 0 };       // Form (1)  
V *pv = 0;         // Form (2) an implicit form of (3)  
V __gc *pvgc = 0;  // Form (3)  
__box V* pvbx = 0; // Form (4) must be local   
```  
  
## <a name="invoking-inherited-virtual-methods"></a>継承された仮想メソッドを呼び出す  
 `Form (1)`正規の値のオブジェクトでありことは合理的な程度を理解、継承された仮想メソッドを呼び出すように試行する場合を除く`ToString()`です。 例:  
  
```  
v.ToString(); // error!  
```  
  
 オーバーライドされていないために、このメソッドを呼び出すために`V`コンパイラは、基本クラスの関連する仮想テーブルへのアクセスを持つ必要があります。 型の値は、仮想テーブル (vptr) に関連付けられているポインターを持たない状態での記憶域であるため、このことが必要`v`ボックス化します。 設計では、マネージ拡張言語、暗黙的なボックス化はサポートされていませんが明示的に指定する必要、プログラマとして  
  
```  
__box( v )->ToString(); // Managed Extensions: note the arrow  
```  
  
 この設計背後のプライマリは教育: メカニズムを基になる彼女は自分値内でインスタンスが提供されていない 'コスト' を理解できるように、プログラマに表示する必要があります。 された`V`のインスタンスを格納する`ToString`、ボックス化する必要はありません。  
  
 新しい構文では、ボックス化自体の基になるコストされませんが、オブジェクトを明示的にボックス化する構文の複雑さが削除されます。  
  
```  
v.ToString(); // new syntax  
```  
  
 反面、コストの明示的なインスタンスを提供しないか、クラス デザイナーは誤解を招く可能性があります、`ToString`メソッド内で`V`です。 使い続ける理由に暗黙のボックス化の理由が 1 つのクラス デザイナーは通常があることを自由に変更なしのユーザーには、ユーザー数は無制限`V`煩わしいの明示的なボックスを排除します。  
  
 インスタンスをオーバーライドするかどうかを決定する条件`ToString`値の中で、クラスをその使用の場所と頻度する必要があります。 ごくまれには、呼び出される場合はもちろんメリットはほとんどの定義です。 同様に呼び出す場合は、アプリケーションのパフォーマンスの高い非領域で、追加することもない多少に追加されます、アプリケーションの全般的なパフォーマンス。 代わりに、追跡ハンドルからボックス化された値を保持でき、そのハンドル経由の呼び出しは必要ありません。 ボックス化  
  
## <a name="there-is-no-longer-a-value-class-default-constructor"></a>値クラスの既定のコンス トラクターはありません。  
 マネージ拡張と、新しい構文の値型を持つ別の相違点は、既定のコンス トラクターに対するサポートの廃止です。 これは、CLR が関連付けられている既定のコンス トラクターを呼び出さずに、値型のインスタンスを作成できます実行中の機会があるためです。 つまり、値型の中で、既定のコンス トラクターをサポートするために、マネージ拡張で試行でした実際面では保証されません。 保証がないを指定するがすっきりが非決定的のアプリケーションでありますのではなく、サポートを廃止する方がよい。  
  
 最初に見えるかもしれませんほどではありません。 これは、値型の各オブジェクトが自動的にゼロ クリアため (つまり、各型が既定値に初期化されて) います。 その結果、ローカル インスタンスのメンバーでは、定義されていないことはありません。 この意味で自明の既定のコンス トラクターを定義する機能の損失は本当にではありません、損失のと、実際には、CLR によって実行されるときより効率的です。  
  
 問題は、マネージ拡張のユーザーは、重要な既定のコンス トラクターを定義する場合です。 これには、新しい構文にマッピングがありません。 コンス トラクター内のコードは、ユーザーによって明示的に呼び出す必要のある名前付きの初期化メソッドに移行する必要があります。  
  
 新しい構文内で値型のオブジェクトの宣言は、それ以外の場合変更されません。 このマイナス面は値型できないことです水準ネイティブ型の折り返しの次の理由。  
  
-   値型のデストラクターはサポートされていません。 つまり、オブジェクトの有効期間の終了によってトリガーされたアクションのセットを自動化する方法はありません。  
  
-   ネイティブのクラスは、ネイティブ ヒープに割り当てられる、ポインターとして、マネージ型内でのみに含まれることができます。  
  
 値型ではなく、参照型を 2 つのヒープの割り当てを回避するに小さなネイティブ クラスをラップするよう: ネイティブ型を保持するために、ネイティブ ヒープとマネージ ラッパーを保持するために、CLR ヒープ。 値型の中でネイティブ クラスをラップ、マネージ ヒープを回避することができますが、ネイティブ ヒープ メモリの解放を自動化する方法が用意されていません。 参照型は、重要なネイティブ クラスをラップする実際的なマネージ型です。  
  
## <a name="interior-pointers"></a>内部ポインター  
 `Form (2)`および`Form (3)`上記のほとんどすべてをアドレスの世界または (つまり、何もマネージまたはネイティブ)、次にします。 そのため、たとえば、次のすべてはマネージ拡張で許可されます。  
  
```  
__value struct V { int i; };  
__gc struct R { V vr; };  
  
V v = { 0 };  // Form (1)  
V *pv = 0;  // Form (2)  
V __gc *pvgc = 0;  // Form (3)  
__box V* pvbx = 0;  // Form (4)  
  
R* r;  
  
pv = &v;            // address a value type on the stack  
pv = __nogc new V;  // address a value type on native heap  
pv = pvgc;          // we are not sure what this addresses  
pv = pvbx;          // address a boxed value type on managed heap  
pv = &r->vr;        // an interior pointer to value type within a  
                    //    reference type on the managed heap  
```  
  
 そのため、`V*`ローカル ブロック内の場所に対処できます (およびそのため、ぶら下がりことができます)、ネイティブ内のグローバル スコープで (たとえば、アドレスに指定するオブジェクトは既に削除されている場合)、CLR ヒープ内でヒープ (およびしたがってが追跡される場合はその必要があります再配置するガベージ コレクション中に)、および (内部ポインターでは、これが呼び出されると、透過的にも追跡されます)、CLR ヒープ上の参照オブジェクトの内部にします。  
  
 マネージ拡張でのネイティブの側面を分離する方法はありません、`V*`です。 つまり、扱われます、包括的に処理するオブジェクトや、マネージ ヒープ上のサブオブジェクトをアドレス指定可能性です。  
  
 新しい構文では、値型のポインターで考慮 2 つの種類: `V*`、非 CLR ヒープの格納場所、および内部のポインターに限定される`interior_ptr<V>`、できますが、マネージ ヒープ内のアドレスは必要ありません。  
  
```  
// may not address within managed heap   
V *pv = 0;   
  
// may or may not address within managed heap  
interior_ptr<V> pvgc = nullptr;   
```  
  
 `Form (2)`および`Form (3)`マネージ拡張のマップ`interior_ptr<V>`です。 `Form (4)`追跡ハンドルです。 マネージ ヒープ内にボックス化されたオブジェクトの全体の宛先を指定します。 新しい構文で変換されます、 `V^`、  
  
```  
V^ pvbx = nullptr; // __box V* pvbx = 0;    
```  
  
 新しい構文では内部ポインターにすべてのマップ、マネージ拡張で次の宣言。 (内で値型では、`System`名前空間です)。  
  
```  
Int32 *pi;   // => interior_ptr<Int32> pi;  
Boolean *pb; // => interior_ptr<Boolean> pb;  
E *pe;       // => interior_ptr<E> pe; // Enumeration  
```  
  
 組み込みの型は内の型をエイリアスとして使用され、操作を行いますが、マネージ型は、考慮されません、`System`名前空間。 したがって、次のマッピングは、マネージ拡張と、新しい構文の当てはまります。  
  
```  
int * pi;     // => int* pi;  
int __gc * pi2; // => interior_ptr<int> pi2;  
```  
  
 変換するときに、`V*`慎重な戦略が常有効にするのには、既存のプログラムで、`interior_ptr<V>`です。 これは、マネージ拡張で扱われた方法です。 新しい構文では、プログラマは、オプションの非マネージ ヒープのアドレスを指定することによって値型を制限する`V*`内部ポインターではなくです。 プログラムの変換では、そのすべての使用の推移的終了を行うし、割り当てられたアドレスが、マネージ ヒープ内に存在かどうかを必ず場合、残してとして`V*`問題ありません。  
  
## <a name="pinning-pointers"></a>ピンされたポインター  
 ガベージ コレクターは、通常圧縮フェーズ中に、ヒープ内の別の場所に、CLR ヒープ上に存在するオブジェクトを必要に応じて移動可能性があります。 この移動は、ハンドル、追跡参照、およびこれらのエンティティを透過的に更新する内部ポインターを追跡する問題ではありません。 この移動は、問題、ただし、ユーザーが、ランタイム環境の外部で CLR ヒープにオブジェクトのアドレスを越えた場合です。 この場合、揮発性オブジェクトの移動は実行時エラーが発生する可能性です。 必要がありますローカルでピン留めして、外部使用のエクステントのそれぞれの場所に、移動されないようオブジェクトを除外します。  
  
 マネージ拡張で、*固定ポインター*があるポインターの宣言を修飾することによって宣言されている、`__pin`キーワード。 マネージ拡張の仕様を少し変更した例を次に示します。  
  
```  
__gc struct H { int j; };  
  
int main()   
{  
   H * h = new H;  
   int __pin * k = & h -> j;  
  
   // ...  
};  
```  
  
 設計では、新しい言語、固定ポインターは内部ポインターに似た構文を使用して宣言されます。  
  
```  
ref struct H  
{  
public:  
   int j;  
};  
  
int main()  
{  
   H^ h = gcnew H;  
   pin_ptr<int> k = &h->j;  
  
   // ...  
}  
```  
  
 新しい構文で固定ポインターは、内部ポインターの特殊なケースです。 ピンされたポインターの元の制約のままになります。 たとえば、パラメーターとして使用することはできませんまたは; メソッドの型を返すこれは、ローカル オブジェクトでのみ宣言できます。 ただし、追加の制約の数の場合は、新しい構文で追加されましたが。  
  
 ピンされたポインターの既定値は`nullptr`ではなく、`0`です。 A`pin_ptr<>`初期化するか、または割り当てられていることはできません`0`です。 すべての割り当て`0`既存のコードでに変更する必要があります`nullptr`です。  
  
 マネージ拡張で固定ポインターで許可されている、マネージ拡張仕様から引用した次の例と同様に、オブジェクト全体をアドレスします。  
  
```  
__gc class G {  
public:  
   void incr(int* pi) { pi += 1; }  
};  
__gc struct H { int j; };  
void f( G * g ) {  
   H __pin * pH = new H;     
   g->incr(& pH -> j);     
};  
```  
  
 新しい構文ではオブジェクト全体をピン留めによって返される、`new`式はサポートされていません。 代わりに、内部メンバーのアドレスを固定する必要があります。 たとえば、オブジェクトに適用された  
  
```  
ref class G {  
public:  
   void incr(int* pi) { *pi += 1; }  
};  
ref struct H { int j; };  
void f( G^ g ) {  
   H ^ph = gcnew H;  
   Console::WriteLine(ph->j);  
   pin_ptr<int> pj = &ph->j;  
   g->incr(  pj );  
   Console::WriteLine(ph->j);  
}  
```  
  
## <a name="see-also"></a>参照  
 [値の型とその動作 (C + + CLI)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)   
 [クラスと構造体](../windows/classes-and-structs-cpp-component-extensions.md)   
 [interior_ptr (C + + CLI)](../windows/interior-ptr-cpp-cli.md)   
 [pin_ptr (C++/CLI)](../windows/pin-ptr-cpp-cli.md)