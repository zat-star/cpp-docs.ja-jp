---
title: "Windows Runtime and Managed Templates (C++ Component Extensions) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "templates, with CLR types"
ms.assetid: cf59d16b-5514-448b-9a95-e0b4fcb616a6
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Windows Runtime and Managed Templates (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

テンプレートは Windows ランタイムまたは共通言語ランタイムの型のプロトタイプを定義できるようにし、異なるテンプレート型のパラメーターを使用して、その型のバリエーションがインスタンス化します。  
  
## すべてのランタイム  
 値または参照型からテンプレートを作成できます。値または参照型の作成についての詳細については、「[Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)」を参照してください。  
  
 標準 C\+\+ クラス テンプレートの詳細については、「[クラス テンプレート](../Topic/Class%20Templates.md)」を参照してください。  
  
## Windows ランタイム  
 \(この言語機能には Windows ランタイムのみに適用される特記事項がありません。\)  
  
### 要件  
 コンパイラ オプション: **\/ZW**  
  
## 共通言語ランタイム  
 次のコード例で指定されたマネージ型からクラス テンプレートの作成にはいくつかの制限があります。  
  
### 要件  
 コンパイラ オプション: **\/clr**  
  
### 例  
 **例**  
  
 マネージ型のテンプレート パラメーターのジェネリック型をインスタンス化することはできますが、ジェネリック型のテンプレート パラメーターのマネージ テンプレートをインスタンス化することはできません。これにより、ジェネリック型を実行時に解決するためです。詳細については、「[Generics and Templates \(Visual C\+\+\)](../windows/generics-and-templates-visual-cpp.md)」を参照してください。  
  
```cpp  
// managed_templates.cpp  
// compile with: /clr /c  
  
generic<class T>   
ref class R;   
  
template<class T>   
ref class Z {  
   // Instantiate a generic with a template parameter.  
   R<T>^ r;    // OK  
};  
  
generic<class T>   
ref class R {  
   // Cannot instantiate a template with a generic parameter.  
   Z<T>^ z;   // C3231  
};  
```  
  
 **例**  
  
 ジェネリック型またはジェネリック関数はマネージ テンプレートに入れ子にすることはできません。  
  
```cpp  
// managed_templates_2.cpp  
// compile with: /clr /c  
  
template<class T> public ref class R {  
   generic<class T> ref class W {};   // C2959  
};  
```  
  
 **例**  
  
 C\+\+\/CLI 言語構文を参照アセンブリで定義されたテンプレートにアクセスするリフレクションを使用できます。テンプレートがインスタンス化されなければ、メタデータに出力されません。テンプレートがインスタンス化されれば、参照先メンバー関数だけがメタデータに表示されます。  
  
```cpp  
// managed_templates_3.cpp  
// compile with: /clr  
  
// Will not appear in metadata.  
template<class T> public ref class A {};  
  
// Will appear in metadata as a specialized type.  
template<class T> public ref class R {  
public:  
   // Test is referenced, will appear in metadata  
   void Test() {}  
  
   // Test2 is not referenced, will not appear in metadata  
   void Test2() {}  
};  
  
// Will appear in metadata.  
generic<class T> public ref class G { };  
  
public ref class S { };  
  
int main() {  
   R<int>^ r = gcnew R<int>;  
   r->Test();  
}  
```  
  
 **例**  
  
 クラス テンプレートの部分的な特化または明示的な特殊化クラスのマネージ修飾子を変更できます。  
  
```cpp  
// managed_templates_4.cpp  
// compile with: /clr /c  
  
// class template  
// ref class  
template <class T>  
ref class A {};  
  
// partial template specialization  
// value type  
template <class T>  
value class A <T *> {};  
  
// partial template specialization  
// interface  
template <class T>   
interface class A<T%> {};  
  
// explicit template specialization  
// native class  
template <>  
class A <int> {};  
  
```  
  
## 参照  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)