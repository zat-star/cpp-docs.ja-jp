---
title: _ _hook |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __hook_cpp
dev_langs:
- C++
helpviewer_keywords:
- __hook keyword [C++]
- event handlers [C++], connecting events to
ms.assetid: f4cabb10-d293-4c0e-a1d2-4745ef9cc22c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d46a9c593826e804c62ab67b8afa894912d15bd8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="hook"></a>__hook
ハンドラー メソッドをイベントに関連付けます。  
  
## <a name="syntax"></a>構文  
  
```  
  
      long __hook(  
   &SourceClass::EventMethod,  
   source,  
   &ReceiverClass::HandlerMethod  
   [, receiver = this]  
);  
long __hook(  
   interface,  
   source  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 **&** *SourceClass* `::` *EventMethod*  
 イベント ハンドラー メソッドをフックする先のイベント メソッドへのポインター。  
  
-   ネイティブ C++ イベント: *SourceClass*は、イベント ソース クラスと*EventMethod*イベントします。  
  
-   COM イベント: *SourceClass*は、イベント ソース インターフェイスと*EventMethod*はそのメソッドの 1 つです。  
  
-   マネージ イベント: *SourceClass*は、イベント ソース クラスと*EventMethod*イベントします。  
  
 `interface`  
 接続されているインターフェイスの名前`receiver`、する COM イベント レシーバーにのみ、 *layout_dependent*のパラメーター、 [event_receiver](../windows/event-receiver.md)属性は**true**.  
  
 *ソース*  
 イベント ソースのインスタンスへのポインター。 コードに応じて`type`で指定された**event_receiver**、*ソース*次のいずれかになります。  
  
-   ネイティブ イベント ソース オブジェクト ポインター。  
  
-   **IUnknown**-ベース ポインター (COM ソース)。  
  
-   マネージ オブジェクトのポインター (マネージ イベントの場合)。  
  
 **&** *ReceiverClass* `::` `HandlerMethod`  
 イベントにフックするイベント ハンドラー メソッドへのポインター。 ハンドラーは、クラスのメソッドまたはそれへの参照として指定されます。ユーザーがクラス名を指定しない場合、`__hook` は、それを呼び出したクラスを使用します。  
  
-   ネイティブ C++ イベント: *ReceiverClass*イベント レシーバー クラスと`HandlerMethod`ハンドラーします。  
  
-   COM イベント: *ReceiverClass*は、イベント レシーバー インターフェイスと`HandlerMethod`そのハンドラーの 1 つです。  
  
-   マネージ イベント: *ReceiverClass*イベント レシーバー クラスと`HandlerMethod`ハンドラーします。  
  
 `receiver`(省略可能)  
 イベント レシーバー クラスのインスタンスへのポインター。 レシーバーを指定しない場合、既定値は `__hook` が呼び出されるレシーバー クラスまたは構造体です。  
  
## <a name="usage"></a>使用法  
 イベント レシーバー クラス外の main を含む、任意の関数スコープで使用できます。  
  
## <a name="remarks"></a>コメント  
 ハンドラー メソッドをイベント メソッドに関連付けるかフックするには、イベント レシーバー内で組み込み関数 `__hook` を使用します。 ソースで指定されたイベントが発生すると、指定されたハンドラーが呼び出されます。 複数のイベント ハンドラーを 1 つのイベントに、または複数のイベントを 1 つのイベント ハンドラーにフックすることができます。  
  
 `__hook` には 2 つの形式があります。 COM のイベント レシーバーを具体的には、ほとんどの場合、最初 (引数が 4 つ) の形式を使用することができます、 *layout_dependent*のパラメーター、 [event_receiver](../windows/event-receiver.md)属性は**false**.  
  
 このような場合、メソッドの 1 つでイベントを発生させる前に、インターフェイスのすべてのメソッドをフックする必要はありません。イベントを処理するメソッドのみフックする必要があります。 2 番目 (引数が 2 つ) の形式を使用する`__hook`する COM イベント レシーバーにのみ * layout_dependent ***= true**です。  
  
 `__hook` は long 型の値を返します。 ゼロ以外の戻り値は、エラーが発生したことを示します (マネージ イベントは例外をスローします)。  
  
 コンパイラは、イベントが存在するかどうかをチェックし、イベント プロシージャがデリゲート シグネチャと一致することを確認します。  
  
 COM イベントを除き、`__hook` と `__unhook` は、イベント レシーバーの外部で呼び出すことができます。  
  
 `__hook` の使用の代替手段は、+= 演算子を使用することです。  
  
 新しい構文で管理されているイベントのコーディング方法の詳細については、次を参照してください。[イベント](../windows/event-cpp-component-extensions.md)です。  
  
> [!NOTE]
>  テンプレート クラスまたは構造体にイベントを含めることはできません。  
  
## <a name="example"></a>例  
 参照してください[ネイティブ C++ でのイベント処理](../cpp/event-handling-in-native-cpp.md)と[COM でのイベント処理](../cpp/event-handling-in-com.md)サンプルについてはします。  
  
## <a name="see-also"></a>関連項目  
 [キーワード](../cpp/keywords-cpp.md)   
 [イベント処理](../cpp/event-handling.md)   
 [event_source](../windows/event-source.md)   
 [event_receiver](../windows/event-receiver.md)   
 [_ _unhook](../cpp/unhook.md)   
 [__raise](../cpp/raise.md)