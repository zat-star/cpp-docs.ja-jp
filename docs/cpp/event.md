---
title: "__event | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__event_cpp"
  - "__event"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__event キーワード [C++]"
  - "イベント [C++], __event"
ms.assetid: d3019b3e-722e-48df-8536-c05878461f9e
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __event
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

イベントを宣言します。  
  
## 構文  
  
```  
  
      __event   
      method-declarator  
      ;  
__event __interface interface-specifier;  
__event member-declarator;  
```  
  
## 解説  
 `__event` キーワードは、メソッド宣言、インターフェイス宣言、またはデータ メンバーの宣言に適用できます。  ただし、`__event` キーワードを使用して、入れ子になったクラスのメンバーを修飾することはできません。  
  
 イベント ソースとイベント レシーバーがネイティブ C\+\+、COM、またはマネージ \(.NET Framework\) であるかによって、次の構成体をイベントとして使用できます。  
  
|ネイティブ C\+\+|COM|マネージ \(.NET Framework\)|  
|-----------------|---------|-----------------------------|  
|方法|—|メソッド|  
|—|インターフェイス|—|  
|—|—|データ メンバー|  
  
 ハンドラー メソッドをイベント メソッドに関連付けるには、イベント レシーバー内で [\_\_hook](../cpp/hook.md) を使用します。  `__event` キーワードを使用してイベントを作成した後、そのイベントが呼び出されると、そのイベントにフックされているすべてのイベント ハンドラーが呼び出されることに注意してください。  
  
 `__event` メソッド宣言では定義を記述できません。定義は暗黙的に生成されるため、通常のメソッドと同じようにイベント メソッドを呼び出すことができます。  
  
> [!NOTE]
>  テンプレート クラスまたは構造体にイベントを含めることはできません。  
  
## ネイティブ イベント  
 ネイティブ イベントはメソッドです。  戻り値の型は、通常、`HRESULT` または `void` ですが、`enum` などの任意の整数型でもかまいません。  イベントが整数の戻り値の型を使用していて、イベント ハンドラーがゼロ以外の値を返すときのエラー条件が定義されていると、発生するイベントは他のデリゲートを呼び出します。  
  
```  
// Examples of native C++ events:  
__event void OnDblClick();  
__event HRESULT OnClick(int* b, char* s);  
```  
  
 サンプル コードについては、「[ネイティブ C\+\+ でのイベント処理](../Topic/Event%20Handling%20in%20Native%20C++.md)」を参照してください。  
  
## COM イベント  
 COM イベントはインターフェイスです。  イベント ソース インターフェイスのメソッドのパラメーターは、**in** パラメーターである必要があります \(ただし、厳密には適用されません\)。これは、**out** パラメーターはマルチキャストした場合に有効ではないためです。  レベル 1 の警告は **out** パラメーターを使用した場合に発行されます。  
  
 戻り値の型は、通常、`HRESULT` または `void` ですが、`enum` などの任意の整数型でもかまいません。  イベントが整数の戻り値の型を使用していて、イベント ハンドラーがゼロ以外の値を返すと、これはエラー状態であり、発生するイベントは他のデリゲートの呼び出しをアボートします。  コンパイラは、生成する IDL でイベント ソース インターフェイスを[ソース](../Topic/source%20\(C++\).md)として自動的にマークすることに注意してください。  
  
 [\_\_interface](../Topic/__interface.md) キーワードは、常に COM イベント ソースの `__event` の後に指定する必要があります。  
  
```  
// Example of a COM event:  
__event __interface IEvent1;  
```  
  
 サンプル コードについては、「[COM でのイベント処理](../cpp/event-handling-in-com.md)」を参照してください。  
  
## マネージ イベント  
 新しい構文でイベントをコーディングする方法については、「[event](../windows/event-cpp-component-extensions.md)」を参照してください。  
  
 マネージ イベントは、データ メンバーまたはメソッドです。  イベントで使用する場合、デリゲートの戻り値の型は[共通言語仕様](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)に準拠している必要があります。  イベント ハンドラーの戻り値の型は、デリゲートの戻り値の型と一致する必要があります。  デリゲートの詳細については、「[\_\_delegate](../Topic/__delegate.md)」を参照してください。  マネージ イベントがメンバー関数である場合、その型はデリゲートへのポインターでなければなりません。  
  
 .NET Framework では、それ自身がメソッド \(つまり、対応するデリゲートの `Invoke` メソッド\) であるかのようにデータ メンバーを処理できます。  マネージ イベント データ メンバーを宣言するためのデリゲート型を事前に定義する必要があります。  これに対し、マネージ イベント メソッドは、まだ定義されていない場合、対応するマネージ デリゲートを暗黙的に定義します。  たとえば、次のように、`OnClick` などのイベント値をイベントとして宣言できます。  
  
```  
// Examples of managed events:  
__event ClickEventHandler* OnClick;  // data member as event  
__event void OnClick(String* s);  // method as event  
```  
  
 マネージ イベントを暗黙的に宣言するときは、イベント ハンドラーが追加または削除されたときに呼び出される追加および削除アクセサーを指定できます。  クラスの外部からイベントを呼び出す \(発生させる\) メソッドを定義することもできます。  
  
## 例: ネイティブ イベント  
  
```  
// EventHandling_Native_Event.cpp  
// compile with: /c  
[event_source(native)]  
class CSource {  
public:  
   __event void MyEvent(int nValue);  
};  
```  
  
## 例: COM イベント  
  
```  
// EventHandling_COM_Event.cpp  
// compile with: /c  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
  
[ module(dll, name="EventSource", uuid="6E46B59E-89C3-4c15-A6D8-B8A1CEC98830") ];  
  
[ dual, uuid("00000000-0000-0000-0000-000000000002") ]  
__interface IEventSource {  
   [id(1)] HRESULT MyEvent();  
};  
 [ coclass, uuid("00000000-0000-0000-0000-000000000003"),  event_source(com) ]  
class CSource : public IEventSource {  
public:  
   __event __interface IEventSource;  
   HRESULT FireEvent() {  
      __raise MyEvent();  
      return S_OK;  
   }  
};  
```  
  
## 例: マネージ イベント  
  
```  
// EventHandling_Managed_Event.cpp  
// compile with: /clr:oldSyntax /c  
using namespace System;  
[event_source(managed)]  
public __gc class CPSource {  
  
public:  
   __event void MyEvent(Int16 nValue);  
};  
```  
  
 イベントに属性を適用するときは、その属性を生成されたメソッドに適用するか、生成されたデリゲートの呼び出しメソッドに適用するかを指定できます。  既定 \(`event:`\) では、属性がイベントに適用されます。  
  
```  
// EventHandling_Managed_Event_2.cpp  
// compile with: /clr:oldSyntax /c  
using namespace System;  
[attribute(All, AllowMultiple=true)]  
public __gc class Attr {};  
  
public __delegate void D();  
  
public __gc class X {  
public:  
   [method:Attr] __event D* E;  
   [returnvalue:Attr] __event void noE();  
};  
```  
  
## 参照  
 [C\+\+ キーワード](../cpp/keywords-cpp.md)   
 [イベント処理](../cpp/event-handling.md)   
 [event\_source](../windows/event-source.md)   
 [event\_receiver](../windows/event-receiver.md)   
 [\_\_hook](../cpp/hook.md)   
 [\_\_unhook](../cpp/unhook.md)   
 [\_\_raise](../cpp/raise.md)