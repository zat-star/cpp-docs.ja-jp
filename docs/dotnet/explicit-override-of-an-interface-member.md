---
title: "インターフェイス メンバーの明示的なオーバーライド | Microsoft Docs"
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
  - "明示的なオーバーライド (仮想関数の)"
  - "関数 [C++], オーバーライド"
  - "インターフェイス メンバー, 明示的なオーバーライド"
  - "オーバーライド関数"
  - "仮想関数, 明示的なオーバーライド"
ms.assetid: 46f1f536-bf43-4311-9a17-ff2282e528a9
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# インターフェイス メンバーの明示的なオーバーライド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

クラス内のインターフェイス メンバーの明示的なオーバーライドを宣言する構文が C\+\+ マネージ拡張から [!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)] に変更されました。  
  
 インターフェイスを実装するインターフェイス メンバーのインスタンスをクラス内に 2 つ作成すると便利です。1 つのインスタンスは、クラス オブジェクトがインターフェイス ハンドル経由で操作される場合に使用されます。もう 1 つのインスタンスは、クラス オブジェクトがクラス インターフェイス経由で使用される場合に使用されます。  たとえば、次のようになります。  
  
```  
public __gc class R : public ICloneable {  
   // to be used through ICloneable  
   Object* ICloneable::Clone();  
  
   // to be used through an R  
   R* Clone();  
};  
```  
  
 マネージ拡張では、これを実現するために、インターフェイス名で修飾されたメソッド名を持つインターフェイス メソッドを明示的に宣言します。  クラスに固有のインスタンスは修飾されません。  このようにすることで、この例では、`R` のインスタンス経由で `Clone` が明示的に呼び出されたときに、その戻り値をダウンキャストする必要がなくなります。  
  
 新しい構文では、マネージ拡張の構文に代わって、一般的なオーバーライド機構が導入されています。  上記の例は次のように書き換えることができます。  
  
```  
public ref class R : public ICloneable {  
public:  
   // to be used through ICloneable  
   virtual Object^ InterfaceClone() = ICloneable::Clone;  
  
   // to be used through an R  
   virtual R^ Clone();  
};  
```  
  
 このように変更するには、明示的にオーバーライドされるインターフェイス メンバーにクラス内で一意の名前を指定する必要があります。  この例では、`InterfaceClone` という不適切な名前を指定しています。  動作はこれまでと同じで、名前を変更した `InterfaceClone,` が `ICloneable` インターフェイス経由で呼び出されます。一方、`R` 型のオブジェクト経由の呼び出しでは、2 つ目の `Clone` インスタンスが呼び出されます。  
  
## 参照  
 [クラスまたはインターフェイス内でのメンバー宣言 \(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [Explicit Overrides](../windows/explicit-overrides-cpp-component-extensions.md)