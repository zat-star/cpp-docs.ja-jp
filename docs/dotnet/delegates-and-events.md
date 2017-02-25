---
title: "デリゲートとイベント | Microsoft Docs"
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
  - "__delegate キーワード"
  - "__event キーワード [C++]"
  - "delegate キーワード [C++]"
  - "デリゲート [C++], アップグレード (C++ マネージ拡張から)"
  - "event キーワード [C++]"
  - "イベント [C++], アップグレード (C++ マネージ拡張から)"
ms.assetid: 3505c626-7e5f-4492-a947-0e2248f7b84a
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# デリゲートとイベント
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

デリゲートとイベントの宣言方法は、[!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)] では C\+\+ マネージ拡張から変更されています。  
  
 今後は、次の例で示すように、従来使用されていた 2 つのアンダースコアが不要になります。  次のコードは、マネージ拡張におけるサンプル コードです。  
  
```  
__delegate void ClickEventHandler(int, double);  
__delegate void DblClickEventHandler(String*);  
  
__gc class EventSource {  
   __event ClickEventHandler* OnClick;    
   __event DblClickEventHandler* OnDblClick;    
};  
```  
  
 新しい構文では、同じコードを次のように記述できます。  
  
```  
delegate void ClickEventHandler( int, double );  
delegate void DblClickEventHandler( String^ );  
  
ref class EventSource {  
   event ClickEventHandler^ OnClick;   
   event DblClickEventHandler^ OnDblClick;   
};  
```  
  
 イベント \(およびデリゲート\) は参照型で、新しい構文ではカレット \(`^`\) を使用することによって見やすくなっています。イベントには、明示的な宣言を使った構文だけでなく、前述のコードのような簡易形式もサポートされています。  明示的な形式では、ユーザーはイベントに関連付けられた `add`、`raise`、および `remove` の各メソッドを指定します \(`add` および `remove` メソッドだけが必須で、`raise` メソッドは省略できます\)。  
  
 マネージ拡張でこれらのメソッドを実装する場合、明示的なイベント宣言を記述することはしませんが、存在しないイベントの名前を決める必要があります。  各メソッドは、マネージ拡張の仕様にある次の例のように、`add_EventName`、`raise_EventName`、および `remove_EventName` という形式で指定されます。  
  
```  
// explicit implementations of add, remove, raise  
public __delegate void f(int);  
public __gc struct E {  
   f* _E;  
public:  
   E() { _E = 0; }  
  
   __event void add_E1(f* d) { _E += d; }  
  
   static void Go() {  
      E* pE = new E;  
      pE->E1 += new f(pE, &E::handler);  
      pE->E1(17);   
      pE->E1 -= new f(pE, &E::handler);  
      pE->E1(17);   
   }  
  
private:  
   __event void raise_E1(int i) {  
      if (_E)  
         _E(i);  
   }  
  
protected:  
   __event void remove_E1(f* d) {  
      _E -= d;  
   }  
};  
```  
  
 新しい構文では、次の書き換え例が示すように、宣言が単純化されています。  次に示すように、1 つのイベントは、イベント宣言と関連するデリゲート型に続く中かっこ内で、2 つまたは 3 つのメソッドを指定します。  
  
```  
public delegate void f( int );  
public ref struct E {  
private:  
   f^ _E; // delegates are also reference types  
  
public:  
   E() {  // note the replacement of 0 with nullptr!  
      _E = nullptr;   
   }  
  
   // the new aggregate syntax of an explicit event declaration  
   event f^ E1 {  
   public:  
      void add( f^ d ) {  
         _E += d;  
      }  
  
   protected:  
      void remove( f^ d ) {  
         _E -= d;  
      }  
  
   private:  
      void raise( int i ) {  
         if ( _E )  
            _E( i );  
      }  
   }  
  
   static void Go() {  
      E^ pE = gcnew E;  
      pE->E1 += gcnew f( pE, &E::handler );  
      pE->E1( 17 );   
      pE->E1 -= gcnew f( pE, &E::handler );  
      pE->E1( 17 );   
   }  
};  
```  
  
## 参照  
 [クラスまたはインターフェイス内でのメンバー宣言 \(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [delegate](../windows/delegate-cpp-component-extensions.md)   
 [event](../windows/event-cpp-component-extensions.md)