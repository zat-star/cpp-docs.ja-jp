---
title: "CWordArray クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWordArray
dev_langs:
- C++
helpviewer_keywords:
- INT
- UINT
- indexed arrays
- arrays [C++], indexed
- WORD data type
- CWordArray class
ms.assetid: 2ba2c194-2c6c-40ff-9db4-e9dbe57e1f57
caps.latest.revision: 26
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
ms.openlocfilehash: cd6c26c49c6b46449ec6d7da42b9166d17d563da
ms.lasthandoff: 02/24/2017

---
# <a name="cwordarray-class"></a>CWordArray クラス
16 ビットのワードの配列をサポートします。  
  
## <a name="syntax"></a>構文  
  
```  
class CWordArray : public CObject  
```  
  
## <a name="members"></a>メンバー  
 メンバー関数は、`CWordArray`クラスのメンバー関数に似ています[CObArray](../../mfc/reference/cobarray-class.md)します。 メンバー関数については `CObArray` クラスの説明を参照してください。 表示されたら、 [CObject](../../mfc/reference/cobject-class.md)ポインター関数パラメーターまたは戻り値は、次のように置き換えてください。、 **WORD**します。  
  
 `CObject* CObArray::GetAt( int <nIndex> ) const;`  
  
 たとえば、次のように変換します。  
  
 `WORD CWordArray::GetAt( int <nIndex> ) const;`  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CObArray::CObArray](../../mfc/reference/cobarray-class.md#cobarray)|空の配列を生成します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CObArray::Add](../../mfc/reference/cobarray-class.md#add)|配列の末尾に要素を追加します。必要に応じて、配列を大きくします。|  
|[CObArray::Append](../../mfc/reference/cobarray-class.md#append)|配列に別の配列を追加します。必要に応じて、配列を大きくします。|  
|[CObArray::Copy](../../mfc/reference/cobarray-class.md#copy)|配列に別の配列をコピーします。必要に応じて、配列を大きくします。|  
|[CObArray::ElementAt](../../mfc/reference/cobarray-class.md#elementat)|配列内の要素ポインターへの一時的な参照を返します。|  
|[CObArray::FreeExtra](../../mfc/reference/cobarray-class.md#freeextra)|現在の上限を超えている未使用のメモリをすべて解放します。|  
|[CObArray::GetAt](../../mfc/reference/cobarray-class.md#getat)|指定されたインデックス位置にある値を返します。|  
|[CObArray::GetCount](../../mfc/reference/cobarray-class.md#getcount)|この配列内の要素の数を取得します。|  
|[CObArray::GetData](../../mfc/reference/cobarray-class.md#getdata)|配列内の要素へのアクセスを許可します。 できる**NULL**します。|  
|[CObArray::GetSize](../../mfc/reference/cobarray-class.md#getsize)|この配列内の要素の数を取得します。|  
|[CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound)|有効な最大のインデックスを返します。|  
|[CObArray::InsertAt](../../mfc/reference/cobarray-class.md#insertat)|指定されたインデックス位置に要素 (または別の配列内のすべての要素) を挿入します。|  
|[CObArray::IsEmpty](../../mfc/reference/cobarray-class.md#isempty)|配列が空かどうかを判別します。|  
|[CObArray::RemoveAll](../../mfc/reference/cobarray-class.md#removeall)|この配列からすべての要素を削除します。|  
|[CObArray::RemoveAt](../../mfc/reference/cobarray-class.md#removeat)|特定のインデックス位置にある要素を削除します。|  
|[CObArray::SetAt](../../mfc/reference/cobarray-class.md#setat)|指定されたインデックスの値を設定します。配列は大きくできません。|  
|[CObArray::SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow)|指定されたインデックスの値を設定します。必要に応じて、配列を大きくします。|  
|[CObArray::SetSize](../../mfc/reference/cobarray-class.md#setsize)|この配列に含まれる要素の数を設定します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CObArray::operator](../../mfc/reference/cobarray-class.md#operator_at)|指定されたインデックス位置にある要素を設定または取得します。|  
  
## <a name="remarks"></a>コメント  
 `CWordArray`組み込まれており、 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)マクロをシリアル化とその要素のダンプをサポートします。 単語の配列がオーバー ロードされた挿入演算子またはでアーカイブに格納されている場合、[指定](../../mfc/reference/cobject-class.md#serialize)メンバー関数の各要素は、逆に、シリアル化されます。  
  
> [!NOTE]
>  配列を使用する前に、`SetSize` を使用してそのサイズを設定し、メモリを割り当てます。 `SetSize` を使用しない場合、配列に要素を追加すると、配列の再割り当てとコピーが頻繁に発生します。 頻繁な再割り当てとコピーは非効率であり、メモリが断片化される可能性があります。  
  
 配列の個々 の要素をダンプする場合は、1 以上、ダンプ コンテキストの深さを設定する必要があります。  
  
 使用する方法について`CWordArray`、記事を参照して[コレクション](../../mfc/collections.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CWordArray`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcoll.h  
  
##  <a name="a-nameicommandsourceinterfacea--icommandsource-interface"></a><a name="icommandsource_interface"></a>ICommandSource インターフェイス  
 ユーザー コントロールにコマンド ソース オブジェクトから送信されたコマンドを管理します。  
  
```  
interface class ICommandSource  
```  
  
### <a name="remarks"></a>コメント  
 MFC の表示では、ユーザー コントロールをホストするときに[CWinFormsView クラス](../../mfc/reference/cwinformsview-class.md)ルート コマンドおよび更新コマンド UI メッセージをユーザー コントロールを MFC のコマンド (フレームのメニュー項目やツール バー ボタンなど) を処理できるようにします。 実装するを割り当てるユーザー コントロールへの参照、`ICommandSource`オブジェクトです。  
  
 参照してください[方法: Windows フォーム コントロールへのコマンド ルーティングの追加](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)を使用する方法の例については`ICommandTarget`です。  
  
 Windows フォームの使用に関する詳細については、次を参照してください。 [MFC では、Windows フォーム ユーザー コントロールを使用して](../../dotnet/using-a-windows-form-user-control-in-mfc.md)します。  
  
##  <a name="a-nameaddcommandhandlera--icommandsourceaddcommandhandler"></a><a name="addcommandhandler"></a>ICommandSource::AddCommandHandler  
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
 このメソッドは、コマンド ハンドラーを追加`cmdHandler`コマンド ソース オブジェクトにし、そのハンドラーに`cmdID`します。  
  
 参照してください[方法: Windows フォーム コントロールへのコマンド ルーティングの追加](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)を使用する方法の例については`AddCommandHandler`です。  
  
##  <a name="a-nameaddcommandrangehandlera--icommandsourceaddcommandrangehandler"></a><a name="addcommandrangehandler"></a>ICommandSource::AddCommandRangeHandler  
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
  
##  <a name="a-nameaddcommandrangeuihandlera--icommandsourceaddcommandrangeuihandler"></a><a name="addcommandrangeuihandler"></a>ICommandSource::AddCommandRangeUIHandler  
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
  
##  <a name="a-nameaddcommanduihandlera--icommandsourceaddcommanduihandler"></a><a name="addcommanduihandler"></a>ICommandSource::AddCommandUIHandler  
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
 このメソッドは、ユーザー インターフェイス コマンド メッセージ ハンドラーを追加`cmdHandler`コマンド ソース オブジェクトにし、そのハンドラーに`cmdID`します。  
  
##  <a name="a-namepostcommanda--icommandsourcepostcommand"></a><a name="postcommand"></a>ICommandSource::PostCommand  
 処理されるまで待つことがなく、メッセージをポストします。  
  
```  
void PostCommand(unsigned int command);
```  
  
### <a name="parameters"></a>パラメーター  
 `command`  
 投稿するメッセージのコマンド ID。  
  
### <a name="remarks"></a>コメント  
 このメソッドで指定した ID にマップされているメッセージを非同期的にポスト`command`します。 呼び出す[CWnd::PostMessage](../../mfc/reference/cwnd-class.md#postmessage)メッセージをメッセージの処理に対応するウィンドウを待たずに、ウィンドウのメッセージ キュー ラベルと返しますに入れます。  
  
##  <a name="a-nameremovecommandhandlera--icommandsourceremovecommandhandler"></a><a name="removecommandhandler"></a>ICommandSource::RemoveCommandHandler  
 コマンド ソース オブジェクトから、コマンド ハンドラーを削除します。  
  
```  
void RemoveCommandHandler(unsigned int cmdID);
```  
  
### <a name="parameters"></a>パラメーター  
 `cmdID`  
 コマンド ID。  
  
### <a name="remarks"></a>コメント  
 このメソッドにマップされているコマンド ハンドラーを削除する`cmdID`コマンド ソース オブジェクトからです。  
  
##  <a name="a-nameremovecommandrangehandlera--icommandsourceremovecommandrangehandler"></a><a name="removecommandrangehandler"></a>ICommandSource::RemoveCommandRangeHandler  
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
 このメソッドによって指定されたコマンド Id にマップされているメッセージ ハンドラーのグループを削除する`cmdIDMin`と`cmdIDMax`、コマンド ソース オブジェクトからです。  
  
##  <a name="a-nameremovecommandrangeuihandlera--icommandsourceremovecommandrangeuihandler"></a><a name="removecommandrangeuihandler"></a>ICommandSource::RemoveCommandRangeUIHandler  
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
 このメソッドによって指定されたコマンド Id にマップされている、ユーザー インターフェイス コマンド メッセージ ハンドラーのグループを削除する`cmdIDMin`と`cmdIDMax`、コマンド ソース オブジェクトからです。  
  
##  <a name="a-nameremovecommanduihandlera--icommandsourceremovecommanduihandler"></a><a name="removecommanduihandler"></a>ICommandSource::RemoveCommandUIHandler  
 コマンド ソース オブジェクトからのユーザー インターフェイス コマンド メッセージのハンドラーを削除します。  
  
```  
void RemoveCommandUIHandler(unsigned int cmdID);
```  
  
### <a name="parameters"></a>パラメーター  
 `cmdID`  
 コマンド ID。  
  
### <a name="remarks"></a>コメント  
 このメソッドにマップされているユーザー インターフェイス コマンド メッセージ ハンドラーを削除する`cmdID`コマンド ソース オブジェクトからです。  
  
##  <a name="a-namesendcommanda--icommandsourcesendcommand"></a><a name="sendcommand"></a>ICommandSource::SendCommand  
 メッセージを送信し、戻る前に処理されるまで待機します。  
  
```  
void SendCommand(unsigned int command);
```  
  
### <a name="parameters"></a>パラメーター  
 `command`  
 送信されるメッセージのコマンド ID。  
  
### <a name="remarks"></a>コメント  
 このメソッドで指定した ID に割り当てられたメッセージを同期的に送信する`command`です。 呼び出す[CWnd::SendMessage](../../mfc/reference/cwnd-class.md#sendmessage)そのウィンドウ プロシージャが返す前にメッセージを処理するまで、ウィンドウのメッセージ キュー ラベルと待機ではメッセージを入れます。  
  
##  <a name="a-nameicommandtargetinterfacea--icommandtarget-interface"></a><a name="icommandtarget_interface"></a>関数のインターフェイス  
 コマンド ソース オブジェクトからコマンドを受信するインターフェイスには、ユーザー コントロールを提供します。  
  
```  
interface class ICommandTarget  
```  
  
### <a name="remarks"></a>コメント  
 MFC の表示では、ユーザー コントロールをホストするときに[CWinFormsView](../../mfc/reference/cwinformsview-class.md)ルート コマンドおよび更新コマンド UI メッセージをユーザー コントロールを MFC のコマンド (フレームのメニュー項目やツール バー ボタンなど) を処理できるようにします。 実装することによって`ICommandTarget`、ユーザー コントロールにオブジェクトへの参照を提供します。  
  
 参照してください[方法: Windows フォーム コントロールへのコマンド ルーティングの追加](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)を使用する方法の例については`ICommandTarget`です。  
  
 Windows フォームの使用に関する詳細については、次を参照してください。 [MFC では、Windows フォーム ユーザー コントロールを使用して](../../dotnet/using-a-windows-form-user-control-in-mfc.md)します。  
  
##  <a name="a-nameinitializea--icommandtargetinitialize"></a><a name="initialize"></a>ICommandTarget::Initialize  
 コマンド ターゲット オブジェクトを初期化します。  
  
```  
void Initialize(ICommandSource^ cmdSource);
```  
  
### <a name="parameters"></a>パラメーター  
 `cmdSource`  
 コマンド ソース オブジェクトへのハンドル。  
  
### <a name="remarks"></a>コメント  
 MFC の表示では、ユーザー コントロールをホストするときに[CWinFormsView](../../mfc/reference/cwinformsview-class.md)ルート コマンドおよび更新コマンド UI メッセージをユーザー コントロールを MFC のコマンドを処理できるようにします。  
  
 このメソッドは、コマンドのターゲット オブジェクトを初期化し、指定したコマンドのソース オブジェクトに関連付けます`cmdSource`します。 ユーザー コントロール クラスの実装で呼び出す必要があります。 初期化でする必要がありますコマンド ハンドラーが登録されたコマンド ソース オブジェクトを呼び出して[ICommandSource::AddCommandHandler](../../mfc/reference/icommandsource-interface.md)で、`Initialize`実装します。 参照してください[方法: Windows フォーム コントロールへのコマンド ルーティングの追加](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)を使用する方法の例については`Initialize`これを行う。  
  
##  <a name="a-nameicommanduiinterfacea--icommandui-interface"></a><a name="icommandui_interface"></a>ICommandUI インターフェイス  
 ユーザー インターフェイスのコマンドを管理します。  
  
```  
interface class ICommandUI  
```  
  
### <a name="remarks"></a>コメント  
 このインターフェイスは、ユーザー インターフェイスのコマンドを管理するメソッドとプロパティを提供します。 `ICommandUI`ような[CCmdUI クラス](../../mfc/reference/ccmdui-class.md)する点を除いて、 `ICommandUI` MFC アプリケーションでは、.NET コンポーネントと相互運用するために使用します。  
  
 `ICommandUI`内で使用される、`ON_UPDATE_COMMAND_UI`ハンドラーの派生クラスです。 有効になっていると、各メニュー項目、メニューが表示されます (選択またはクリックする) がアプリケーションのユーザーをアクティブ化または無効にします。 各メニュー コマンドのターゲット実装することでこの情報を提供する、`ON_UPDATE_COMMAND_UI`ハンドラー。 アプリケーション内のコマンドのユーザー インターフェイス オブジェクトごとに、メッセージ マップ エントリと各ハンドラーに対する関数プロトタイプを作成するのに [プロパティ] ウィンドウを使用します。  
  
 方法の詳細については`ICommandUI`インターフェイスがコマンドのルーティングで使用しを参照してください[方法: Windows フォーム コントロールへのコマンド ルーティングの追加](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)します。  
  
 Windows フォームの使用に関する詳細については、次を参照してください。 [MFC では、Windows フォーム ユーザー コントロールを使用して](../../dotnet/using-a-windows-form-user-control-in-mfc.md)します。  
  
 MFC でのユーザー インターフェイスのコマンドを管理する方法の詳細については、次を参照してください。 [CCmdUI クラス](../../mfc/reference/ccmdui-class.md)します。  
  
##  <a name="a-namechecka--icommanduicheck"></a><a name="check"></a>ICommandUI::Check  
 このコマンドのユーザー インターフェイス項目を適切なチェックの状態に設定します。  
  
```  
property UICheckState Check;  
```  
  
### <a name="remarks"></a>コメント  
 このプロパティは、このコマンドのユーザー インターフェイス項目を適切なチェックの状態に設定します。 設定`Check`次の値にします。  
  
|用語|定義|  
|----------|----------------|  
|0|選択しない|  
|1|チェック|  
|2|不確定な設定します。|  
  
##  <a name="a-namecontinueroutinga--icommanduicontinuerouting"></a><a name="continuerouting"></a>ICommandUI::ContinueRouting  
 ハンドラーのチェーンに現在のメッセージを渡すようにコマンドのルーティング メカニズムに指示します。  
  
```  
void ContinueRouting();
```  
  
### <a name="remarks"></a>コメント  
 これは、高度なメンバー関数と組み合わせて使用する必要がありますが、 [ON_COMMAND_EX](http://msdn.microsoft.com/library/0bb49090-aee8-4203-87c8-dd001d3dd26e)を返すハンドラー`FALSE`します。 詳細については、テクニカル ノートを参照してください。 [TN006: メッセージ マップ](../../mfc/tn006-message-maps.md)します。  
  
##  <a name="a-nameenableda--icommanduienabled"></a><a name="enabled"></a>ICommandUI::Enabled  
 有効または、このコマンドのユーザー インターフェイス項目を無効にします。  
  
```  
property bool Enabled;  
```  
  
### <a name="remarks"></a>コメント  
 このプロパティでは、有効または、このコマンドのユーザー インターフェイス項目を無効にします。 設定`Enabled`に`TRUE`、項目を有効にする`FALSE`を無効にします。  
  
##  <a name="a-nameida--icommanduiid"></a><a name="id"></a>ICommandUI::ID  
 によって表されるユーザー インターフェイス オブジェクトの ID を取得、`ICommandUI`オブジェクトです。  
  
```  
property unsigned int ID;  
```  
  
### <a name="remarks"></a>コメント  
 このプロパティのメニュー項目のツール バー ボタンの ID (ハンドル) を取得またはによって表されるその他のユーザー インターフェイス オブジェクト、`ICommandUI`オブジェクトです。  
  
##  <a name="a-nameindexa--icommanduiindex"></a><a name="index"></a>ICommandUI::Index  
 によって表されるユーザー インターフェイス オブジェクトのインデックスを取得、`ICommandUI`オブジェクトです。  
  
```  
property unsigned int Index;  
```  
  
### <a name="remarks"></a>コメント  
 このプロパティは、ツール バー ボタン、メニュー項目のインデックス (ハンドル) を取得またはによって表されるその他のユーザー インターフェイス オブジェクト、`ICommandUI`オブジェクトです。  
  
##  <a name="a-nameradioa--icommanduiradio"></a><a name="radio"></a>ICommandUI::Radio  
 このコマンドのユーザー インターフェイス項目を適切なチェックの状態に設定します。  
  
```  
property bool Radio;  
```  
  
### <a name="remarks"></a>コメント  
 このプロパティは、このコマンドのユーザー インターフェイス項目を適切なチェックの状態に設定します。 設定`Radio`に`TRUE`アイテムを有効にするそれ以外の場合`FALSE`します。  
  
##  <a name="a-nametexta--icommanduitext"></a><a name="text"></a>ICommandUI::Text  
 このコマンドのユーザー インターフェイスの項目のテキストを設定します。  
  
```  
property String^ Text;  
```  
  
### <a name="remarks"></a>コメント  
 このプロパティは、このコマンドのユーザー インターフェイスの項目のテキストを設定します。 設定`Text`をテキスト文字列のハンドル。  
  
##  <a name="a-nameiviewinterfacea--iview-interface"></a><a name="iview_interface"></a>IView インターフェイス  
 さまざまなメソッド実装を[CWinFormsView](../../mfc/reference/cwinformsview-class.md)を使用してマネージ コントロールをビューの通知を送信します。  
  
```  
interface class IView  
```  
  
### <a name="remarks"></a>コメント  
 `IView`いくつかのメソッドを実装する`CWinFormsView`を使用してホストされるマネージ コントロールを一般的な通知の表示を転送します。 これらは[OnInitialUpdate](../../mfc/reference/iview-interface.md)、 [OnUpdate](../../mfc/reference/iview-interface.md)と[OnActivateView](../../mfc/reference/iview-interface.md)します。  
  
 `IView`ような[CView](../../mfc/reference/cview-class.md)が、管理ビューおよびコントロールでのみ使用されます。  
  
 Windows フォームの使用に関する詳細については、次を参照してください。 [MFC では、Windows フォーム ユーザー コントロールを使用して](../../dotnet/using-a-windows-form-user-control-in-mfc.md)します。  
  
##  <a name="a-nameonactivateviewa--iviewonactivateview"></a><a name="onactivateview"></a>IView::OnActivateView  
 ビューがアクティブ化または非アクティブ化されたときに、MFC によって呼び出されます。  
  
```  
void OnActivateView(bool activate);
```  
  
### <a name="parameters"></a>パラメーター  
 `activate`  
 表示されているかどうかを示しますがアクティブまたは非アクティブ化します。  
  
##  <a name="a-nameoninitialupdatea--iviewoninitialupdate"></a><a name="oninitialupdate"></a>IView::OnInitialUpdate  
 ドキュメントにビューを最初にアタッチ後、ビューが最初に表示される前に、フレームワークによって呼び出されます。  
  
```  
void OnInitialUpdate();
```  
  
##  <a name="a-nameonupdatea--iviewonupdate"></a><a name="onupdate"></a>IView::OnUpdate  
 ビューのドキュメントが変更された後に、MFC によって呼び出されます。  
  
```  
void OnUpdate();
```  
  
### <a name="remarks"></a>コメント  
 この関数は、ビューの変更を反映するように表示を更新できます。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプルの収集](../../visual-cpp-samples.md)   
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)




