---
title: "CJumpList クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CJumpList
- AFXADV/CJumpList
- AFXADV/CJumpList::CJumpList
- AFXADV/CJumpList::AbortList
- AFXADV/CJumpList::AddDestination
- AFXADV/CJumpList::AddKnownCategory
- AFXADV/CJumpList::AddTask
- AFXADV/CJumpList::AddTasks
- AFXADV/CJumpList::AddTaskSeparator
- AFXADV/CJumpList::ClearAll
- AFXADV/CJumpList::ClearAllDestinations
- AFXADV/CJumpList::CommitList
- AFXADV/CJumpList::GetDestinationList
- AFXADV/CJumpList::GetMaxSlots
- AFXADV/CJumpList::GetRemovedItems
- AFXADV/CJumpList::InitializeList
- AFXADV/CJumpList::SetAppID
dev_langs:
- C++
helpviewer_keywords:
- CJumpList class
ms.assetid: d364d27e-f512-4b12-9872-c2a17c78ab1f
caps.latest.revision: 15
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: b3662bd00f7c757df3a77f5920c48389bbd749fb
ms.lasthandoff: 02/24/2017

---
# <a name="cjumplist-class"></a>CJumpList クラス
A`CJumpList`タスク バーのアイコンを右クリックしたときに表示されるショートカットの一覧を示します。  
  
## <a name="syntax"></a>構文  
  
```  
class CJumpList;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CJumpList::CJumpList](#cjumplist)|`CJumpList` オブジェクトを構築します。|  
|[CJumpList:: ~ CJumpList](#cjumplist__~cjumplist)|`CJumpList` オブジェクトを破棄します。|  
  
|名前|説明|  
|----------|-----------------|  
|[CJumpList::AbortList](#abortlist)|コミットしなくてもリスト構築トランザクションを中止します。|  
|[CJumpList::AddDestination](#adddestination)|オーバーロードされます。 変換先を一覧に追加します。|  
|[CJumpList::AddKnownCategory](#addknowncategory)|既知のカテゴリを一覧に追加します。|  
|[CJumpList::AddTask](#addtask)|オーバーロードされます。 正規のタスク カテゴリに項目を追加します。|  
|[CJumpList::AddTasks](#addtasks)|正規のタスク カテゴリに項目を追加します。|  
|[CJumpList::AddTaskSeparator](#addtaskseparator)|タスク間の区切り記号を追加します。|  
|[CJumpList::ClearAll](#clearall)|すべてのタスクとの現在のインスタンスに追加された変換先を削除`CJumpList`これまでです。|  
|[CJumpList::ClearAllDestinations](#clearalldestinations)|現在のインスタンスに追加されたすべての送信先を削除`CJumpList`これまでです。|  
|[CJumpList::CommitList](#commitlist)|リスト生成トランザクションを終了し、関連するストア (ここではレジストリです。) に報告されたリストをコミット|  
|[CJumpList::GetDestinationList](#getdestinationlist)|宛先一覧へのインターフェイス ポインターを取得します。|  
|[CJumpList::GetMaxSlots](#getmaxslots)|呼び出し元のアプリケーションの保存先のメニューで表示できるカテゴリ ヘッダーを含む項目の最大数を取得します。|  
|[CJumpList::GetRemovedItems](#getremoveditems)|表す項目の配列を返しますでは、変換先を削除します。|  
|[CJumpList::InitializeList](#initializelist)|リスト生成トランザクションを開始します。|  
|[CJumpList::SetAppID](#setappid)|構築される一覧については、アプリケーション ユーザーのモデル ID を設定します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CJumpList](../../mfc/reference/cjumplist-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxadv.h  
  
##  <a name="_dtorcjumplist"></a>CJumpList:: ~ CJumpList  
 `CJumpList` オブジェクトを破棄します。  
  
```  
~CJumpList();
```  
  
##  <a name="abortlist"></a>CJumpList::AbortList  
 コミットしなくてもリスト構築トランザクションを中止します。  
  
```  
void AbortList();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドを呼び出して破棄すると同じ効果は`CJumpList`呼び出さずに`CommitList`します。  
  
##  <a name="adddestination"></a>CJumpList::AddDestination  
 変換先を一覧に追加します。  
  
```  
BOOL AddDestination(
    LPCTSTR lpcszCategoryName,  
    LPCTSTR strDestinationPath);

 
BOOL AddDestination(
    LPCTSTR strCategoryName,  
    IShellItem* pShellItem);

 
BOOL AddDestination(
    LPCTSTR strCategoryName,  
    IShellLink* pShellLink);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpcszCategoryName`  
 カテゴリ名を指定します。 指定されたカテゴリが存在しない場合は作成されます。  
  
 `strDestinationPath`  
 コピー先ファイルへのパスを指定します。  
  
 `strCategoryName`  
 カテゴリ名を指定します。 指定されたカテゴリが存在しない場合は作成されます。  
  
 `pShellItem`  
 追加する先を表すシェル項目を指定します。  
  
 `pShellLink`  
 追加する先を表すシェル リンクを指定します。  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
 インスタンス`CJumpList`追加の変換先を内部的に蓄積されでそれらをコミット`CommitList`します。  
  
##  <a name="addknowncategory"></a>CJumpList::AddKnownCategory  
 既知のカテゴリを一覧に追加します。  
  
```  
BOOL AddKnownCategory(KNOWNDESTCATEGORY category);
```  
  
### <a name="parameters"></a>パラメーター  
 `category`  
 既知のカテゴリの種類を指定します。 いずれかになります`KDC_RECENT`、または`KDC_KNOWN`です。  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
 既知のカテゴリは、利用頻度および最近使用したファイル カテゴリを使用するアプリケーションごとに私たちが自動的に計算する`SHAddToRecentDocs`(または直接これを使用しないように、シェルを使用すると一部のシナリオで、アプリケーションの代わりに呼び出しが)。  
  
##  <a name="addtask"></a>CJumpList::AddTask  
 正規のタスク カテゴリに項目を追加します。  
  
```  
BOOL AddTask(
    LPCTSTR strTargetExecutablePath,  
    LPCTSTR strCommandLineArgs,  
    LPCTSTR strTitle,  
    LPCTSTR strIconLocation,  
    int iIconIndex);  
  
BOOL AddTask(IShellLink* pShellLink);
```  
  
### <a name="parameters"></a>パラメーター  
 `strTargetExecutablePath`  
 タスクのターゲット パスを指定します。  
  
 `strCommandLineArgs`  
 StrTargetExecutablePath で指定された実行可能ファイルのコマンドライン引数を指定します。  
  
 `strTitle`  
 送信先リストに表示されるタスク名。  
  
 `strIconLocation`  
 タイトルの送信先リストに表示されるアイコンの場所です。  
  
 `iIconIndex`  
 アイコンのインデックス。  
  
 `pShellLink`  
 追加するタスクを表すシェル リンクします。  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
 インスタンス`CJumpList`中に、ターゲット リストに追加して指定したタスクの累積`CommitList`します。 タスク項目は、アプリケーションの保存先のメニューの下部にあるカテゴリに表示されます。 このカテゴリが優先されるその他のすべてのカテゴリの UI でいっぱいになったとき。  
  
##  <a name="addtasks"></a>CJumpList::AddTasks  
 正規のタスク カテゴリに項目を追加します。  
  
```  
BOOL AddTasks(IObjectArray* pObjectCollection);
```  
  
### <a name="parameters"></a>パラメーター  
 `pObjectCollection`  
 追加するタスクのコレクション。  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
 CJumpList のインスタンスを選択し、指定したタスクの累積中に、ターゲット リストに追加`CommitList`します。 タスク項目は、アプリケーションの保存先のメニューの下部にあるカテゴリに表示されます。 このカテゴリが優先されるその他のすべてのカテゴリの UI でいっぱいになったとき。  
  
##  <a name="addtaskseparator"></a>CJumpList::AddTaskSeparator  
 タスク間の区切り記号を追加します。  
  
```  
BOOL AddTaskSeparator();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合は 0 以外の場合は、0 です。  
  
##  <a name="cjumplist"></a>CJumpList::CJumpList  
 `CJumpList` オブジェクトを構築します。  
  
```  
CJumpList(BOOL bAutoCommit = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bAutoCommit`  
 このパラメーターが FALSE の場合、リストがデストラクターで自動的にコミットされません。  
  
##  <a name="clearall"></a>CJumpList::ClearAll  
 すべてのタスクとの現在のインスタンスに追加された変換先を削除`CJumpList`これまでです。  
  
```  
void ClearAll();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドをクリアし、すべてのデータとの内部インターフェイスを解放します。  
  
##  <a name="clearalldestinations"></a>CJumpList::ClearAllDestinations  
 これまで CJumpList の現在のインスタンスに追加されたすべての送信先を削除します。  
  
```  
void ClearAllDestinations();
```  
  
### <a name="remarks"></a>コメント  
 変換先 ボックスの一覧のビルドの現在のセッションでこれまでは追加されて、その他の送信先を再度追加するすべての送信先を削除する必要がある場合は、この関数を呼び出します。 場合、内部`ICustomDestinationList`されましたが、初期化が中断して有効です。  
  
##  <a name="commitlist"></a>CJumpList::CommitList  
 リスト構築トランザクションを終了し、関連するストア (ここではレジストリ) に報告されたリストをコミットします。  
  
```  
BOOL CommitList();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
 コミットはアトミックです。 コミットに失敗した場合、エラーが返されます。  `CommitList`が呼び出されると、現在削除された項目の一覧をクリーンアップします。 このメソッドを呼び出すオブジェクトをリセットします ボックスの一覧作成のアクティブなトランザクションがあるないようにします。 リストを更新する`BeginList`もう一度呼び出す必要があります。  
  
##  <a name="getdestinationlist"></a>CJumpList::GetDestinationList  
 宛先一覧へのインターフェイス ポインターを取得します。  
  
```  
ICustomDestinationList* GetDestinationList();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
 ジャンプ リストは初期化されていないまたは、コミットまたは中止されましたが場合、返される値になります`NULL`します。  
  
##  <a name="getmaxslots"></a>CJumpList::GetMaxSlots  
 呼び出し元のアプリケーションの保存先のメニューで表示できるカテゴリ ヘッダーを含む項目の最大数を取得します。  
  
```  
UINT GetMaxSlots() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
 アプリケーションでは、さまざまな項目と組み合わせてこの値になるまでカテゴリ ヘッダーがレポートのみ可能性があります。 場合に呼び出す`AppendCategory`、 `AppendKnownCategory`、または`AddUserTasks`この数を超える、エラーが返されます。  
  
##  <a name="getremoveditems"></a>CJumpList::GetRemovedItems  
 表す項目の配列を返しますでは、変換先を削除します。  
  
```  
IObjectArray* GetRemovedItems();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
 削除された変換先は、ジャンプ リストの初期化中に取得されます。 新しいターゲット リストを生成するときに、最初に削除された一覧の列挙子によって返されるすべての項目の追跡データをオフにすると、削除された変換先リストを処理するアプリケーションが必要です。 アプリケーションが、アイテムを現在の呼び出しのトランザクションで削除されただけを提供しようとしています。 場合`BeginList`開始されると、その項目を再度追加したメソッドの呼び出しは失敗、アプリケーションが削除されたリストを考慮しことを確認します。  
  
##  <a name="initializelist"></a>CJumpList::InitializeList  
 リスト生成トランザクションを開始します。  
  
```  
BOOL InitializeList();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
 ポインターを取得する場合を除き、このメソッドを明示的に呼び出す必要はありません`ICustomDestinationList`を使用して`GetDestinationList`を使用して、使用可能なスロット数`GetMaxSlots`、またはを使用して削除された項目のリスト`GetRemovedItems`します。  
  
##  <a name="setappid"></a>CJumpList::SetAppID  
 構築される一覧については、アプリケーション ユーザーのモデル ID を設定します。  
  
```  
void SetAppID(LPCTSTR strAppID);
```  
  
### <a name="parameters"></a>パラメーター  
 `strAppID`  
 アプリケーション ユーザーのモデル ID を指定する文字列  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

