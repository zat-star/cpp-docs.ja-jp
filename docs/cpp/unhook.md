---
title: "_ _unhook |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __unhook
- __unhook_cpp
dev_langs:
- C++
helpviewer_keywords:
- event handlers [C++], dissociating events
- __unhook keyword [C++]
ms.assetid: 953a14f3-5199-459d-81e5-fcf015a19878
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1513391aedf9a08cd1ece971d79fd5f6913d406d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="unhook"></a>__unhook
イベントからハンドラー メソッドの関連付けを解除します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      long  __unhook(  
   &SourceClass::EventMethod,  
   source,  
   &ReceiverClass::HandlerMethod  
   [, receiver = this]   
);  
long  __unhook(   
   interface,  
   source  
);  
long  __unhook(  
   source   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 **&***SourceClass* `::` *EventMethod*  
 イベント ハンドラー メソッドをアンフックする元のイベント メソッドへのポインター。  
  
-   ネイティブ C++ イベント: *SourceClass*は、イベント ソース クラスと*EventMethod*イベントします。  
  
-   COM イベント: *SourceClass*は、イベント ソース インターフェイスと*EventMethod*はそのメソッドの 1 つです。  
  
-   マネージ イベント: *SourceClass*は、イベント ソース クラスと*EventMethod*イベントします。  
  
 `interface`  
 Unhooked されているインターフェイスの名前`receiver`、する COM イベント レシーバーにのみ、 *layout_dependent*のパラメーター、 [event_receiver](../windows/event-receiver.md)属性は**true**.  
  
 *ソース*  
 イベント ソースのインスタンスへのポインター。 コードに応じて`type`で指定された**event_receiver**、*ソース*次のいずれかになります。  
  
-   ネイティブ イベント ソース オブジェクト ポインター。  
  
-   **IUnknown**-ベース ポインター (COM ソース)。  
  
-   マネージ オブジェクトのポインター (マネージ イベントの場合)。  
  
 **&***ReceiverClass* `::``HandlerMethod`  
 イベントからアンフックするイベント ハンドラー メソッドへのポインター。 ハンドラーは、クラスのメソッドまたはそれへの参照として指定されます。ユーザーがクラス名を指定しない場合、`__unhook` は、それを呼び出したクラスを使用します。  
  
-   ネイティブ C++ イベント: *ReceiverClass*イベント レシーバー クラスと`HandlerMethod`ハンドラーします。  
  
-   COM イベント: *ReceiverClass*は、イベント レシーバー インターフェイスと`HandlerMethod`そのハンドラーの 1 つです。  
  
-   マネージ イベント: *ReceiverClass*イベント レシーバー クラスと`HandlerMethod`ハンドラーします。  
  
 `receiver`(省略可能)  
 イベント レシーバー クラスのインスタンスへのポインター。 レシーバーを指定しない場合、既定値は `__unhook` が呼び出されるレシーバー クラスまたは構造体です。  
  
## <a name="usage"></a>使用法  
 イベント レシーバー クラス外の main を含む、任意の関数スコープで使用できます。  
  
## <a name="remarks"></a>コメント  
 ハンドラー メソッドとイベント メソッドとの関連付けを解除、つまり "アンフック" するには、イベント レシーバー内で組み込み関数 `__unhook` を使用します。  
  
 `__unhook` には 3 つの形式があります。 ほとんどの場合、最初の形式 (引数が 4 つ) を使用できます。 `__unhook` の 2 番目 (引数が 2 つ) の形式は、COM イベント レシーバーにのみ使用でき、イベント インターフェイス全体がアンフックされます。 3 番目 (引数が 1 つ) の形式は、指定したソースからすべてのデリゲートをアンフックする場合に使用します。  
  
 ゼロ以外の戻り値は、エラーが発生したことを示します (マネージ イベントは例外をスローします)。  
  
 フックされていないイベントやイベント ハンドラーに対して `__unhook` を呼び出した場合、効果はありません。  
  
 コンパイル時に、コンパイラはイベントが存在することを確認し、指定されたハンドラーを使用してパラメーターの型チェックを実行します。  
  
 COM イベントを除き、`__hook` と `__unhook` は、イベント レシーバーの外部で呼び出すことができます。  
  
 `__unhook` の使用の代替手段は、-= 演算子を使用することです。  
  
 新しい構文で管理されているイベントのコーディング方法の詳細については、次を参照してください。[イベント](../windows/event-cpp-component-extensions.md)です。  
  
> [!NOTE]
>  テンプレート クラスまたは構造体にイベントを含めることはできません。  
  
## <a name="example"></a>例  
 参照してください[ネイティブ C++ でのイベント処理](../cpp/event-handling-in-native-cpp.md)と[COM でのイベント処理](../cpp/event-handling-in-com.md)サンプルについてはします。  
  
## <a name="see-also"></a>参照  
 [キーワード](../cpp/keywords-cpp.md)   
 [event_source](../windows/event-source.md)   
 [event_receiver](../windows/event-receiver.md)   
 [_ _event](../cpp/event.md)   
 [_ _hook します。](../cpp/hook.md)   
 [__raise](../cpp/raise.md)