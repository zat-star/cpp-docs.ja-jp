---
title: "仮想関数のシール | Microsoft Docs"
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
  - "__sealed キーワード"
  - "派生クラス, 仮想関数"
  - "sealed キーワード [C++]"
  - "仮想関数, シール"
ms.assetid: 0e9fae03-6425-4512-9a24-8ccb6dc8a0d4
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 仮想関数のシール
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

仮想関数をシールするための構文は、C\+\+ のマネージ拡張から [!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)] に変更されています。  
  
 マネージ拡張の `__sealed` キーワードは、参照型を変更して、その以降の派生を無効にするか \(「[マネージ クラス型の宣言](../dotnet/declaration-of-a-managed-class-type.md)」を参照\)、または仮想関数を変更して、派生クラス内のメソッドの以降のオーバーライドを無効にするために使用されます。  たとえば、次のようになります。  
  
```  
__gc class base { public: virtual void f(); };  
__gc class derived : public base {  
public:  
   __sealed void f();  
};  
```  
  
 この例では、関数プロトタイプの正確な一致に基づいて、`derived::f()` が `base::f()` インスタンスをオーバーライドします。  `__sealed` キーワードは、派生クラスから継承された後続のクラスが `derived::f()` のオーバーライドを提供できないことを示します。  
  
 新しい構文では、`sealed` は、以前のように実際の関数プロトタイプの前の任意の場所に置くことはできず、署名の後に配置します。  さらに、`sealed` を使用するには、`virtual` キーワードも明示的に使用する必要があります。  上の `derived` を正しく変換すると、次のようになります。  
  
```  
ref class derived: public base {  
public:  
   virtual void f() override sealed;  
};  
```  
  
 このインスタンスに `virtual` キーワードがないと、エラーになります。  新しい構文では、コンテキスト キーワード `abstract` を `=0` の代わりに使用して、純粋仮想関数を示すことができます。  これはマネージ拡張ではサポートされていませんでした。  たとえば、次のようになります。  
  
```  
__gc class base { public: virtual void f()=0; };  
```  
  
 これは次のように書き換えることができます。  
  
```  
ref class base { public: virtual void f() abstract; };  
```  
  
## 参照  
 [クラスまたはインターフェイス内でのメンバー宣言 \(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [sealed](../windows/sealed-cpp-component-extensions.md)