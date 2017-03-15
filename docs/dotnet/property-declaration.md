---
title: "プロパティの宣言 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__property キーワード"
  - "宣言 (プロパティの), C++"
  - "property キーワード [C++]"
ms.assetid: de169378-a8b8-49f4-a586-76bffc9b5c9f
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# プロパティの宣言
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

マネージ クラスでのプロパティの宣言方法は、[!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)] では C\+\+ マネージ拡張から変更されています。  
  
 マネージ拡張では、`set` または `get` の各プロパティ アクセサーは独立したメソッドとして指定されます。  各メソッドの宣言には、`__property` キーワードがプレフィックスとして付けられます。  メソッド名は `set_` または `get_` から始まり、その後に \(ユーザーが認識可能な\) プロパティの実際の名前が続きます。  したがって、`x` 座標を持つ `Vector` の `get` プロパティの名前は `get_x` となり、ユーザーは `x` と指定してこのプロパティを呼び出します。  こうしたメソッドの名前付け規則と独立した仕様は、実行時におけるプロパティの基本実装を反映しています。  たとえば、次のコードでは、複数の座標プロパティを持つ `Vector` クラスを定義しています。  
  
```  
public __gc __sealed class Vector {  
public:  
   __property double get_x(){ return _x; }  
   __property double get_y(){ return _y; }  
   __property double get_z(){ return _z; }  
  
   __property void set_x( double newx ){ _x = newx; }  
   __property void set_y( double newy ){ _y = newy; }  
   __property void set_z( double newz ){ _z = newz; }  
};  
```  
  
 このコードでは、プロパティ関連の機能が散開しており、関連する sets や gets をユーザーが構文的にまとめる必要があります。  何より、冗長でわかりにくいという欠点があります。  新しい構文では、より C\# に近い構文が採用されており、`property` キーワードの後にプロパティの型と純粋なプロパティ名が続きます。  `set` および `get` access メソッドは、プロパティ名の後のブロック内に置かれます。  ただし、C\# とは異なり、access メソッドのシグネチャを指定する必要があります。  たとえば、次の例は上記のコードを新しい構文に変換したものです。  
  
```  
public ref class Vector sealed {   
public:  
   property double x {  
      double get() {  
         return _x;  
      }  
  
      void set( double newx ) {  
         _x = newx;  
      }  
   } // Note: no semi-colon  
};  
```  
  
 `public` `get`、`private`、または `protected` `set` など、プロパティのアクセス メソッドがアクセス レベルの違いを反映している場合は、アクセス ラベルを明示的に指定できます。  既定では、プロパティのアクセス レベルはクラス ブロックのアクセス レベルを反映します。  たとえば、上記の `Vector` の定義では、`get` メソッドおよび `set` メソッドの両者ともアクセス レベルは `public` になります。  `set` メソッドを `protected` または `private` に設定するには、上記の定義を次のように変更します。  
  
```  
public ref class Vector sealed {   
public:  
   property double x {  
      double get() {  
         return _x;  
      }  
  
   private:  
      void set( double newx ) {  
         _x = newx;  
      }  
  
   } // note: extent of private culminates here …  
  
// note: dot is a public method of Vector  
double dot( const Vector^ wv );  
  
// etc.  
};  
```  
  
 プロパティ内のアクセス キーワードのスコープは、プロパティ ブロックの右中かっこ \(}\) まで、または別のアクセス キーワードが指定されている箇所までです。  有効範囲がプロパティの定義ブロックを超えることはありません。定義ブロック以外の箇所については、クラス ブロックのアクセス レベルが適用されます。  たとえば、上記の定義において、`Vector::dot()` はパブリック メソッドとなります。  
  
 3 つの `Vector` 座標について set\/get プロパティを記述する場合、次の 3 つの手順が必要となります。  
  
1.  適切な型のプライベート状態のメンバーを宣言します。  
  
2.  ユーザーがプロパティ値を取得しようとしている場合はその値を返します。  
  
3.  新しい値を代入します。  
  
 新しい構文ではプロパティの省略構文を利用できます。上記の処理は自動的に実装されます。  
  
```  
public ref class Vector sealed {   
public:  
   // equivalent shorthand property syntax  
   property double x;   
   property double y;  
   property double z;  
};  
```  
  
 プロパティの省略構文には興味深い副作用があります。つまり、バックステージの静的メンバーがコンパイラによって生成される一方で、クラス内からそのメンバーにアクセスするには set\/get アクセサーを使用する以外に手段がないということです。  
  
## 参照  
 [クラスまたはインターフェイス内でのメンバー宣言 \(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [property](../windows/property-cpp-component-extensions.md)