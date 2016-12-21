---
title: "CLR 参照クラスのオブジェクトの宣言 | Microsoft Docs"
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
  - "参照型, CLR"
  - "型 [C++], 参照型"
ms.assetid: 6d64f746-3715-4948-ada3-88859f4150e4
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CLR 参照クラスのオブジェクトの宣言
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

参照クラス型のオブジェクトを宣言およびインスタンス化する構文は、[!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)] では C\+\+ マネージ拡張から変更されています。  
  
 マネージ拡張では、参照クラス型のオブジェクトは ISO\-C\+\+ ポインター構文を使用して宣言し、オプションで `__gc` キーワードをアスタリスク \(`*`\) の左に指定します。  以下は、マネージ拡張構文によるさまざまな参照クラス型オブジェクトの宣言の例です。  
  
```  
public __gc class Form1 : public System::Windows::Forms::Form {  
private:  
   System::ComponentModel::Container __gc *components;  
   Button __gc *button1;  
   DataGrid __gc *myDataGrid;     
   DataSet __gc *myDataSet;  
  
   void PrintValues( Array* myArr ) {  
      System::Collections::IEnumerator* myEnumerator =   
         myArr->GetEnumerator();  
  
      Array *localArray;  
      myArr->Copy(myArr, localArray, myArr->Length);  
   }  
};  
```  
  
 新しい構文では、新しい宣言子トークン \(`^`\) を使用して参照クラス型オブジェクトを宣言します。これは、正式には、*トラッキング ハンドル*と呼びますが、単純に*キャレット*と呼ばれることもあります。参照型は CLR ヒープ内にあるため、ガベージ コレクションによってヒープが最適化されるときに透過的に移動される可能性があります。トラッキングという修飾語は、このことを強調しています。  トラッキング ハンドルは実行時に透過的に更新されます。  類似の概念として、*トラッキング参照* \(`%`\) と*内部ポインター* \(`interior_ptr<>`\) の 2 つがあります。これらについては、「[値型セマンティクス](../Topic/Value%20Type%20Semantics.md)」で説明します。  
  
 ISO\-C\+\+ のポインター構文の再利用から宣言構文に移行した主な理由は、次のとおりです。  
  
-   ポインター構文を使用すると、オーバーロードされた演算子を参照オブジェクトに直接適用できず、  内部名を通じて演算子を呼び出す必要があります。たとえば、`rV1->op_Addition(rV2)` とする必要があり、`rV1+rV2` よりも直感性に欠けます。  
  
-   ガベージ コレクションが行われるヒープに格納されているオブジェクトに対して許可されていないポインター操作がいくつかあります \(キャストやポインター演算など\)。  トラッキング ハンドルの概念は CLR 参照型の本質をより的確に捉えています。  
  
 トラッキング ハンドルでは `__gc` 修飾子を使用する必要はなく、サポートもされていません。  オブジェクトそのものの使用方法は変わりません。これまでどおり、ポインター メンバー選択演算子 \(`->`\) によってメンバーにアクセスできます。  たとえば、上のマネージ拡張のコード例を新しい構文に変換すると、次のようになります。  
  
```  
public ref class Form1: public System::Windows::Forms::Form {  
private:  
   System::ComponentModel::Container^ components;  
   Button^ button1;  
   DataGrid^ myDataGrid;  
   DataSet^ myDataSet;  
  
   void PrintValues( Array^ myArr ) {  
      System::Collections::IEnumerator^ myEnumerator =  
         myArr->GetEnumerator();  
  
      Array ^localArray;  
      myArr->Copy(myArr, localArray, myArr->Length);   }  
};  
```  
  
## CLR ヒープへのオブジェクトの動的割り当て  
 マネージ拡張では、オブジェクトをネイティブ ヒープとマネージ ヒープに割り当てるために 2 つの `new` 式が存在することが、ほとんど意識されませんでした。  ネイティブ ヒープまたはマネージ ヒープのどちらからメモリを確保するかは、ほとんどの場合、コンパイラがコンテキストから正しく判断できます。  次に例を示します。  
  
```  
Button *button1 = new Button; // OK: managed heap  
int *pi1 = new int;           // OK: native heap  
Int32 *pi2 = new Int32;       // OK: managed heap  
```  
  
 コンテキストに基づくヒープ割り当てを望まない場合は、`__gc` キーワードまたは `__nogc` キーワードを使用してコンパイラを制御することもできます。  新しい構文では、`gcnew` キーワードの導入によって、異なる 2 つの new 式の存在が明確になっています。  たとえば、上の 3 つの宣言は、新しい構文では次のようになります。  
  
```  
Button^ button1 = gcnew Button;        // OK: managed heap  
int * pi1 = new int;                   // OK: native heap  
Int32^ pi2 = gcnew Int32; // OK: managed heap  
```  
  
 以下は、前のセクションで宣言した `Form1` のメンバーをマネージ拡張で初期化する例です。  
  
```  
void InitializeComponent() {  
   components = new System::ComponentModel::Container();  
   button1 = new System::Windows::Forms::Button();  
   myDataGrid = new DataGrid();  
  
   button1->Click +=   
      new System::EventHandler(this, &Form1::button1_Click);  
}  
```  
  
 この初期化コードを新しい構文に書き直すと、次のようになります。  `gcnew` 式のターゲットになる場合は参照型にハットが必要ないことに注意してください。  
  
```  
void InitializeComponent() {  
   components = gcnew System::ComponentModel::Container;  
   button1 = gcnew System::Windows::Forms::Button;  
   myDataGrid = gcnew DataGrid;  
  
   button1->Click +=   
      gcnew System::EventHandler( this, &Form1::button1_Click );  
}  
```  
  
## オブジェクトなしへの追跡参照  
 新しい構文では、`0` は null アドレスを表すのではなく、整数 \(`1`、`10`、`100` などと同じ\) として扱われるようになりました。  トラッキング参照の null 値は、新しい特殊なトークンによって表されます。  たとえば、オブジェクトなしをアドレス指定するように参照型を初期化する場合、マネージ拡張では次のようになります。  
  
```  
// OK: we set obj to refer to no object  
Object * obj = 0;  
  
// Error: no implicit boxing  
Object * obj2 = 1;  
```  
  
 新しい構文では、`Object` の初期化や値型の割り当てを行うと、その値型の暗黙のボックス化が行われます。  したがって、新しい構文では、`obj` と `obj2` は両方とも、アドレス指定されたボックス化された Int32 オブジェクト \(それぞれ値 0 および 1 を保持している\) に初期化されます。  たとえば、次のようになります。  
  
```  
// causes the implicit boxing of both 0 and 1  
Object ^ obj = 0;  
Object ^ obj2 = 1;  
```  
  
 その結果、トラッキング ハンドルの null への明示的な初期化、割り当て、および比較を行うには、新しいキーワード `nullptr` を使用します。前の例を新しい構文で正しく書き直すと次のようになります。  
  
```  
// OK: we set obj to refer to no object  
Object ^ obj = nullptr;  
  
// OK: we initialize obj2 to a Int32^  
Object ^ obj2 = 1;  
```  
  
 既存のコードを新しい構文に移植する際には、このことによって作業が少し複雑になります。  たとえば、次のような値クラスの宣言を考えます。  
  
```  
__value struct Holder {  
   Holder( Continuation* c, Sexpr* v ) {  
      cont = c;  
      value = v;  
      args = 0;  
      env = 0;  
   }  
  
private:  
   Continuation* cont;  
   Sexpr * value;  
   Environment* env;  
   Sexpr * args __gc [];  
};  
```  
  
 ここで、`args` と `env` はいずれも CLR 参照型です。  コンストラクターでこれら 2 つのメンバーが `0` に初期化されていますが、これらは、このままでは新しい構文に移行できません。  `nullptr` に変更する必要があります。  
  
```  
value struct Holder {  
   Holder( Continuation^ c, Sexpr^ v )  
   {  
      cont = c;  
      value = v;  
      args = nullptr;  
      env = nullptr;  
   }  
  
private:  
   Continuation^ cont;  
   Sexpr^ value;  
   Environment^ env;  
   array<Sexpr^>^ args;  
};  
```  
  
 これらのメンバーを `0` と比較するテストも、同様に `nullptr` との比較に変更する必要があります。  以下はマネージ拡張の構文です。  
  
```  
Sexpr * Loop (Sexpr* input) {  
   value = 0;  
   Holder holder = Interpret(this, input, env);  
  
   while (holder.cont != 0) {  
      if (holder.env != 0) {  
         holder=Interpret(holder.cont,holder.value,holder.env);  
      }  
      else if (holder.args != 0) {  
         holder =   
         holder.value->closure()->  
         apply(holder.cont,holder.args);  
      }  
   }  
  
   return value;  
}  
```  
  
 以下は、`0` の部分をすべて `nullptr` で置き換えたものです。  この場合、変換ツールを使用すると、すべてとは言わないまでも、`NULL` マクロの使用を含む多くの変換を自動化できます。  
  
```  
Sexpr ^ Loop (Sexpr^ input) {  
   value = nullptr;  
   Holder holder = Interpret(this, input, env);  
  
   while ( holder.cont != nullptr ) {  
      if ( holder.env != nullptr ) {  
         holder=Interpret(holder.cont,holder.value,holder.env);  
      }  
      else if (holder.args != nullptr ) {  
         holder =   
         holder.value->closure()->  
         apply(holder.cont,holder.args);  
      }  
   }  
  
   return value;  
}  
```  
  
 `nullptr` は、任意のポインター型やトラッキング ハンドル型に変換されますが、整数型への上位変換は行われません。  たとえば、次の初期化の中で `nullptr` が初期値として有効であるのは最初の 2 つだけです。  
  
```  
// OK: we set obj and pstr to refer to no object  
Object^ obj = nullptr;  
char*   pstr = nullptr; // 0 would also work here  
  
// Error: no conversion of nullptr to 0 …  
int ival = nullptr;  
```  
  
 同様の例をもう 1 つ紹介します。次のような一連のオーバーロードされたメソッドがあるとします。  
  
```  
void f( Object^ ); // (1)  
void f( char* );   // (2)  
void f( int );     // (3)  
```  
  
 上のメソッドを、次のように `nullptr` リテラルで呼び出します。  
  
```  
// Error: ambiguous: matches (1) and (2)  
f(  nullptr );  
```  
  
 この呼び出しがあいまいになるのは、`nullptr` がトラッキング ハンドルとポインターの両方に一致し、両者の優先順位も決まっていないからです \(このあいまいさを解決するには、明示的なキャストが必要です\)。  
  
 `0` で呼び出した場合は、\(3\) に厳密に一致します。  
  
```  
// OK: matches (3)  
f( 0 );  
```  
  
 これは、`0` が整数型であるためです。  `f(int)` が存在しない場合でも、この呼び出しはあいまいにはならず、標準変換によって `f(char*)` に一致します。  一致の規則では、厳密な一致が標準変換より優先されます。  厳密な一致がなかった場合は、標準変換が値型の暗黙のボックス化より優先されます。  あいまいにならないのはこの規則があるためです。  
  
## 参照  
 [マネージ型 \(C\+\+\/CL\)](../dotnet/managed-types-cpp-cl.md)   
 [Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)   
 [オブジェクト演算子 \(^\) へのハンドル](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)   
 [nullptr](../windows/nullptr-cpp-component-extensions.md)