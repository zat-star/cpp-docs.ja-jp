---
title: "変更の概略 (C++/CLI) | Microsoft Docs"
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
ms.assetid: c0bbbd6b-c5c4-44cf-a6ca-c1010c377e9d
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 変更の概略 (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、C\+\+ マネージ拡張から [!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)] への移行に伴う、言語上の変更点をいくつか紹介します。  詳細については、各項目のリンクを参照してください。  
  
## キーワードの 2 つのアンダースコアの削除  
 すべてのキーワードの前に付いていた 2 つのアンダースコアは、1 つの例外を除き、削除されました。  つまり、`__value` は `value` 、`__interface` は `interface` のようになっています。  ユーザー コードでのキーワードと識別子の名前の衝突を回避するため、キーワードは基本的に状況依存として扱われます。  
  
 詳細については、「[言語キーワード \(C\+\+\/CLI\)\]](../Topic/Language%20Keywords%20\(C++-CLI\).md)」を参照してください。  
  
## クラス宣言  
 マネージ拡張の構文  
  
```  
__gc class Block {};                           // reference class  
__value class Vector {};                       // value class  
__interface I {};                        // interface class  
__gc __abstract class Shape {};                // abstract class  
__gc __sealed class Shape2D : public Shape {}; // derived class  
```  
  
 新しい構文  
  
```  
ref class Block {};                // reference class  
value class Vector {};             // value class  
interface class I {};        // interface class  
ref class Shape abstract {};       // abstract class  
ref class Shape2D sealed: Shape{}; // derived class  
```  
  
 詳細については、「[マネージ型 \(C\+\+\/CL\)](../dotnet/managed-types-cpp-cl.md)」を参照してください。  
  
## オブジェクト宣言  
 マネージ拡張の構文  
  
```  
public __gc class Form1 : public System::Windows::Forms::Form {  
private:  
   System::ComponentModel::Container __gc *components;  
   System::Windows::Forms::Button   __gc *button1;  
   System::Windows::Forms::DataGrid __gc *myDataGrid;     
   System::Data::DataSet  __gc *myDataSet;  
};  
```  
  
 新しい構文  
  
```  
public ref class Form1 : System::Windows::Forms::Form {  
   System::ComponentModel::Container^ components;  
   System::Windows::Forms::Button^ button1;  
   System::Windows::Forms::DataGrid^ myDataGrid;  
   System::Data::DataSet^ myDataSet;  
};  
```  
  
 詳細については、「[CLR 参照クラスのオブジェクトの宣言](../dotnet/declaration-of-a-clr-reference-class-object.md)」を参照してください。  
  
### マネージ ヒープの割り当て  
 マネージ拡張の構文  
  
```  
Button* button1 = new Button; // managed heap  
int *pi1 = new int;           // native heap  
Int32 *pi2 = new Int32;       // managed heap  
```  
  
 新しい構文  
  
```  
Button^ button1 = gcnew Button;        // managed heap  
int * pi1 = new int;                   // native heap  
Int32^ pi2 = gcnew Int32;              // managed heap  
```  
  
 詳細については、「[CLR 参照クラスのオブジェクトの宣言](../dotnet/declaration-of-a-clr-reference-class-object.md)」を参照してください。  
  
### オブジェクトなしへの追跡参照  
 マネージ拡張の構文  
  
```  
// OK: we set obj to refer to no object  
Object * obj = 0;  
  
// Error: no implicit boxing  
Object * obj2 = 1;  
```  
  
 新しい構文  
  
```  
// Incorrect Translation  
// causes the implicit boxing of both 0 and 1  
Object ^ obj = 0;  
Object ^ obj2 = 1;  
  
// Correct Translation  
// OK: we set obj to refer to no object  
Object ^ obj = nullptr;  
  
// OK: we initialize obj2 to an Int32^  
Object ^ obj2 = 1;  
```  
  
 詳細については、「[CLR 参照クラスのオブジェクトの宣言](../dotnet/declaration-of-a-clr-reference-class-object.md)」を参照してください。  
  
## 配列の宣言  
 CLR 配列はデザインし直されました。  stl `vector` テンプレートのように見えますが、基となる `System::Array` クラスに割り当てられているので、テンプレート実装ではありません。  
  
 詳細については、「[CLR 配列の宣言](../dotnet/declaration-of-a-clr-array.md)」を参照してください。  
  
### パラメーターとしての配列  
 マネージ拡張の配列構文  
  
```  
void PrintValues( Object* myArr __gc[]);   
void PrintValues( int myArr __gc[,,]);   
```  
  
 新しい配列構文  
  
```  
void PrintValues( array<Object^>^ myArr );  
void PrintValues( array<int,3>^ myArr );  
```  
  
### 戻り値の型としての配列  
 マネージ拡張の配列構文  
  
```  
Int32 f() [];   
int GetArray() __gc[];  
```  
  
 新しい配列構文  
  
```  
array<Int32>^ f();  
array<int>^ GetArray();  
```  
  
### ローカル CLR 配列の略式の初期化  
 マネージ拡張の配列構文  
  
```  
int GetArray() __gc[] {  
   int a1 __gc[] = { 1, 2, 3, 4, 5 };  
   Object* myObjArray __gc[] = { __box(26), __box(27), __box(28),  
                                 __box(29), __box(30) };  
  
   return a1;  
}  
```  
  
 新しい配列構文  
  
```  
array<int>^ GetArray() {  
   array<int>^ a1 = {1,2,3,4,5};  
   array<Object^>^ myObjArray = {26,27,28,29,30};  
  
   return a1;  
}  
```  
  
### 明示的な CLR 配列宣言  
 マネージ拡張の配列構文  
  
```  
Object* myArray[] = new Object*[2];  
String* myMat[,] = new String*[4,4];  
```  
  
 新しい配列構文  
  
```  
array<Object^>^ myArray = gcnew array<Object^>(2);  
array<String^,2>^ myMat = gcnew array<String^,2>(4,4);  
```  
  
 新規導入 : gcnew の後の明示的な配列の初期化  
  
```  
// explicit initialization list follow gcnew   
// is not supported in Managed Extensions  
array<Object^>^ myArray =   
   gcnew array<Object^>(4){ 1, 1, 2, 3 };  
```  
  
## スカラー プロパティ  
 マネージ拡張のプロパティ構文  
  
```  
public __gc __sealed class Vector {  
   double _x;  
  
public:  
   __property double get_x(){ return _x; }  
   __property void set_x( double newx ){ _x = newx; }  
};  
```  
  
 新しいプロパティ構文  
  
```  
public ref class Vector sealed {   
   double _x;  
  
public:  
   property double x   
   {  
      double get()             { return _x; }  
      void   set( double newx ){ _x = newx; }  
   } // Note: no semi-colon …  
};  
```  
  
 新規導入 : 単純なプロパティ  
  
```  
public ref class Vector sealed {   
public:  
   // equivalent shorthand property syntax  
   // backing store is not accessible  
   property double x;   
};  
```  
  
 詳細については、「[プロパティの宣言](../dotnet/property-declaration.md)」を参照してください。  
  
## インデックス付きプロパティ  
 マネージ拡張のインデックス付きプロパティ構文  
  
```  
public __gc class Matrix {  
   float mat[,];  
  
public:   
   __property void set_Item( int r, int c, float value) { mat[r,c] = value; }  
   __property int get_Item( int r, int c ) { return mat[r,c]; }  
};  
```  
  
 新しいインデックス付きプロパティ構文  
  
```  
public ref class Matrix {  
   array<float, 2>^ mat;  
  
public:  
   property float Item [int,int] {  
      float get( int r, int c ) { return mat[r,c]; }  
      void set( int r, int c, float value ) { mat[r,c] = value; }  
   }  
};  
```  
  
 新規導入 : クラス レベルのインデックス付きプロパティ  
  
```  
public ref class Matrix {  
   array<float, 2>^ mat;  
  
public:  
   // ok: class level indexer now  
   //     Matrix mat;  
   //     mat[ 0, 0 ] = 1;   
   //  
   // invokes the set accessor of the default indexer  
  
   property float default [int,int] {  
      float get( int r, int c ) { return mat[r,c]; }  
      void set( int r, int c, float value ) { mat[r,c] = value; }  
   }  
};  
```  
  
 詳細については、「[プロパティ インデックスの宣言](../dotnet/property-index-declaration.md)」を参照してください。  
  
## オーバーロードされた演算子  
 マネージ拡張の演算子オーバーロード構文  
  
```  
public __gc __sealed class Vector {  
public:  
   Vector( double x, double y, double z );  
  
   static bool    op_Equality( const Vector*, const Vector* );  
   static Vector* op_Division( const Vector*, double );  
};  
  
int main() {  
   Vector *pa = new Vector( 0.231, 2.4745, 0.023 );  
   Vector *pb = new Vector( 1.475, 4.8916, -1.23 );   
  
   Vector *pc = Vector::op_Division( pa, 4.8916 );  
  
   if ( Vector::op_Equality( pa, pc ))  
      ;  
}  
```  
  
 新しい演算子オーバーロード構文  
  
```  
public ref class Vector sealed {  
public:  
   Vector( double x, double y, double z );  
  
   static bool    operator ==( const Vector^, const Vector^ );  
   static Vector^ operator /( const Vector^, double );  
};  
  
int main() {  
   Vector^ pa = gcnew Vector( 0.231, 2.4745, 0.023 );  
   Vector^ pb = gcnew Vector( 1.475, 4.8916, -1.23 );  
  
   Vector^ pc = pa / 4.8916;  
   if ( pc == pa )  
      ;  
}  
```  
  
 詳細については、「[オーバーロードされた演算子](../dotnet/overloaded-operators.md)」を参照してください。  
  
## 変換演算子  
 マネージ拡張の変換演算子構文  
  
```  
__gc struct MyDouble {  
   static MyDouble* op_Implicit( int i );   
   static int op_Explicit( MyDouble* val );  
   static String* op_Explicit( MyDouble* val );   
};  
```  
  
 新しい変換演算子構文  
  
```  
ref struct MyDouble {  
public:  
   static operator MyDouble^ ( int i );  
   static explicit operator int ( MyDouble^ val );  
   static explicit operator String^ ( MyDouble^ val );  
};  
```  
  
 詳細については、「[変換演算子に対する変更点](../dotnet/changes-to-conversion-operators.md)」を参照してください。  
  
## インターフェイス メンバーの明示的オーバーライド  
 マネージ拡張の明示的オーバーライド構文  
  
```  
public __gc class R : public ICloneable {  
   // to be used through ICloneable  
   Object* ICloneable::Clone();  
  
   // to be used through an R  
   R* Clone();  
};  
```  
  
 新しい明示的オーバーライド構文  
  
```  
public ref class R : public ICloneable {  
   // to be used through ICloneable  
   virtual Object^ InterfaceClone() = ICloneable::Clone;  
  
   // to be used through an R   
   virtual R^ Clone();  
};  
```  
  
 詳細については、「[インターフェイス メンバーの明示的なオーバーライド](../dotnet/explicit-override-of-an-interface-member.md)」を参照してください。  
  
## プライベート仮想関数  
 マネージ拡張のプライベート仮想関数構文  
  
```  
__gc class Base {  
private:  
   // inaccessible to a derived class  
   virtual void g();   
};  
  
__gc class Derived : public Base {  
public:  
   // ok: g() overrides Base::g()  
   virtual void g();  
};  
```  
  
 新しいプライベート仮想関数構文  
  
```  
ref class Base {  
private:  
   // inaccessible to a derived class  
   virtual void g();   
};  
  
ref class Derived : public Base {  
public:  
   // error: cannot override: Base::g() is inaccessible  
   virtual void g() override;  
};  
```  
  
 詳細については、「[プライベート仮想関数](../Topic/Private%20Virtual%20Functions.md)」を参照してください。  
  
## CLR 列挙型  
 マネージ拡張の列挙型構文  
  
```  
__value enum e1 { fail, pass };  
public __value enum e2 : unsigned short  {   
   not_ok = 1024,   
   maybe, ok = 2048   
};    
```  
  
 新しい列挙型構文  
  
```  
enum class e1 { fail, pass };  
public enum class e2 : unsigned short {   
   not_ok = 1024,  
   maybe, ok = 2048   
};  
```  
  
 このように構文が多少変わったこと以外に、CLR 列挙型の動作もいくつか変更されています。  
  
-   CLR 列挙型の事前の宣言はサポートされなくなりました。  
  
-   組み込みの数値型と Object クラス階層構造の間でのオーバーロードの解決は、マネージ拡張と [!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)] では逆転しています。  その副次効果として、CLR 列挙型が暗黙のうちに数値型に変換されることはなくなりました。  
  
-   マネージ拡張の場合とは異なり、新しい構文では CLR 列挙型は独自のスコープを維持します。  これまで、列挙子は列挙型の保持しているスコープ内で参照可能でしたが、今度は列挙子は列挙型のスコープ内にカプセル化されています。  
  
 詳細については、「[CLR 列挙型](../dotnet/clr-enum-type.md)」を参照してください。  
  
## \_\_box キーワードの削除  
 マネージ拡張のボックス化構文  
  
```  
Object *o = __box( 1024 ); // explicit boxing  
```  
  
 新しいボックス化構文  
  
```  
Object ^o = 1024; // implicit boxing  
```  
  
 詳細については、「[追跡ハンドルからボックス化変換された値へ](../dotnet/a-tracking-handle-to-a-boxed-value.md)」を参照してください。  
  
## 固定ポインター  
 マネージ拡張の固定ポインター構文  
  
```  
__gc struct H { int j; };  
  
int main() {  
   H * h = new H;  
   int __pin * k = & h -> j;  
};  
```  
  
 新しい固定ポインター構文  
  
```  
ref struct H { int j; };  
  
int main() {  
   H^ h = gcnew H;  
   pin_ptr<int> k = &h->j;  
}  
```  
  
 詳細については、「[値型セマンティクス](../Topic/Value%20Type%20Semantics.md)」を参照してください。  
  
## \_\_typeof キーワードの typeid への変更  
 マネージ拡張の typeof 構文  
  
```  
Array* myIntArray =   
   Array::CreateInstance( __typeof(Int32), 5 );  
```  
  
 新しい typeid 構文  
  
```  
Array^ myIntArray =   
   Array::CreateInstance( Int32::typeid, 5 );  
```  
  
 詳細については、「[typeof から T::typeid への移行](../dotnet/typeof-goes-to-t-typeid.md)」を参照してください。  
  
## 参照  
 [C\+\+\/CLI 移行ガイド](../dotnet/cpp-cli-migration-primer.md)   
 [\(NOTINBUILD\)Managed Extensions for C\+\+ Syntax Upgrade Checklist](http://msdn.microsoft.com/ja-jp/edbded88-7ef3-4757-bd9d-b8f48ac2aada)   
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)