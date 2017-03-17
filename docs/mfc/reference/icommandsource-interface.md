---
title: "ICommandSource インターフェイス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ICommandSource
- AFXWINFORMS/ICommandSource
- AFXWINFORMS/ICommandSource::AddCommandHandler
- AFXWINFORMS/ICommandSource::AddCommandRangeHandler
- AFXWINFORMS/ICommandSource::AddCommandRangeUIHandler
- AFXWINFORMS/ICommandSource::AddCommandUIHandler
- AFXWINFORMS/ICommandSource::PostCommand
- AFXWINFORMS/ICommandSource::RemoveCommandHandler
- AFXWINFORMS/ICommandSource::RemoveCommandRangeHandler
- AFXWINFORMS/ICommandSource::RemoveCommandRangeUIHandler
- AFXWINFORMS/ICommandSource::RemoveCommandUIHandler
- AFXWINFORMS/ICommandSource::SendCommand
dev_langs:
- C++
helpviewer_keywords:
- ICommandSource interface
ms.assetid: a4b1f698-c09f-4ba8-9b13-0e74a0a4967e
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
ms.openlocfilehash: f923a8a42327cb74ce9323f72aae90c7411da27c
ms.lasthandoff: 02/24/2017

---
# <a name="icommandsource-interface"></a>ICommandSource インターフェイス
ユーザー コントロールにコマンド ソース オブジェクトから送信されたコマンドを管理します。  
  
## <a name="syntax"></a>構文  
  
```  
interface class ICommandSource  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[ICommandSource::AddCommandHandler](#addcommandhandler)|コマンド ソース オブジェクトには、コマンド ハンドラーを追加します。|  
|[ICommandSource::AddCommandRangeHandler](#addcommandrangehandler)|コマンド ソース オブジェクトに一連のコマンド ハンドラーを追加します。|  
|[ICommandSource::AddCommandRangeUIHandler](#addcommandrangeuihandler)|コマンド ソース オブジェクトに一連のユーザー インターフェイス コマンド メッセージ ハンドラーを追加します。|  
|[ICommandSource::AddCommandUIHandler](#addcommandrangeuihandler)|コマンド ソース オブジェクトには、ユーザー インターフェイス コマンド メッセージのハンドラーを追加します。|  
|[ICommandSource::PostCommand](#postcommand)|処理されるまで待つことがなく、メッセージをポストします。|  
|[ICommandSource::RemoveCommandHandler](#removecommandhandler)|コマンド ソース オブジェクトから、コマンド ハンドラーを削除します。|  
|[ICommandSource::RemoveCommandRangeHandler](#removecommandrangehandler)|コマンド ソース オブジェクトから一連のコマンド ハンドラーを削除します。|  
|[ICommandSource::RemoveCommandRangeUIHandler](#removecommandrangeuihandler)|コマンド ソース オブジェクトからのユーザー インターフェイス コマンド メッセージ ハンドラーのグループを削除します。|  
|[ICommandSource::RemoveCommandUIHandler](#removecommandrangeuihandler)|コマンド ソース オブジェクトからのユーザー インターフェイス コマンド メッセージのハンドラーを削除します。|  
|[ICommandSource::SendCommand](#sendcommand)|メッセージを送信し、戻る前に処理されるまで待機します。|  
  
### <a name="remarks"></a>コメント  
 MFC の表示では、ユーザー コントロールをホストするときに[CWinFormsView クラス](../../mfc/reference/cwinformsview-class.md)ルート コマンドおよび更新コマンド UI メッセージをユーザー コントロールを MFC のコマンド (フレームのメニュー項目やツール バー ボタンなど) を処理できるようにします。 実装することによって[関数インターフェイス](../../mfc/reference/icommandtarget-interface.md)、ユーザー コントロールへの参照を提供する、`ICommandSource`オブジェクトです。  
  
 参照してください[方法: Windows フォーム コントロールへのコマンド ルーティングの追加](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)を使用する方法の例については`ICommandTarget`です。  
  
 Windows フォームの使用に関する詳細については、次を参照してください。 [MFC では、Windows フォーム ユーザー コントロールを使用して](../../dotnet/using-a-windows-form-user-control-in-mfc.md)します。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxwinforms.h (アセンブリ atlmfc\lib\mfcmifc80.dll で定義)  
  
## <a name="addcommandhandler"></a>ICommandSource::AddCommandHandler
コマンド ソース オブジェクトには、コマンド ハンドラーを追加します。
```
void AddCommandHandler(
    unsigned int cmdID,
    CommandHandler^ cmdHandler);
```

### <a name="parameters"></a>パラメーター  
`cmdID`  
コマンド ID。  
`cmdHandler`  
コマンドのハンドラー メソッドへのハンドル。

### <a name="remarks"></a>コメント
このメソッドでは、コマンド ハンドラー cmdHandler をコマンド ソース オブジェクトに追加し、cmdID ハンドラーにマップします。
参照してください[方法: Windows フォーム コントロールへのコマンド ルーティングの追加](https://msdn.microsoft.com/library/y33d8624.aspx)AddCommandHandler を使用する方法の例についてです。

## <a name="addcommandrangehandler"></a>ICommandSource::AddCommandRangeHandler

コマンド ソース オブジェクトに一連のコマンド ハンドラーを追加します。
```
void AddCommandRangeHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax,
    CommandHandler^ cmdHandler);
```
### <a name="parameters"></a>パラメーター  
`cmdIDMin`  
コマンド ID 範囲の開始インデックス。
`cmdIDMax`  
コマンド ID 範囲の終了インデックス。
`cmdHandler`  
コマンドがマップされているメッセージのハンドラー メソッドへのハンドル。
### <a name="remarks"></a>コメント
このメソッドは、コマンド Id の連続する範囲を&1; つのメッセージ ハンドラーにマップし、コマンド ソース オブジェクトに追加します。 1 つのメソッドを使用して関連するボタンのグループを処理するために使用されます。

## <a name="addcommandrangeuihandler"></a>ICommandSource::AddCommandRangeUIHandler
コマンド ソース オブジェクトに一連のユーザー インターフェイス コマンド メッセージ ハンドラーを追加します。
```
void AddCommandRangeUIHandler(
    unsigned int cmdIDMin, 
    unsigned int cmdIDMax, 
    CommandUIHandler^ cmdUIHandler);
```
### <a name="parameters"></a>パラメーター  
`cmdIDMin`  
コマンド ID 範囲の開始インデックス。
`cmdIDMax`  
コマンド ID 範囲の終了インデックス。
`cmdHandler`  
コマンドがマップされているメッセージのハンドラー メソッドへのハンドル。

### <a name="remarks"></a>コメント
このメソッドは、コマンド Id の連続する範囲を&1; 人のユーザー インターフェイス コマンド メッセージのハンドラーにマップし、コマンド ソース オブジェクトに追加します。 1 つのメソッドを使用して関連するボタンのグループを処理するために使用されます。

## <a name="addcommanduihandler"></a>ICommandSource::AddCommandUIHandler
コマンド ソース オブジェクトには、ユーザー インターフェイス コマンド メッセージのハンドラーを追加します。
```
void AddCommandUIHandler(
    unsigned int cmdID, 
    CommandUIHandler^ cmdUIHandler);
```
### <a name="parameters"></a>パラメーター
`cmdID`  
コマンド ID。  
`cmdUIHandler`  
ユーザー インターフェイス コマンド メッセージのハンドラー メソッドへのハンドル。

### <a name="remarks"></a>コメント
このメソッドは、コマンド ソース オブジェクトにユーザー インターフェイス コマンド メッセージ ハンドラー cmdHandler を追加し、ハンドラーを cmdID にマップします。

## <a name="postcommand"></a>ICommandSource::PostCommand
処理されるまで待つことがなく、メッセージをポストします。
```
void PostCommand(unsigned int command);
```
### <a name="parameters"></a>パラメーター
`command`  
投稿するメッセージのコマンド ID。
### <a name="remarks"></a>コメント
このメソッドは、コマンドで指定した ID に割り当てられたメッセージを非同期的にポストします。 ウィンドウのメッセージ キューにメッセージを配置する CWnd::PostMessage を呼び出すし、メッセージの処理に対応するウィンドウを待たずに戻ります。


## <a name="removecommandhandler"></a>ICommandSource::RemoveCommandHandler
コマンド ソース オブジェクトから、コマンド ハンドラーを削除します。
```
void RemoveCommandHandler(unsigned int cmdID);
```
### <a name="parameters"></a>パラメーター
`cmdID`  
コマンド ID。
### <a name="remarks"></a>コメント
このメソッドは、コマンド ソース オブジェクトから cmdID に割り当てられたコマンド ハンドラーを削除します。


## <a name="removecommandrangecommandhandler"></a>ICommandSource::RemoveCommandRangeHandler 
コマンド ソース オブジェクトから一連のコマンド ハンドラーを削除します。
```
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax);
```
### <a name="parameters"></a>パラメーター
`cmdIDMin`  
コマンド ID 範囲の開始インデックス。
`cmdIDMax`  
コマンド ID 範囲の終了インデックス。
### <a name="remarks"></a>コメント
このメソッドは、一連のコマンド ソース オブジェクトから cmdIDMin および cmdIDMax で指定されたコマンド Id に割り当て、メッセージのハンドラーを削除します。

## <a name="removecommandrangeuihandler"></a>ICommandSource::RemoveCommandRangeUIHandler 
コマンド ソース オブジェクトからのユーザー インターフェイス コマンド メッセージ ハンドラーのグループを削除します。
```
void RemoveCommandRangeUIHandler(
    unsigned int cmdIDMin,
    unsigned int cmdIDMax);
```
### <a name="parameters"></a>パラメーター
`cmdIDMin`  
コマンド ID 範囲の開始インデックス。
`cmdIDMax`  
コマンド ID 範囲の終了インデックス。
### <a name="remarks"></a>コメント
このメソッドは、一連のコマンド ソース オブジェクトから cmdIDMin および cmdIDMax で指定されたコマンド Id に割り当て、ユーザー インターフェイス コマンド メッセージ ハンドラーを削除します。

## <a name="removecommanduihandler"></a>ICommandSource::RemoveCommandUIHandler 
コマンド ソース オブジェクトからのユーザー インターフェイス コマンド メッセージのハンドラーを削除します。
```
void RemoveCommandUIHandler(unsigned int cmdID);
```
### <a name="parameters"></a>パラメーター
`cmdID`  
コマンド ID。
### <a name="remarks"></a>コメント
このメソッドは、コマンド ソース オブジェクトから cmdID に割り当てられたユーザー インターフェイス コマンド メッセージ ハンドラーを削除します。

## <a name="sendcommand"></a>ICommandSource::SendCommand 
メッセージを送信し、戻る前に処理されるまで待機します。
```
void SendCommand(unsigned int command);
```
### <a name="parameters"></a>パラメーター
`command`  
送信されるメッセージのコマンド ID。
### <a name="remarks"></a>コメント
このメソッドは、コマンドで指定した ID に割り当てられたメッセージを同期的に送信します。 ウィンドウのメッセージ キューにメッセージを配置する CWnd::SendMessage を呼び出すし、そのウィンドウ プロシージャが返す前にメッセージを処理するまで待機します。
## <a name="see-also"></a>関連項目  
 [方法: コマンドの追加にルーティングする Windows フォーム コントロール](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)   
 [関数のインターフェイス](../../mfc/reference/icommandtarget-interface.md)

