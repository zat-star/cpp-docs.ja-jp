---
title: _ _event |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __event_cpp
- __event
dev_langs:
- C++
helpviewer_keywords:
- __event keyword [C++]
- events [C++], __event
ms.assetid: d3019b3e-722e-48df-8536-c05878461f9e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 921ab0d8a18e8bb50f7ca5ea02002aa16244abcd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="event"></a>__event
イベントを宣言します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      __event   
      method-declarator  
      ;  
__event __interface interface-specifier;  
__event member-declarator;  
```  
  
## <a name="remarks"></a>コメント  
 `__event` キーワードは、メソッド宣言、インターフェイス宣言、またはデータ メンバーの宣言に適用できます。 ただし、`__event` キーワードを使用して、入れ子になったクラスのメンバーを修飾することはできません。  
  
 イベント ソースとイベント レシーバーがネイティブ C++、COM、またはマネージ (.NET Framework) であるかによって、次の構成体をイベントとして使用できます。  
  
|ネイティブ C++|COM|マネージ (.NET Framework)|  
|------------------|---------|--------------------------------|  
|メソッド|—|メソッド|  
|—|interface|—|  
|—|—|データ メンバー|  
  
 使用して[_ _hook](../cpp/hook.md)ハンドラー メソッドをイベント メソッドに関連付けるには、イベント レシーバーでします。 `__event` キーワードを使用してイベントを作成した後、そのイベントが呼び出されると、そのイベントにフックされているすべてのイベント ハンドラーが呼び出されることに注意してください。  
  
 `__event` メソッド宣言では定義を記述できません。定義は暗黙的に生成されるため、通常のメソッドと同じようにイベント メソッドを呼び出すことができます。  
  
> [!NOTE]
>  テンプレート クラスまたは構造体にイベントを含めることはできません。  
  
## <a name="native-events"></a>ネイティブ イベント  
 ネイティブ イベントはメソッドです。 戻り値の型は、通常、`HRESULT` または `void` ですが、`enum` などの任意の整数型でもかまいません。 イベントが整数の戻り値の型を使用していて、イベント ハンドラーがゼロ以外の値を返すときのエラー条件が定義されていると、発生するイベントは他のデリゲートを呼び出します。  
  
```  
// Examples of native C++ events:  
__event void OnDblClick();  
__event HRESULT OnClick(int* b, char* s);  
```  
  
 参照してください[ネイティブ C++ でのイベント処理](../cpp/event-handling-in-native-cpp.md)サンプル コードについてはします。  
  
## <a name="com-events"></a>COM イベント  
 COM イベントはインターフェイスです。 イベント ソース インターフェイスのメソッドのパラメーターにする必要があります**で**パラメーター (ただし、これが厳格に強制されていません)、ため、**アウト**パラメーターはマルチキャストした場合に便利です。 使用する場合に、レベル 1 の警告が発行される、**アウト**パラメーター。  
  
 戻り値の型は、通常、`HRESULT` または `void` ですが、`enum` などの任意の整数型でもかまいません。 イベントが整数の戻り値の型を使用していて、イベント ハンドラーがゼロ以外の値を返すと、これはエラー状態であり、発生するイベントは他のデリゲートの呼び出しをアボートします。 コンパイラは、イベント ソース インターフェイスとしてに自動的にマークされますに注意してください、[ソース](../windows/source-cpp.md)生成された IDL にします。  
  
 [_ _Interface](../cpp/interface.md)キーワードの後に必要なは常に`__event`COM イベント ソース。  
  
```  
// Example of a COM event:  
__event __interface IEvent1;  
```  
  
 参照してください[COM でのイベント処理](../cpp/event-handling-in-com.md)サンプル コードについてはします。  
  
## <a name="managed-events"></a>マネージ イベント  
 新しい構文でイベントをコーディング方法の詳細については、次を参照してください。[イベント](../windows/event-cpp-component-extensions.md)です。  
  
 マネージ イベントは、データ メンバーまたはメソッドです。 デリゲートの戻り値の型に準拠している必要がありますイベントと共に使用すると、[共通言語仕様](/dotnet/standard/language-independence-and-language-independent-components)です。 イベント ハンドラーの戻り値の型は、デリゲートの戻り値の型と一致する必要があります。 デリゲートの詳細については、次を参照してください。[デリゲートとイベント](../dotnet/delegates-and-events.md)です。 マネージ イベントがメンバー関数である場合、その型はデリゲートへのポインターでなければなりません。  
  
 .NET Framework では、それ自身がメソッド (つまり、対応するデリゲートの `Invoke` メソッド) であるかのようにデータ メンバーを処理できます。 マネージ イベント データ メンバーを宣言するためのデリゲート型を事前に定義する必要があります。 これに対し、マネージ イベント メソッドは、まだ定義されていない場合、対応するマネージ デリゲートを暗黙的に定義します。 たとえば、次のように、`OnClick` などのイベント値をイベントとして宣言できます。  
  
```  
// Examples of managed events:  
__event ClickEventHandler* OnClick;  // data member as event  
__event void OnClick(String* s);  // method as event  
```  
  
 マネージ イベントを暗黙的に宣言するときは、イベント ハンドラーが追加または削除されたときに呼び出される追加および削除アクセサーを指定できます。 クラスの外部からイベントを呼び出す (発生させる) メソッドを定義することもできます。  
  
## <a name="example-native-events"></a>例: ネイティブ イベント  
  
```  
// EventHandling_Native_Event.cpp  
// compile with: /c  
[event_source(native)]  
class CSource {  
public:  
   __event void MyEvent(int nValue);  
};  
```  
  
## <a name="example-com-events"></a>例: COM イベント  
  
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
  
## <a name="see-also"></a>関連項目  
 [キーワード](../cpp/keywords-cpp.md)   
 [イベント処理](../cpp/event-handling.md)   
 [event_source](../windows/event-source.md)   
 [event_receiver](../windows/event-receiver.md)   
 [_ _hook します。](../cpp/hook.md)   
 [_ _unhook](../cpp/unhook.md)   
 [__raise](../cpp/raise.md)