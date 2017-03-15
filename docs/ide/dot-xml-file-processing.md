---
title: ".Xml ファイルの処理 | Microsoft Docs"
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
  - "XML ドキュメント, XML ファイルの処理"
ms.assetid: e70fdeae-80ac-4872-ab24-771c5635cfbf
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# .Xml ファイルの処理
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コンパイラは、ドキュメントを生成するためにタグ付けされたコードの構成体ごとに、ID 文字列を生成します。  詳細については、[推奨されるタグ ドキュメント コメント](../Topic/Recommended%20Tags%20for%20Documentation%20Comments%20\(Visual%20C++\).md)を参照してください。  ID 文字列によって、構成体は一意に識別されます。  .xml ファイルを処理するプログラムはドキュメントを適用するリフレクション項目または .NET Framework の対応するメタデータを識別するために、ID 文字列を使用できます。  
  
 .xml ファイルは、コード、その階層ビューで要素ごとに生成された ID の一覧ではありません。  
  
 コンパイラは、次の規則に基づいて ID 文字列を生成します。  
  
-   生成される文字列に空白は含まれません。  
  
-   ID 文字列の最初の部分には、単一の文字とコロンで、識別されるメンバーの種類を示します。  使用されるメンバー型は次のとおりです。  
  
    |文字|説明|  
    |--------|--------|  
    |N|namespace<br /><br /> 名前空間と名前空間への cref 参照ができるドキュメント コメントを追加できません。|  
    |T|型 : class、interface、struct、enum、delegate|  
    |D|typedef|  
    |F|field|  
    |P|プロパティ \(インデクサーまたはその他のインデックス付きプロパティを含む\)|  
    |M|メソッド \(コンストラクター、演算子などの特殊なメソッドを含む\)|  
    |E|イベント|  
    |\!|エラー文字列<br /><br /> エラーに続く文字列で、エラーの内容を示します。  Visual C\+\+ コンパイラは、解決できないリンクのエラー情報を生成します。|  
  
-   文字列の 2 番目の部分は、項目の完全限定名です。名前は、名前空間のルートから始まります。  項目の名前、項目が含まれている型または型、および名前空間は、ピリオドで区切られます。  名前自体にピリオドがある場合、名前のピリオドはハッシュ記号 \('\#'\) に置き換えられます。  項目の名前にはハッシュ記号がないことが前提です。  たとえば、`String` コンストラクターの完全修飾名は「System.String.\#ctor」です。  
  
-   プロパティおよびメソッドについては、メソッドに引数がある場合は、引数のリストをかっこで囲み、メソッドに続けて指定します。  引数がない場合は、かっこはありません。  引数の区切り文字には、コンマを使用します。  各引数のエンコードは、次に示す .NET Framework のシグネチャでの引数のエンコーディング方法にそのまま従います。  
  
    -   基本型。  通常の型 \(ELEMENT\_TYPE\_CLASS または ELEMENT\_TYPE\_VALUETYPE\) は、型の完全限定名で表されます。  
  
    -   ELEMENT\_TYPE\_I4、ELEMENT\_TYPE\_OBJECT、ELEMENT\_TYPE\_STRING、ELEMENT\_TYPE\_TYPEDBYREF、  ELEMENT\_TYPE\_VOID などは、対応する完全な型、たとえば、**System.Int32** や **System.TypedReference**の完全修飾名で表されます。  
  
    -   ELEMENT\_TYPE\_PTR は、修飾される型に続けて '\*' と表されます。  
  
    -   ELEMENT\_TYPE\_BYREF は、修飾される型に続けて '@' と表されます。  
  
    -   ELEMENT\_TYPE\_PINNED は、修飾される型に続けて '^' と表されます。  Visual C\+\+ コンパイラでは生成されません。  
  
    -   ELEMENT\_TYPE\_CMOD\_REQ は、修飾される型に続けて "&#124;" と修飾子クラスの完全限定名で表されます。  Visual C\+\+ コンパイラでは生成されません。  
  
    -   ELEMENT\_TYPE\_CMOD\_OPT は、修飾される型に続けて "\!" と修飾子クラスの完全修飾名で表されます。  
  
    -   ELEMENT\_TYPE\_SZARRAY は、配列の要素型に続けて "\[\]" と表されます。  
  
    -   ELEMENT\_TYPE\_GENERICARRAY は、配列の要素型に続けて "\[?\]" と表されます。  Visual C\+\+ コンパイラでは生成されません。  
  
    -   ELEMENT\_TYPE\_ARRAY は、\[*lowerbound*:`size`,*lowerbound*:`size`\] の形式で表されます。ここで、コンマの個数はランク \-1 個であり、各次元の下限とサイズは明らかな場合は、10 進数で表されます。  下限またはサイズを、指定しない場合は省略します。  特定の次元で下限およびサイズが省略されている場合は、その次元の ':' も省略されます。  たとえば、ある 2 次元配列の下限が 1 で、サイズの指定がない場合は、\[1:,1:\] と表されます。  
  
    -   ELEMENT\_TYPE\_FNPTR は、"\=FUNC:`type`\(*signature*\)" と表されます。ここで、`type` は戻り値の型であり、*signature* はメソッドの引数です。  引数がない場合は、かっこが省略されます。  Visual C\+\+ コンパイラでは生成されません。  
  
     次に示すシグネチャ コンポーネントは、オーバーロードされるメソッドの区別には使用されることがないため、表されません。  
  
    -   呼び出し規約  
  
    -   戻り値の型  
  
    -   ELEMENT\_TYPE\_SENTINEL  
  
-   変換演算子の場合のみ、としてメソッドの戻り値は" ~ "としてエンコードされ、前にエンコードされた戻り値の型が表されます。  
  
-   ジェネリック型では、型の名前の後に、バック チック \(\`\)、ジェネリック型パラメーターの数を示す数値が順に続きます。  次に例を示します。  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
     `public class MyClass\<T, U>`で定義される型。  
  
     パラメーターとしてジェネリック型を受け取るメソッドでは、ジェネリック型パラメーターは、バック チック付きの数値 \(\`0、\`1 など\) として指定されます。  各数値は、型のジェネリック パラメーターに対する、インデックス番号が 0 から始まる配列表記を表しています。  
  
## 使用例  
 次の例は、クラス用およびそのメンバーの ID 文字列を生成する方法を示します。  
  
```  
// xml_id_strings.cpp  
// compile with: /clr /doc /LD  
///   
namespace N {    
// "N:N"  
  
   /// <see cref="System" />  
   //  <see cref="N:System"/>  
   ref class X {      
   // "T:N.X"  
  
   protected:  
      ///   
      !X(){}     
      // "M:N.X.Finalize", destructor's representation in metadata  
  
   public:  
      ///   
      X() {}     
      // "M:N.X.#ctor"  
  
      ///   
      static X() {}     
      // "M:N.X.#cctor"  
  
      ///   
      X(int i) {}     
      // "M:N.X.#ctor(System.Int32)"  
  
      ///   
      ~X() {}     
      // "M:N.X.Dispose", Dispose function representation in metadata  
  
      ///   
      System::String^ q;     
      // "F:N.X.q"  
  
      ///   
      double PI;     
      // "F:N.X.PI"  
  
      ///   
      int f() { return 1; }     
      // "M:N.X.f"  
  
      ///   
      int bb(System::String ^ s, int % y, void * z) { return 1; }  
      // "M:N.X.bb(System.String,System.Int32@,System.Void*)"  
  
      ///   
      int gg(array<short> ^ array1, array< int, 2 >^ IntArray) { return 0; }   
      // "M:N.X.gg(System.Int16[], System.Int32[0:,0:])"  
  
      ///   
      static X^ operator+(X^ x, X^ xx) { return x; }  
     // "M:N.X.op_Addition(N.X,N.X)"  
  
      ///   
      property int prop;     
      // "M:N.X.prop"  
  
      ///   
      property int prop2 {     
      // "P:N.X.prop2"  
  
         ///   
         int get() { return 0; }  
         // M:N.X.get_prop2  
  
         ///   
         void set(int i) {}  
         // M:N.X.set_prop2(System.Int32)  
      }  
  
      ///   
      delegate void D(int i);   
      // "T:N.X.D"  
  
      ///   
      event D ^ d;   
      // "E:N.X.d"  
  
      ///   
      ref class Nested {};   
      // "T:N.X.Nested"  
  
      ///   
      static explicit operator System::Int32 (X x) { return 1; }   
      // "M:N.X.op_Explicit(N.X!System.Runtime.CompilerServices.IsByValue)~System.Int32"  
   };  
}  
```  
  
## 参照  
 [XML に関するドキュメント](../ide/xml-documentation-visual-cpp.md)