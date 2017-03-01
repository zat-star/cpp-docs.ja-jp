---
title: "アプリケーションの制御 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- application control
ms.assetid: c1f69f15-e0fe-4515-9f36-d63d31869deb
caps.latest.revision: 12
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
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 81eb0bcdd8c9d154f62635e7f306cefcf7a15c1b
ms.lasthandoff: 02/24/2017

---
# <a name="application-control"></a>アプリケーションの制御
OLE には、アプリケーションとそのオブジェクトを十分に制御が必要です。 OLE システム Dll を起動してアプリケーションを自動的にリリースを運用環境と、オブジェクトの変更を調整具合できる必要があります。 このトピック内の関数は、それらの要件を満たしています。 、OLE システム Dll によって呼び出されるだけでなくこれらの関数をアプリケーションにもから呼び出すことがあります必要があります。  
  
### <a name="application-control"></a>アプリケーションの制御  
  
|||  
|-|-|  
|[AfxOleCanExitApp](#afxolecanexitapp)|アプリケーションが終了できるかどうかを示します。|  
|[AfxOleGetMessageFilter](#afxolegetmessagefilter)|アプリケーションの現在のメッセージ フィルターを取得します。|  
|[AfxOleGetUserCtrl](#afxolegetuserctrl)|現在のユーザー制御フラグを取得します。|  
|[AfxOleSetUserCtrl](#afxolesetuserctrl)|設定またはユーザー制御フラグをクリアします。|  
|[AfxOleLockApp](#afxolelockapp)|アプリケーションのアクティブなオブジェクトの数のフレームワークのグローバル カウントをインクリメントします。|  
|[AfxOleUnlockApp](#afxoleunlockapp)|デクリメント フレームワークのアプリケーションでアクティブなオブジェクトの数をカウントします。|  
|[AfxOleRegisterServerClass](#afxoleregisterserverclass)|OLE システム レジストリには、サーバーを登録します。|  
|[AfxOleSetEditMenu](#afxoleseteditmenu)|ユーザー インターフェイスを実装して、 *typename*コマンドのオブジェクトします。|  
  
##  <a name="a-nameafxolecanexitappa--afxolecanexitapp"></a><a name="afxolecanexitapp"></a>AfxOleCanExitApp  
 アプリケーションが終了できるかどうかを示します。  
  
```   
BOOL AFXAPI AfxOleCanExitApp(); 
```  
  
### <a name="return-value"></a>戻り値  
 以外の場合は、アプリケーションが終了することができます。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 アプリケーションでは、そのオブジェクトに未解決の参照がある場合は終了する必要があります。 グローバル関数`AfxOleLockApp`と`AfxOleUnlockApp`インクリメントおよびデクリメント、それぞれ、アプリケーションのオブジェクトへの参照カウンターです。 このカウンターがゼロ以外の場合、アプリケーションは終了できません。 カウンターがゼロ以外の場合は、アプリケーションのメイン ウィンドウが非表示 (破棄されずに) [システム] メニューまたは [ファイル] メニューからの終了を閉じるを選択するとします。 フレームワークでは、この関数を呼び出します**CFrameWnd::OnClose**します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCAutomation&#2;](../../mfc/codesnippet/cpp/application-control_1.cpp)]  

## <a name="requirements"></a>要件  
 **ヘッダー**: afxdisp.h 

##  <a name="a-nameafxolegetmessagefiltera--afxolegetmessagefilter"></a><a name="afxolegetmessagefilter"></a>AfxOleGetMessageFilter  
 アプリケーションの現在のメッセージ フィルターを取得します。  
  
```   
COleMessageFilter* AFXAPI  AfxOleGetMessageFilter(); 
```  
  
### <a name="return-value"></a>戻り値  
 現在のメッセージ フィルターへのポインター。  
  
### <a name="remarks"></a>コメント  
 現在にアクセスするには、この関数を呼び出す`COleMessageFilter`-を呼び出します。 同様に、オブジェクトを派生`AfxGetApp`現在のアプリケーション オブジェクトにアクセスします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCAutomation&#3;](../../mfc/codesnippet/cpp/application-control_2.cpp)]  
  
 [!code-cpp[NVC_MFCAutomation&4;](../../mfc/codesnippet/cpp/application-control_3.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー**: afxwin.h 

##  <a name="a-nameafxolegetuserctrla--afxolegetuserctrl"></a><a name="afxolegetuserctrl"></a>AfxOleGetUserCtrl  
 現在のユーザー制御フラグを取得します。  
  
```   
BOOL  AFXAPI AfxOleGetUserCtrl(); 
```  
  
### <a name="return-value"></a>戻り値  
 ユーザーがアプリケーションのコントロールの場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ユーザーが明示的に開かれるか、新しいドキュメントを作成したときに、ユーザーがアプリケーションを制御します。 ユーザーはコントロールにも、OLE システム Dll によって、アプリケーションを起動しなかった場合、つまり、ユーザー システム シェルを使用してアプリケーションを起動する場合は。  

### <a name="requirements"></a>要件  
 **ヘッダー**: afxdisp.h

##  <a name="a-nameafxolesetuserctrla--afxolesetuserctrl"></a><a name="afxolesetuserctrl"></a>AfxOleSetUserCtrl  
 設定またはのリファレンスで説明されているユーザー制御フラグをクリア`AfxOleGetUserCtrl`します。  
  
```  
void  AFXAPI AfxOleSetUserCtrl(BOOL bUserCtrl); 
```  
  
### <a name="parameters"></a>パラメーター  
 *bUserCtrl*  
 ユーザー制御フラグを設定またはクリアするかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 フレームワークが呼び出しますが、ユーザーを作成するか、ドキュメントを読み込みますドキュメントが読み込まれるか、コンテナー アプリケーションからの埋め込みオブジェクトの読み込みなどの間接のアクションによって作成されたときではなく。  
  
 アプリケーションでは、その他のアクションは、アプリケーションのコントロールにユーザーを配置する必要がある場合は、この関数を呼び出します。  

### <a name="requirements"></a>要件  
 **ヘッダー**: afxdisp.h

##  <a name="a-nameafxolelockappa--afxolelockapp"></a><a name="afxolelockapp"></a>AfxOleLockApp  
 アプリケーションのアクティブなオブジェクトの数のフレームワークのグローバル カウントをインクリメントします。  
  
```   
void  AFXAPI  AfxOleLockApp(); 
```  
  
### <a name="remarks"></a>コメント  
 フレームワークは、アプリケーションでアクティブなオブジェクトの数のカウントを保持します。 `AfxOleLockApp`と`AfxOleUnlockApp`関数はそれぞれ、インクリメントし、このカウントをデクリメントします。  
  
 ユーザーがアクティブなオブジェクトを持つアプリケーションを終了しようとしたときに-アクティブなオブジェクトの数がゼロ以外、アプリケーション: フレームワークには、完全にシャット ダウンではなく、ユーザーの視点から、アプリケーションが非表示にします。 `AfxOleCanExitApp`関数では、アプリケーションが終了できるかどうかを示します。  
  
 呼び出す`AfxOleLockApp`任意のオブジェクトであるようにそのオブジェクトをクライアント アプリケーションでまだ使用されているときに破棄することが望ましい場合は、OLE インターフェイスを公開するからです。 呼び出すことも`AfxOleUnlockApp`を呼び出す任意のオブジェクトのデストラクターで`AfxOleLockApp`コンス トラクターでします。 既定では、 `COleDocument` (クラスと派生クラス) に自動的にロックし、アプリケーションのロックを解除します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCAutomation&#5;](../../mfc/codesnippet/cpp/application-control_4.cpp)]  

### <a name="requirements"></a>要件  
 **ヘッダー**: afxdisp.h

##  <a name="a-nameafxoleunlockappa--afxoleunlockapp"></a><a name="afxoleunlockapp"></a>AfxOleUnlockApp  
 デクリメント、アプリケーションのアクティブなオブジェクトのフレームワークの数。  
  
```   
void AFXAPI AfxOleUnlockApp(); 
```  
  
### <a name="remarks"></a>コメント  
 参照してください`AfxOleLockApp`についてさらにします。  
  
 アクティブなオブジェクトの数が&0; に達すると**AfxOleOnReleaseAllObjects**が呼び出されます。  
  
### <a name="example"></a>例  
 例を参照してください[AfxOleLockApp](#afxolelockapp)します。  

### <a name="requirements"></a>要件  
 **ヘッダー**: afxdisp.h  

##  <a name="a-nameafxoleregisterserverclassa--afxoleregisterserverclass"></a><a name="afxoleregisterserverclass"></a>AfxOleRegisterServerClass  
 この関数では、OLE システム レジストリにサーバーを登録することができます。  
  
```   
BOOL AFXAPI AfxOleRegisterServerClass(
    REFCLSID clsid,  
    LPCTSTR lpszClassName,  
    LPCTSTR lpszShortTypeName,  
    LPCTSTR lpszLongTypeName,  
    OLE_APPTYPE nAppType = OAT_SERVER,  
    LPCTSTR* rglpszRegister = NULL,  
    LPCTSTR* rglpszOverwrite = NULL); 
```  
  
### <a name="parameters"></a>パラメーター  
 `clsid`  
 サーバーの OLE クラスの ID への参照  
  
 `lpszClassName`  
 サーバーのオブジェクトのクラス名を含む文字列へのポインター。  
  
 *lpszShortTypeName*  
 サーバーのオブジェクトの種類を"Chart"などの短い名前を含む文字列へのポインター  
  
 *lpszLongTypeName*  
 サーバーのオブジェクトの種類を"Microsoft Excel 5.0 Chart"などの長い名前を含む文字列へのポインター  
  
 `nAppType`  
 取得した、値、 **OLE_APPTYPE** OLE アプリケーションの種類を指定します。 使用可能な値、次のとおりです。  
  
- `OAT_INPLACE_SERVER`サーバーは、サーバー全体のユーザー インターフェイスを持っています。  
  
- `OAT_SERVER`サーバーは、埋め込みだけをサポートします。  
  
- `OAT_CONTAINER`コンテナーは、埋め込みアイテムへのリンクをサポートします。  
  
- `OAT_DISPATCH_OBJECT``IDispatch`-可能なオブジェクトです。  
  
 `rglpszRegister`  
 キーとキーの既存の値が見つからない場合は、OLE システム レジストリに追加する値を表す文字列へのポインターの配列。  
  
 `rglpszOverwrite`  
 キーとレジストリに指定されたキーの既存の値が含まれている場合、OLE システム レジストリに追加する値を表す文字列へのポインターの配列。  
  
### <a name="return-value"></a>戻り値  
 サーバー クラスが正常に登録されている場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ほとんどのアプリケーションが使用できる**COleTemplateServer::Register**をアプリケーションのドキュメントの種類を登録します。 使用することができます、アプリケーションのシステム レジストリ形式では一般的なパターンが収まらない場合`AfxOleRegisterServerClass`詳細に制御します。  
  
 レジストリは、キーと値のセットで構成されます。 `rglpszRegister`と`rglpszOverwrite`引数文字列へのポインターの配列である、文字列から構成される、キーと値で区切られた、 **NULL**文字 ( `'\0'`)。 これらの各文字列が可能な文字シーケンスは、置き換え可能パラメーターをとります`%1`を通じて`%5`します。  
  
 シンボルはように入力されます。  
  
|シンボル|値|  
|------------|-----------|  
|%1|クラスの ID を文字列として書式設定|  
|%2|クラス名|  
|%3|実行可能ファイルへのパス|  
|%4|短い型名|  
|%5|Long 型の名前|  

### <a name="requirements"></a>要件  
 **ヘッダー**: afxdisp.h

##  <a name="a-nameafxoleseteditmenua--afxoleseteditmenu"></a><a name="afxoleseteditmenu"></a>AfxOleSetEditMenu  
 ユーザー インターフェイスを実装して、 *typename*コマンドのオブジェクトします。  
  
```   
void  AFXAPI  AfxOleSetEditMenu(
    COleClientItem* pClient,  
    CMenu* pMenu,  
    UINT iMenuItem,  
    UINT nIDVerbMin,  
    UINT nIDVerbMax = 0,  
    UINT nIDConvert = 0); 
```  
  
### <a name="parameters"></a>パラメーター  
 `pClient`  
 クライアント OLE アイテムへのポインター。  
  
 `pMenu`  
 更新するメニュー オブジェクトへのポインター。  
  
 *iMenuItem*  
 更新するメニュー項目のインデックス。  
  
 `nIDVerbMin`  
 主動詞に対応するコマンド ID です。  
  
 *nIDVerbMax*  
 最後の動詞に対応するコマンド ID です。  
  
 *nIDConvert*  
 変換のメニュー項目の ID。  
  
### <a name="remarks"></a>コメント  
 主動詞のみを認識すると、サーバーの場合、メニュー項目は次のようになります。"動詞*typename*オブジェクト"と`nIDVerbMin`コマンドが送信されるのは、コマンドを選択するとします。 かどうかには、サーバーが、いくつかの動詞を認識し、メニュー項目になります" *typename*オブジェクト"され、コマンドを選択すると、すべての動詞の一覧を表示するサブメニューが表示されます。 サブメニューの動詞を選択すると`nIDVerbMin`かどうかは、最初の動詞を選択した場合は送信`nIDVerbMin`+ 1 が 2 番目の動作は、選択した場合に送信されます。 既定値`COleDocument`の実装は、この機能を自動的に処理します。  
  
 クライアントのアプリケーション リソースのスクリプトで、次のステートメントを持つ必要があります (します。RC) のファイル:  
  
 **#include \<afxolecl.rc >**  

### <a name="requirements"></a>要件  
 **ヘッダー**: afxole.h 

## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)

