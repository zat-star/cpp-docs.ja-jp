---
title: "ICommandUI インターフェイス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ICommandUI
- AFXWINFORMS/ICommandUI
- AFXWINFORMS/icommandui__Check
- AFXWINFORMS/ICommandUI::ContinueRouting
- AFXWINFORMS/ICommandUI::Enabled
- AFXWINFORMS/ICommandUI::ID
- AFXWINFORMS/ICommandUI::Index
- AFXWINFORMS/ICommandUI::Radio
- AFXWINFORMS/ICommandUI::Text
dev_langs:
- C++
helpviewer_keywords:
- ICommandUI interface
ms.assetid: 134afe8d-dcdf-47ca-857a-a166a6b665dd
caps.latest.revision: 24
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 1db6b3fa58639140322816c37103566353b15633
ms.lasthandoff: 02/24/2017

---
# <a name="icommandui-interface"></a>ICommandUI インターフェイス
ユーザー インターフェイスのコマンドを管理します。  
  
## <a name="syntax"></a>構文  
  
```  
interface class ICommandUI  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[icommandui__Check](#check)|このコマンドのユーザー インターフェイス項目を適切なチェックの状態に設定します。|  
|[ICommandUI::ContinueRouting](#continuerouting)|ハンドラーのチェーンに現在のメッセージを渡すようにコマンド ルーティング メカニズムに指示します。|  
|[ICommandUI::Enabled](#enabled)|有効または、このコマンドのユーザー インターフェイス項目を無効にします。|  
|[ICommandUI::ID](#id)|によって表されるユーザー インターフェイス オブジェクトの ID を取得、`ICommandUI`オブジェクトです。|  
|[ICommandUI::Index](#index)|によって表されるユーザー インターフェイス オブジェクトのインデックスを取得、`ICommandUI`オブジェクトです。|  
|[ICommandUI::Radio](#radio)|このコマンドのユーザー インターフェイス項目を適切なチェックの状態に設定します。|  
|[ICommandUI::Text](#text)|このコマンドのユーザー インターフェイスの項目のテキストを設定します。|  
  
## <a name="remarks"></a>コメント  
 このインターフェイスは、ユーザー インターフェイスのコマンドを管理するメソッドとプロパティを提供します。 `ICommandUI`ような[CCmdUI クラス](../../mfc/reference/ccmdui-class.md)する点を除いて、 `ICommandUI` MFC アプリケーションでは、.NET コンポーネントと相互運用するために使用します。  
  
 `ICommandUI`内で使用される、`ON_UPDATE_COMMAND_UI`ハンドラーで、[関数](../../mfc/reference/icommandtarget-interface.md)-クラスを派生します。 有効になっていると、各メニュー項目、メニューが表示されます (選択またはクリックする) がアプリケーションのユーザーをアクティブ化または無効にします。 各メニュー コマンドのターゲット実装することでこの情報を提供する、`ON_UPDATE_COMMAND_UI`ハンドラー。 アプリケーション内のコマンドのユーザー インターフェイス オブジェクトごとに、メッセージ マップ エントリと各ハンドラーに対する関数プロトタイプを作成するのに [プロパティ] ウィンドウを使用します。  
  
 方法の詳細については`ICommandUI`インターフェイスがコマンドのルーティングで使用しを参照してください[方法: Windows フォーム コントロールへのコマンド ルーティングの追加](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)します。  
  
 Windows フォームの使用に関する詳細については、次を参照してください。 [MFC では、Windows フォーム ユーザー コントロールを使用して](../../dotnet/using-a-windows-form-user-control-in-mfc.md)します。  
  
 MFC でのユーザー インターフェイスのコマンドを管理する方法の詳細については、次を参照してください。 [CCmdUI クラス](../../mfc/reference/ccmdui-class.md)します。  
  
## <a name="check"></a>ICommandUI::Check  
このコマンドのユーザー インターフェイス項目を適切なチェックの状態に設定します。
```
property UICheckState Check;
```
## <a name="remarks"></a>コメント  
このプロパティは、このコマンドのユーザー インターフェイス項目を適切なチェックの状態に設定します。 チェックは、次の値に設定します。  
- 0 をオフにします  
- 1 のチェック  
- 不確定な設定&2;  

## <a name="continuerouting"></a>ICommandUI::ContinueRouting   
ハンドラーのチェーンに現在のメッセージを渡すようにコマンドのルーティング メカニズムに指示します。
```
void ContinueRouting();
```
## <a name="remarks"></a>コメント
これは、FALSE を返す ON_COMMAND_EX ハンドラーと組み合わせて使用する高度なメンバー関数です。 詳細については、テクニカル ノート TN006 を参照してください: メッセージ マップです。

## <a name="enabled"></a>ICommandUI::Enabled 
有効または、このコマンドのユーザー インターフェイス項目を無効にします。
```
property bool Enabled;
```
## <a name="remarks"></a>コメント
このプロパティでは、有効または、このコマンドのユーザー インターフェイス項目を無効にします。 有効にする項目を無効にする場合は FALSE の場合は true を Enabled を設定します。

## <a name="id"></a>ICommandUI::ID  
ICommandUI オブジェクトによって表されるユーザー インターフェイス オブジェクトの ID を取得します。
```
property unsigned int ID;
```
## <a name="remarks"></a>コメント
このプロパティは、メニュー項目、ツール バー ボタンまたは ICommandUI オブジェクトによって表されるその他のユーザー インターフェイス オブジェクトの ID (ハンドル) を取得します。

## <a name="index"></a>ICommandUI::Index   
ICommandUI オブジェクトによって表されるユーザー インターフェイス オブジェクトのインデックスを取得します。
```
property unsigned int Index;
```
## <a name="remarks"></a>コメント
このプロパティは、メニュー項目、ツール バー ボタンまたは ICommandUI オブジェクトによって表されるその他のユーザー インターフェイス オブジェクトのインデックス (ハンドル) を取得します。

## <a name="radio"></a>ICommandUI::Radio 
このコマンドのユーザー インターフェイス項目を適切なチェックの状態に設定します。
```
property bool Radio;
```
## <a name="remarks"></a>コメント
このプロパティは、このコマンドのユーザー インターフェイス項目を適切なチェックの状態に設定します。 無線を有効にする項目で true に設定します。それ以外の場合は FALSE。

## <a name="text"></a>ICommandUI::Text 
このコマンドのユーザー インターフェイスの項目のテキストを設定します。
```
property String^ Text;
```
## <a name="remarks"></a>コメント
このプロパティは、このコマンドのユーザー インターフェイスの項目のテキストを設定します。 テキストをテキスト文字列のハンドルに設定します。

## <a name="requirements"></a>要件  
 **ヘッダー:** afxwinforms.h (アセンブリ atlmfc\lib\mfcmifc80.dll で定義)  
  
## <a name="see-also"></a>関連項目  
 [CCmdUI クラス](../../mfc/reference/ccmdui-class.md)

