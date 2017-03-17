---
title: "CDaoRecordView クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDaoRecordView
- AFXDAO/CDaoRecordView
- AFXDAO/CDaoRecordView::CDaoRecordView
- AFXDAO/CDaoRecordView::IsOnFirstRecord
- AFXDAO/CDaoRecordView::IsOnLastRecord
- AFXDAO/CDaoRecordView::OnGetRecordset
- AFXDAO/CDaoRecordView::OnMove
dev_langs:
- C++
helpviewer_keywords:
- CDaoRecordView class
- data-bound controls [C++], DAO controls
- data binding [C++], DAO views
- bound controls [C++], displaying database data
- application wizards [C++], creating record views
- controls [MFC], data binding
ms.assetid: 5aa7d0e2-bd05-413e-b216-80c404ce18ac
caps.latest.revision: 23
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
ms.openlocfilehash: 11aa318e84e89835ceb710725590f3c3e6387fcd
ms.lasthandoff: 02/24/2017

---
# <a name="cdaorecordview-class"></a>CDaoRecordView クラス
コントロール内にデータベース レコードを表示するビューです。  
  
## <a name="syntax"></a>構文  
  
```  
class AFX_NOVTABLE CDaoRecordView : public CFormView  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[指定して](#cdaorecordview)|`CDaoRecordView` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDaoRecordView::IsOnFirstRecord](#isonfirstrecord)|現在のレコードが関連するレコード セットの最初のレコードの場合は&0; 以外を返します。|  
|[CDaoRecordView::IsOnLastRecord](#isonlastrecord)|現在のレコードが関連するレコード セットの最後のレコードの場合は&0; 以外を返します。|  
|[CDaoRecordView::OnGetRecordset](#ongetrecordset)|派生したクラスのオブジェクトへのポインターを返します`CDaoRecordset`します。 ClassWizard では、この関数を上書きし、必要な場合、レコード セットを作成します。|  
|[CDaoRecordView::OnMove](#onmove)|現在のレコードを変更した場合、データ ソースで更新し、指定されたレコードに移動 (次、前に、最初のページまたは最後)。|  
  
## <a name="remarks"></a>コメント  
 ビューがフォーム ビューに直接接続、`CDaoRecordset`オブジェクトです。 ビューのダイアログ テンプレート リソースから作成され、のフィールドを表示、`CDaoRecordset`ダイアログ テンプレートのコントロール内のオブジェクト。 `CDaoRecordView`オブジェクト ダイアログ データ エクス (チェンジ DDX) および DAO レコード フィールド エクス (チェンジ DFX) を使用して、フォーム上のコントロールとレコード セットのフィールドの間のデータの移動を自動化します。 `CDaoRecordView`移動するための既定の実装を提供しても、最初次、前、または最後のレコードと現在の表示のレコードを更新するためのインターフェイスです。  
  
> [!NOTE]
>  DAO データベース クラスは、ODBC Open Database Connectivity () を基 MFC データベース クラスとは異なります。 DAO データベース クラスの名前では、"CDao"というプレフィックスが付いています。 DAO クラスで ODBC データ ソースにアクセスできます。Microsoft Jet データベース エンジンを使用するため、DAO クラスは一般に優れた機能を提供します。  
  
 レコード ビューを作成する最も一般的な方法は、アプリケーションのウィザードでです。 アプリケーション ウィザードでは、レコード ビュー クラスとスケルトンのスターター アプリケーションの一部として、関連するレコード セット クラスの両方を作成します。  
  
 1 つのフォームを単に必要がある場合は、アプリケーション ウィザードを使用が簡単です。 ClassWizard では、開発プロセスの後半で、レコード ビューを使用するかを判断することができます。 アプリケーション ウィザードを使用してレコード ビュー クラスを作成しない場合に、後で ClassWizard で作成できます。 レコード セット クラスの名前付けで詳細に制御が提供されるため、最も柔軟な方法は ClassWizard を使用してレコード ビューとレコード セットを個別に作成し、それらを接続するとします。H/です。CPP ファイルです。 この方法では、同じレコード セット クラスで複数のレコード ビューを持つこともできます。  
  
 メニュー (および必要に応じてツールバー) を簡単に、レコード ビューにレコード間を移動するエンドユーザーのためにアプリケーション ウィザードで作成の移行に関するリソース、最初次、前、または最後のレコードです。 ClassWizard でユーザーがレコード ビュー クラスを作成する場合は、エディターを作成するこれらのリソース自分でメニューとビットマップを使用する必要があります。  
  
 レコード間を移動するための既定の実装については、次を参照してください。`IsOnFirstRecord`と`IsOnLastRecord`」および「[レコード ビューを使用して](../../data/using-a-record-view-mfc-data-access.md)、両方に適用されます`CRecordView`と`CDaoRecordView`です。  
  
 `CDaoRecordView`レコード ビューは、ユーザー インターフェイスを更新できるようにはのレコード セット内のユーザーの位置を追跡します。 ユーザーがレコード セットの先頭または末尾に移動、レコード ビュー、ユーザー インターフェイス オブジェクトを無効になります: メニュー項目やツール バー ボタンなど — を移動するため同じ方向にさらにします。  
  
 宣言と、レコード ビューとレコード セット クラスを使用する方法の詳細についてを参照してください「の作成、レコード ビューのデザインと」記事[レコード ビュー](../../data/record-views-mfc-data-access.md)します。 レコード ビューの動作とその使用方法の詳細については、記事を参照してください。[レコード ビューを使用して](../../data/using-a-record-view-mfc-data-access.md)します。 上記で説明したすべてのアーティクルが両方に適用`CRecordView`と`CDaoRecordView`です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 `CDaoRecordView`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  
  
##  <a name="cdaorecordview"></a>指定して  
 派生した型のオブジェクトを作成する場合`CDaoRecordView`、どちらの形式のビュー オブジェクトを初期化し、ビューの基になるダイアログ リソースの特定にコンス トラクターを呼び出します。  
  
```  
explicit CDaoRecordView(LPCTSTR lpszTemplateName);  
explicit CDaoRecordView(UINT nIDTemplate);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszTemplateName`  
 ダイアログ テンプレート リソースの名前を指定する null で終わる文字列が含まれています。  
  
 `nIDTemplate`  
 ダイアログ テンプレート リソースの ID 番号が含まれています。  
  
### <a name="remarks"></a>コメント  
 (コンス トラクターの引数として文字列を渡す) の名前または ID (符号なし整数の引数として渡します) か、リソースを識別できます。 リソースを使用して ID をお勧めします。  
  
> [!NOTE]
>  派生クラスでは、独自のコンス トラクターを指定する必要があります。 派生クラスのコンス トラクターで、コンス トラクターを呼び出します`CDaoRecordView::CDaoRecordView`リソース名または ID を引数として使用します。  
  
 **CDaoRecordView::OnInitialUpdate**呼び出し`CWnd::UpdateData`、どの呼び出し`CWnd::DoDataExchange`します。 この最初の呼び出し`DoDataExchange`接続`CDaoRecordView`(間接的に) に制御`CDaoRecordset`ClassWizard で作成されたデータ メンバーのフィールドです。 これらのデータ メンバーは、基本クラスを呼び出した後まで使用できません**CFormView::OnInitialUpdate**メンバー関数。  
  
> [!NOTE]
>  ClassWizard を使用する場合、ウィザードで定義、`enum`値`CDaoRecordView::IDD`コンス トラクターの一覧でメンバーの初期化を使用してクラスの宣言です。  
  
 [!code-cpp[NVC_MFCDatabase&#35;](../../mfc/codesnippet/cpp/cdaorecordview-class_1.cpp)]  
  
##  <a name="isonfirstrecord"></a>CDaoRecordView::IsOnFirstRecord  
 このメンバー関数を呼び出して現在のレコードがレコード ビューに関連付けられているレコード セット オブジェクト内の最初のレコードであるかどうかを確認します。  
  
```  
BOOL IsOnFirstRecord();
```  
  
### <a name="return-value"></a>戻り値  
 現在のレコードがレコード セットの最初のレコードの場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数は ClassWizard で作成されたコマンド更新ハンドラーの既定の実装を記述するために便利です。  
  
 ユーザーは、最初のレコードに移動、framework 無効になりますが、ユーザー インターフェイス オブジェクト (メニュー項目やツール バー ボタンなど) がある場合、最初のページと前のレコードに移動するためです。  
  
##  <a name="isonlastrecord"></a>CDaoRecordView::IsOnLastRecord  
 このメンバー関数を呼び出して現在のレコードがレコード ビューに関連付けられているレコード セット オブジェクトの最後のレコードであるかどうかを確認します。  
  
```  
BOOL IsOnLastRecord();
```  
  
### <a name="return-value"></a>戻り値  
 現在のレコードがレコード セットの最後のレコードの場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数は、既定の実装を ClassWizard がレコード間を移動するためのユーザー インターフェイスをサポートするために書き込むコマンド更新ハンドラーを記述するために便利です。  
  
> [!CAUTION]
>  この関数の結果は信頼性がする点を除いて、ビューがそれ以降、ユーザーに移動されるまで、レコード セットの末尾を検出できません。 ユーザーは、レコード ビューは次または最後のレコードに移動するためのユーザー インターフェイス オブジェクトを無効にする必要があることを確認する前に、最後のレコードを超える移動する必要があります。 最後のレコードの後ろに移動し、バックアップの最後に移動レコード (またはその前に)、レコード ビューは、レコード セット内のユーザーの位置を追跡し、ユーザー インターフェイス オブジェクトを正しく無効にできます。  
  
##  <a name="ongetrecordset"></a>CDaoRecordView::OnGetRecordset  
 ポインターを返す、 `CDaoRecordset`-レコード ビューに関連付けられているオブジェクトを派生します。  
  
```  
virtual CDaoRecordset* OnGetRecordset() = 0;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 `CDaoRecordset`-派生オブジェクトにオブジェクトが正常に作成された、それ以外の場合、 **NULL**ポインター。  
  
### <a name="remarks"></a>コメント  
 作成またはレコード セット オブジェクトを取得してにポインターを返すには、この関数をオーバーライドする必要があります。 ClassWizard 使用して、レコード ビュー クラスを宣言する場合の既定のオーバーライドが書き込まれます。 ClassWizard の既定の実装では、いずれかが存在する場合は、レコード ビューに格納されているレコード セットのポインターを返します。 ClassWizard でユーザーが指定されている場合は、型のレコード セット オブジェクトを作成、その**開く**メンバーは、テーブルを開くか、クエリを実行する関数し、オブジェクトへのポインターを返します。  
  
 詳細と例については、記事を参照して[レコード ビュー: レコード ビューを使用して](../../data/using-a-record-view-mfc-data-access.md)します。  
  
##  <a name="onmove"></a>CDaoRecordView::OnMove  
 このメンバー関数を呼び出して、レコード セット内の別のレコードに移動し、レコード ビューのコントロールにそのフィールドを表示します。  
  
```  
virtual BOOL OnMove(UINT nIDMoveCommand);
```  
  
### <a name="parameters"></a>パラメーター  
 `nIDMoveCommand`  
 次の標準コマンド ID 値のいずれかです。  
  
- `ID_RECORD_FIRST`レコード セットの最初のレコードに移動します。  
  
- `ID_RECORD_LAST`レコード セットの最後のレコードに移動します。  
  
- `ID_RECORD_NEXT`レコード セットの次のレコードに移動します。  
  
- `ID_RECORD_PREV`レコード セットの前のレコードに移動します。  
  
### <a name="return-value"></a>戻り値  
 移動が成功した場合は 0 以外。移動要求が拒否された場合は、それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 既定の実装の適切な移動メンバー関数の呼び出し、`CDaoRecordset`レコード ビューに関連付けられているオブジェクト。  
  
 既定では、`OnMove`ユーザーを使用すると、レコード ビューに変更された場合は、データ ソースの現在のレコードを更新します。  
  
 アプリケーション ウィザードでは、最初のレコード、最後のレコード、次のレコード、および前のレコードのメニュー項目を含むメニュー リソースを作成します。 [ツールバー] オプションを選択した場合、アプリケーション ウィザードもこれらのコマンドに対応するボタンをツールバーを作成します。  
  
 過去のレコード セットの最後のレコードを移動する場合、レコード ビューは最後のレコードが表示されます。 最初のレコードを超えて後方移動した場合、レコード ビューは最初のレコードが表示されます。  
  
> [!CAUTION]
>  呼び出す`OnMove`レコード セットにレコードが存在しない場合は例外をスローします。 適切なユーザー インターフェイス更新ハンドラー関数を呼び出す: **OnUpdateRecordFirst**、 **OnUpdateRecordLast**、 **OnUpdateRecordNext**、または**OnUpdateRecordPrev** —、対応するすべてのレコードをレコード セットが存在するかどうかを判断する操作に移動します。  
  
## <a name="see-also"></a>関連項目  
 [CFormView クラス](../../mfc/reference/cformview-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDaoRecordset クラス](../../mfc/reference/cdaorecordset-class.md)   
 [どちらのクラス](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoQueryDef クラス](../../mfc/reference/cdaoquerydef-class.md)   
 [CDaoDatabase クラス](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoWorkspace クラス](../../mfc/reference/cdaoworkspace-class.md)   
 [CFormView クラス](../../mfc/reference/cformview-class.md)

