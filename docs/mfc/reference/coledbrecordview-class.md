---
title: "COleDBRecordView クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDBRecordView
- AFXOLEDB/COleDBRecordView
- AFXOLEDB/COleDBRecordView::COleDBRecordView
- AFXOLEDB/COleDBRecordView::OnGetRowset
- AFXOLEDB/COleDBRecordView::OnMove
dev_langs:
- C++
helpviewer_keywords:
- MFC, OLE DB
- COleDBRecordView class
ms.assetid: 98612427-c4c9-4760-b7e1-85b17448add9
caps.latest.revision: 20
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
ms.openlocfilehash: 89b5cb175900d11854dcad03440a1ef0bfb8cff9
ms.lasthandoff: 02/24/2017

---
# <a name="coledbrecordview-class"></a>COleDBRecordView クラス
コントロール内にデータベース レコードを表示するビューです。  
  
## <a name="syntax"></a>構文  
  
```  
class COleDBRecordView : public CFormView  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleDBRecordView::COleDBRecordView](#coledbrecordview)|`COleDBRecordView` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleDBRecordView::OnGetRowset](#ongetrowset)|標準を返す`HRESULT`値。|  
|[COleDBRecordView::OnMove](#onmove)|データ ソースで (ダーティの場合) に現在のレコードを更新し、指定されたレコードに移動します (次、前に、最初のページまたは最後)。|  
  
## <a name="remarks"></a>コメント  
 ビューがフォーム ビューに直接接続、`CRowset`オブジェクトです。 ビューのダイアログ テンプレート リソースから作成され、のフィールドを表示、`CRowset`ダイアログ テンプレートのコントロール内のオブジェクト。 `COleDBRecordView`オブジェクトは、ダイアログ データ エクス チェンジ (DDX) を使用し、ナビゲーションの機能に組み込まれて`CRowset`フォーム上のコントロールと、行セットのフィールド間のデータ移動を自動化します。 `COleDBRecordView`移動するための既定の実装を提供しても、最初次、前、または最後のレコードとビューの現在のレコードを更新するためのインターフェイスです。  
  
 DDX 関数を使用する**COleDbRecordView**データベース レコード セットから直接データを取得し、ダイアログ コントロールに表示します。 使用する必要があります、 **DDX_\* **メソッド (など`DDX_Text`) ではなく、 **DDX_Field\* **関数 (よう`DDX_FieldText`) と**COleDbRecordView**します。 `DDX_FieldText`は動作しません**COleDbRecordView**ため`DDX_FieldText`型の追加の引数を取る**CRecordset\* ** (の`CRecordView`) または**CDaoRecordset\* ** (の`CDaoRecordView`)。  
  
> [!NOTE]
>  OLE DB コンシューマー テンプレート クラスではなく、データ アクセス オブジェクト (DAO) クラスで作業している場合は、クラスを使用して[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)代わりにします。 詳細については、記事を参照してください。[の概要: データベース プログラミング](../../data/data-access-programming-mfc-atl.md)します。  
  
 `COleDBRecordView`レコード ビューは、ユーザー インターフェイスを更新できるようにはの行セット内のユーザーの位置を追跡します。 ユーザーは、行セットの先頭または末尾に移動、レコード ビュー、ユーザー インターフェイス オブジェクトの â € を無効になる"メニュー項目またはツールバー ボタン â € など"を移動するため同じ方向にさらにします。  
  
 行セット クラスの詳細については、次を参照してください。、[を使用して OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)記事です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 `COleDBRecordView`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxoledb.h  
  
##  <a name="coledbrecordview"></a>COleDBRecordView::COleDBRecordView  
 `COleDBRecordView` オブジェクトを構築します。  
  
```  
COleDBRecordView(LPCTSTR lpszTemplateName);  
COleDBRecordView(UINT nIDTemplate);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszTemplateName`  
 ダイアログ テンプレート リソースの名前を表す null で終わる文字列が含まれています。  
  
 `nIDTemplate`  
 ダイアログ テンプレート リソースの ID 番号が含まれています。  
  
### <a name="remarks"></a>コメント  
 派生した型のオブジェクトを作成する場合`COleDBRecordView`、ビュー オブジェクトを作成し、ビューの基になるダイアログ リソースを識別するコンス トラクターの&1; つを呼び出します。 (コンス トラクターの引数として文字列を渡す) の名前または ID (パスの引数として符号なし整数) では、リソースを識別できます。  
  
> [!NOTE]
>  派生クラス*必要があります*独自のコンス トラクターを指定します。 コンス トラクターで、コンス トラクターを呼び出す`COleDBRecordView::COleDBRecordView`リソースの名前または ID を引数として使用します。  
  
##  <a name="ongetrowset"></a>COleDBRecordView::OnGetRowset  
 ハンドルを返します、 **CRowset<> </> ** 、レコード ビューに関連付けられているオブジェクト。  
  
```  
virtual CRowset<>* OnGetRowset(Â) = 0;  
 
```  
  
### <a name="return-value"></a>戻り値  
 標準の `HRESULT` 値。  
  
### <a name="remarks"></a>コメント  
 作成または行セット オブジェクトを取得してにハンドルを返すには、この関数をオーバーライドする必要があります。 ClassWizard 使用して、レコード ビュー クラスを宣言する場合の既定のオーバーライドが書き込まれます。 ClassWizard の既定の実装では、1 つが存在する場合は、レコード ビューに格納されている行セット ハンドルを返します。 ClassWizard でユーザーが指定されている場合は、型の行セット オブジェクトを構築、その**開く**メンバーは、テーブルを開くか、クエリを実行する関数し、オブジェクトにハンドルが返されます。  
  
> [!NOTE]
>  MFC 7.0 以前`OnGetRowset`へのポインターを返す`CRowset`します。 呼び出すコードを使用していれば`OnGetRowset`、化されたクラスに戻り値の型を変更する必要がある**CRowset<>**します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDatabase #&38;](../../mfc/codesnippet/cpp/coledbrecordview-class_1.cpp)]  
  
 詳細と例については、記事を参照して[レコード ビュー: レコード ビューを使用して](../../data/using-a-record-view-mfc-data-access.md)します。  
  
##  <a name="onmove"></a>COleDBRecordView::OnMove  
 行セットと表示内のレコードに移動、レコードのコントロールでは、そのフィールドを表示します。  
  
```  
virtual BOOL OnMove(UINT nIDMoveCommand);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDMoveCommand`  
 次の標準コマンド ID 値のいずれかです。  
  
- `ID_RECORD_FIRST`--を移動、レコード セット内の最初のレコードに本です。  
  
- `ID_RECORD_LAST`Â Â 本は、レコード セットのレコードで移動最後にします。  
  
- `ID_RECORD_NEXT`--を移動、レコード セットの次のレコードに本です。  
  
- `ID_RECORD_PREV`---、前のレコードに移動、レコード セット内です。  
  
### <a name="return-value"></a>戻り値  
 移動が成功した場合は 0 以外。移動要求が拒否された場合は、それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 既定の実装を呼び出す、適切な**移動**のメンバー関数、`CRowset`レコード ビューに関連付けられているオブジェクト。  
  
 既定では、`OnMove`ユーザーを使用すると、レコード ビューに変更された場合は、データ ソースの現在のレコードを更新します。  
  
 アプリケーション ウィザードでは、最初のレコード、最後のレコード、次のレコード、および前のレコードのメニュー項目を含むメニュー リソースを作成します。 ドッキング可能ツールバー オプションを選択した場合、アプリケーション ウィザードもこれらのコマンドに対応するボタンをツールバーを作成します。  
  
 過去のレコード セットの最後のレコードを移動する場合、レコード ビューは最後のレコードが表示されます。 最初のレコードを超えて後方移動した場合、レコード ビューは最初のレコードが表示されます。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)




