---
title: "accelerator_view クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amprt/Concurrency::accelerator_view
dev_langs:
- C++
helpviewer_keywords:
- accelerator_view class
ms.assetid: 9f298c21-bf62-46e0-88b8-01c5c78ef144
caps.latest.revision: 18
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 78569f1ff21af3ed05cb908a851f0fe05d5d271a
ms.lasthandoff: 02/24/2017

---
# <a name="acceleratorview-class"></a>accelerator_view クラス
C ++. AMP のデータ並列アクセラレータでの仮想デバイスの抽象化を表します。  
  
### <a name="syntax"></a>構文  
  
```  
class accelerator_view;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[accelerator_view コンス トラクター](#ctor)|`accelerator_view` クラスの新しいインスタンスを初期化します。|  
|[~ accelerator_view デストラクター](#dtor)|`accelerator_view` オブジェクトを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[create_marker メソッド](#create_marker)|これまでにこの `accelerator_view` オブジェクトに送信されたすべてのコマンドの完了を追跡するために予定を返します。|  
|[flush メソッド](#flush)|`accelerator_view` オブジェクトのキューに格納されたすべての保留中のコマンドを実行のためにアクセラレータに送信します。|  
|[get_accelerator メソッド](#get_accelerator)|`accelerator` オブジェクトの `accelerator_view` オブジェクトを返します。|  
|[get_is_auto_selection メソッド](#get_is_auto_selection)|ランタイムの適切なアクセラレータが自動的に選択するかどうかを示すブール値を返すときに、`accelerator_view`に渡されるオブジェクト、 [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)します。|  
|[get_is_debug メソッド](#get_is_debug)|`accelerator_view` オブジェクトに広範なエラー レポートに有効なデバッグ レイヤーがあるかどうかを示すブール値を返します。|  
|[get_queuing_mode メソッド](#get_queuing_mode)|`accelerator_view` オブジェクトのキュー モードを返します。|  
|[get_version メソッド](#get_version)|`accelerator_view` のバージョンを返します。|  
|[wait メソッド](#wait)|終了する `accelerator_view` オブジェクトに送信されるすべてのコマンドを待機します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[operator! = 演算子](#operator_neq)|この `accelerator_view` オブジェクトを別のオブジェクトと比較し、同じ場合は `false` を返し、それ以外の場合は `true` を返します。|  
|[operator = 演算子](#operator_eq)|指定された `accelerator_view` オブジェクトの内容をこのオブジェクトにコピーします。|  
|[operator = 演算子](#operator_eq_eq)|この `accelerator_view` オブジェクトを別のオブジェクトと比較し、同じ場合は `true` を返し、それ以外の場合は `false` を返します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[accelerator データ メンバー](#accelerator)|`accelerator` オブジェクトの `accelerator_view` オブジェクトを取得します。|  
|[is_auto_selection データ メンバー](#is_auto_selection)|ランタイムの適切なアクセラレータが自動的に選択するかどうかを示すブール値を取得ときに、`accelerator_view`に渡されるオブジェクト、 [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)します。|  
|[is_debug データ メンバー](#is_debug)|`accelerator_view` オブジェクトに広範なエラー レポートに有効なデバッグ レイヤーがあるかどうかを示すブール値を取得します。|  
|[queuing_mode データ メンバー](#queuing_mode)|`accelerator_view` オブジェクトのキュー モードを取得します。|  
|[バージョン データ メンバー](#version)|accelerator のバージョンを取得します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `accelerator_view`  
  
### <a name="remarks"></a>コメント  
 `accelerator_view` オブジェクトは、アクセラレータの論理的で分離されたビューを表します。 単一の物理計算デバイスは、多くの論理的で分離された `accelerator_view` オブジェクトを使用できます。 各アクセラレータには既定の `accelerator_view` オブジェクトがあります。 追加の `accelerator_view` オブジェクトを作成できます。  
  
 物理デバイスは、多くのクライアント スレッド間で共有できます。 クライアント スレッドがアクセラレータの同じ `accelerator_view` オブジェクトを協調的に使用することができるか、または、各クライアントが他のクライアント スレッドから分離するために独立した `accelerator_view` オブジェクトを使用して計算デバイスと通信できます。  
  
 `accelerator_view`オブジェクトは、2 つのいずれかを設定できます[queuing_mode 列挙型](concurrency-namespace-enums-amp.md#queuing_mode)状態です。 キュー モードが `immediate` である場合、`copy` および `parallel_for_each` のようなコマンドが呼び出し元に戻るとすぐに対応するアクセラレータ デバイスに送信されます。 キュー モードが `deferred` の場合、このようなコマンドは `accelerator_view` オブジェクトに対応するコマンド キューに置かれます。 コマンドは、`flush()` が呼び出されるまでデバイスに実際に送信されません。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** amprt.h  
  
 **名前空間:** Concurrency  

## <a name="a-nameacceleratora-accelerator"></a><a name="accelerator"></a>アクセラレータ 

Accelerator_view オブジェクトのアクセラレータのオブジェクトを取得します。  
  
### <a name="syntax"></a>構文  
  
```  
__declspec(property(get= get_accelerator)) Concurrency::accelerator accelerator;  
```  
  
## <a name="a-namectora-acceleratorview"></a><a name="ctor"></a>accelerator_view 

既存のコピーによって accelerator_view クラスの新しいインスタンスを初期化します。`accelerator_view`オブジェクトです。  
  
### <a name="syntax"></a>構文  
  
```  
accelerator_view( const accelerator_view & _Other );  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Other`  
 コピーする `accelerator_view` オブジェクト。  
  
## <a name="a-nameacceleratorviewcreatemarkera-createmarker"></a><a name="accelerator_view__create_marker"></a>create_marker 

これまでにこの `accelerator_view` オブジェクトに送信されたすべてのコマンドの完了を追跡するために予定を返します。  
  
### <a name="syntax"></a>構文  
  
```  
concurrency::completion_future create_marker();  
```  
  
### <a name="return-value"></a>戻り値  
 これまでこの `accelerator_view` オブジェクトに送信されたすべてのコマンドの完了を追跡するための予定です。  
  
## <a name="a-nameflusha-flush"></a><a name="flush"></a>フラッシュ 

実行のためにアクセラレータに accelerator_view オブジェクトをキューに保留中のすべてのコマンドを送信します。  
  
### <a name="syntax"></a>構文  
  
```  
void flush();  
```  
  
### <a name="return-value"></a>戻り値  
 `void` を返します。  

## <a name="a-nameacceleratorviewgetacceleratora-getaccelerator"></a><a name="accelerator_view__get_accelerator"></a>get_accelerator 

Accelerator_view オブジェクトのアクセラレータのオブジェクトを返します。
### <a name="syntax"></a>構文
```
accelerator get_accelerator() const;
```
### <a name="return-value"></a>戻り値
Accelerator_view オブジェクトのアクセラレータのオブジェクト。

## <a name="a-nameacceleratorviewgetisautoselectiona-getisautoselection"></a><a name="accelerator_view__get_is_auto_selection"></a>get_is_auto_selection 

選択を示すかどうか、ランタイムは自動的に適切なアクセラレータ accelerator_view に渡されるブール値を返す、 [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)します。  
  
### <a name="syntax"></a>構文  
  
```  
bool get_is_auto_selection() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ランタイムが自動的に適切なアクセラレータを選択する場合は `true`、それ以外の場合は `false`。  
  
## <a name="a-nameacceleratorviewgetisdebuga-getisdebug"></a><a name="accelerator_view__get_is_debug"></a>get_is_debug 

Accelerator_view オブジェクトに広範なエラー レポートに有効なデバッグ レイヤーがあるかどうかを示すブール値を返します。  
  
### <a name="syntax"></a>構文  
  
```  
bool get_is_debug() const;  
```  
  
### <a name="return-value"></a>戻り値  
 示すブール値かどうか、`accelerator_view`広範なエラー レポートに有効なデバッグ レイヤーが付きます。  

## <a name="a-nameacceleratorviewgetqueuingmodea-getqueuingmode"></a><a name="accelerator_view__get_queuing_mode"></a>get_queuing_mode 

Accelerator_view オブジェクトのキュー モードを返します。  
  
### <a name="syntax"></a>構文  
  
```  
queuing_mode get_queuing_mode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 キュー モード、`accelerator_view`オブジェクトです。  
  
## <a name="a-nameacceleratorviewgetversiona-getversion"></a><a name="accelerator_view__get_version"></a>get_version 

Accelerator_view のバージョンを返します。  
  
### <a name="syntax"></a>構文  
  
```  
unsigned int get_version() const;  
```  
  
### <a name="return-value"></a>戻り値  
 バージョン、`accelerator_view`です。  
  
## <a name="a-nameacceleratorviewisautoselectiona-isautoselection"></a><a name="accelerator_view__is_auto_selection"></a>is_auto_selection 

選択を示すかどうか、ランタイムは自動的に適切なアクセラレータ accelerator_view に渡されるブール値を取得、 [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each)します。  
  
### <a name="syntax"></a>構文  
  
```  
__declspec(property(get= get_is_auto_selection)) bool is_auto_selection;  
```  
  
## <a name="a-nameacceleratorviewisdebuga-isdebug"></a><a name="accelerator_view__is_debug"></a>is_debug 

Accelerator_view オブジェクトに広範なエラー レポートに有効なデバッグ レイヤーがあるかどうかを示すブール値を取得します。  
  
### <a name="syntax"></a>構文  
  
```  
__declspec(property(get= get_is_debug)) bool is_debug;  
```  
  
## <a name="a-nameacceleratorviewoperatorneqa-operator"></a><a name="accelerator_view__operator_neq"></a>operator! = 

別の場合は、この accelerator_view オブジェクトを比較し、返します`false`は同じである場合、それ以外の場合を返します`true`します。  
  
### <a name="syntax"></a>構文  
  
```  
bool operator!= (    const accelerator_view & _Other ) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Other`  
 `accelerator_view`これと比較するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 2 つのオブジェクトが同一である場合は `false`。それ以外の場合は `true`。  
  
## <a name="a-nameacceleratorviewoperatoreqa-operator"></a><a name="accelerator_view__operator_eq"></a>演算子 = 

これには、指定された accelerator_view オブジェクトの内容をコピーします。  
  
### <a name="syntax"></a>構文  
  
```  
accelerator_view & operator= (    const accelerator_view & _Other );  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Other`  
 コピー元の `accelerator_view` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 変更したへの参照を`accelerator_view`オブジェクトです。  
  
## <a name="a-nameacceleratorviewoperatoreqeqa-operator"></a><a name="accelerator_view__operator_eq_eq"></a>演算子 = = 

別の場合は、この accelerator_view オブジェクトを比較し、返します`true`は同じである場合、それ以外の場合を返します`false`します。  
  
### <a name="syntax"></a>構文  
  
```  
bool operator= = (    const accelerator_view & _Other ) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Other`  
 `accelerator_view`これと比較するオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 2 つのオブジェクトが同一である場合は `true`。それ以外の場合は `false`。  
  
## <a name="a-nameacceleratorviewqueuingmodea-queuingmode"></a><a name="accelerator_view__queuing_mode"></a>queuing_mode 

Accelerator_view オブジェクトのキュー モードを取得します。  
  
### <a name="syntax"></a>構文  
  
```  
__declspec(property(get= get_queuing_mode)) Concurrency::queuing_mode queuing_mode;  
```  
  
## <a name="a-nameacceleratorviewversiona-version"></a><a name="accelerator_view__version"></a>バージョン 

Accelerator_view のバージョンを取得します。  
  
### <a name="syntax"></a>構文  
  
```  
__declspec(property(get= get_version)) unsigned int version;  
```  
  
## <a name="a-nameacceleratorviewwaita-wait"></a><a name="accelerator_view__wait"></a>待機 

Accelerator_view オブジェクトに送信されたすべてのコマンドを完了するまで待機します。  
  
### <a name="syntax"></a>構文  
  
```  
void wait();  
```  
  
#### <a name="return-value"></a>戻り値  
 `void` を返します。  
  
#### <a name="remarks"></a>コメント  
 場合、 [queuing_mode](concurrency-namespace-enums-amp.md#queuing_mode)は`immediate`、ブロックすることがなく、このメソッドをすぐに返します。  
  
##  <a name="a-namedtora-acceleratorview"></a><a name="dtor"></a>~ accelerator_view 

 Accelerator_view オブジェクトを破棄します。  
  
#### <a name="syntax"></a>構文  
  
```  
~accelerator_view();  
```  
  
### <a name="return-value"></a>戻り値  
  
 
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)

