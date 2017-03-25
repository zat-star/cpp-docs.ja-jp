---
title: "メッセージ マップ マクロ (MFC) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.messages
dev_langs:
- C++
helpviewer_keywords:
- message map macros
- Windows messages [C++], declaration
- demarcating Windows messages
- message maps [C++], macros
- message maps [C++], declaration and demarcation
- message mapping macros
- ranges, message map
- message map ranges
ms.assetid: 531b15ce-32b5-4ca0-a849-bb519616c731
caps.latest.revision: 10
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
ms.sourcegitcommit: d4b97ed874b145f9c6d9a9536476243bba0fd1c1
ms.openlocfilehash: 0c5856dce919ca8ea2d396fbf2523dc45409b519
ms.lasthandoff: 03/06/2017

---
# <a name="message-map-macros-mfc"></a>メッセージ マップ マクロ (MFC)
メッセージ マップをサポートするためには、MFC は、次のマクロを提供します。  
  
### <a name="message-map-declaration-and-demarcation-macros"></a>メッセージ マップの宣言と定義用マクロ  
  
|||  
|-|-|  
|[DECLARE_MESSAGE_MAP](#declare_message_map)|メッセージ マップがクラスでメッセージを関数にマップ (クラス宣言で使用する必要があります) 使用されることを宣言します。|  
|[BEGIN_MESSAGE_MAP](#begin_message_map)|メッセージ マップ (クラスの実装で使用する必要があります) の定義を開始します。|  
|[END_MESSAGE_MAP](#end_message_map)|メッセージ マップ (クラスの実装で使用する必要があります) の定義を終了します。|  
  
### <a name="message-mapping-macros"></a>メッセージ割り当てマクロ  
  
|||  
|-|-|  
|[ON_COMMAND](#on_command)|指定したコマンドのメッセージを処理する関数を示します。|  
|[ON_CONTROL](#on_control)|指定したコントロール通知メッセージを処理する関数を示します。|  
|[ON_MESSAGE](#on_message)|ユーザー定義のメッセージを処理する関数を示します。|  
|[ON_OLECMD](#on_olecmd)|DocObject またはコンテナーからメニュー コマンドを処理する関数を示します。|  
|[ON_REGISTERED_MESSAGE](#on_registered_message)|登録済みのユーザー定義のメッセージを処理する関数を示します。|  
|[ON_REGISTERED_THREAD_MESSAGE](#on_registered_thread_message)|ある場合にどの関数が登録されているユーザー定義メッセージを処理を示す、`CWinThread`クラスです。|  
|[ON_THREAD_MESSAGE](#on_thread_message)|ある場合、どの関数がユーザー定義メッセージを処理するかを示す、`CWinThread`クラスです。|  
|[ON_UPDATE_COMMAND_UI](#on_update_command_ui)|指定されたユーザー インターフェイスの更新コマンド メッセージを処理する関数を示します。|  
  
### <a name="message-map-range-macros"></a>範囲指定のメッセージ マップ マクロ  
  
|||  
|-|-|  
|[割り当てるには](#on_command_range)|マクロに対する最初の&2; つのパラメーターで指定されたコマンド Id の範囲を処理する関数を示します。|  
|[ON_UPDATE_COMMAND_UI_RANGE](#on_update_command_ui_range)|最初の&2; つの pa で指定されたコマンド Id の範囲を処理する更新ハンドラーを示します] rameters マクロにします。|  
|[ON_CONTROL_RANGE](#on_control_range)|コントロールのマクロに&2; 番目と&3; 番目のパラメーターで指定した Id の範囲からの通知を処理する関数を示します。 最初のパラメーターは、コントロールの通知メッセージをなどは**BN_CLICKED**します。|  
  
 メッセージ マップ、メッセージ マップの宣言と定義用マクロ、およびメッセージ マップ マクロの詳細については、次を参照してください。[メッセージ マップ](../../mfc/reference/message-maps-mfc.md)と[メッセージの処理とのマッピング」](../../mfc/message-handling-and-mapping.md)します。 メッセージ マップの範囲の詳細については、次を参照してください。[メッセージ マップの範囲内のハンドラー](../../mfc/handlers-for-message-map-ranges.md)します。  

## <a name="declare_message_map"></a>DECLARE_MESSAGE_MAP
 クラスがメッセージ マップを定義することを宣言します。 各`CCmdTarget`-プログラム内の派生クラスは、メッセージを処理するメッセージ マップを提供する必要があります。  
  
### <a name="syntax"></a>構文  
  
```    
DECLARE_MESSAGE_MAP( )  
```  
  
### <a name="remarks"></a>コメント  
 使用して、`DECLARE_MESSAGE_MAP`クラス宣言の末尾のマクロです。 クラスのメンバー関数を定義する .cpp ファイルで使用して、`BEGIN_MESSAGE_MAP`メッセージ ハンドラー関数の各マクロを`END_MESSAGE_MAP`マクロです。  
  
> [!NOTE]
>  後のすべてのメンバーを宣言する場合`DECLARE_MESSAGE_MAP`、新しいアクセスの種類を指定する必要があります (**パブリック**、 `private`、または`protected`) にします。  
  
 メッセージの詳細については、マップ、および`DECLARE_MESSAGE_MAP`マクロを参照してください[メッセージの処理とマップ」](../../mfc/message-handling-and-mapping.md)します。  
  
### <a name="example"></a>例  
```cpp  
class CMainFrame : public CMDIFrameWnd
{
   DECLARE_MESSAGE_MAP()

   // Remainder of class declaration omitted.
``` 
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  

## <a name="begin_message_map"></a>BEGIN_MESSAGE_MAP
メッセージ マップの定義を開始します。  
  
### <a name="syntax"></a>構文  
  
```  
BEGIN_MESSAGE_MAP( theClass, baseClass )  
```  
  
### <a name="parameters"></a>パラメーター  
 `theClass`  
 マップを持つメッセージ クラスの名前を指定します。  
  
 `baseClass`  
 基本クラスの名前を指定`theClass`します。  
  
### <a name="remarks"></a>コメント  
 クラスのメンバー関数を定義する実装 (.cpp) ファイルでメッセージ マップを開始、`BEGIN_MESSAGE_MAP`マクロのメッセージ ハンドラー関数のマクロのエントリを追加し、しし、メッセージ マップ、`END_MESSAGE_MAP`マクロです。  
  
 メッセージ マップの詳細については、次を参照してください[メッセージ マップ。](message-maps-mfc.md)  
  
### <a name="example"></a>例  
```cpp  
BEGIN_MESSAGE_MAP(CMainFrame, CMDIFrameWnd)
   ON_WM_CREATE()
END_MESSAGE_MAP()
```
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h 

## <a name="end_message_map"></a>END_MESSAGE_MAP
メッセージ マップの定義を終了します。  
  
### <a name="syntax"></a>構文  
  
```   
END_MESSAGE_MAP( )  
```  
  
### <a name="remarks"></a>コメント  
 メッセージの詳細については、マップ、および`END_MESSAGE_MAP`マクロを参照してください[メッセージの処理とマップ」](../../mfc/message-handling-and-mapping.md)します。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  

## <a name="on_command"></a>ON_COMMAND
このマクロは、コマンドのメッセージをメンバー関数にマップします。  
  
### <a name="syntax"></a>構文  
  
```  
ON_COMMAND( id, memberFxn )  
```  
  
### <a name="parameters"></a>パラメーター  
 `id`  
 コマンド ID。  
  
 `memberFxn`  
 コマンドがマップされているメッセージ ハンドラー関数の名前。  
  
### <a name="remarks"></a>コメント  
 これは、メニュー項目またはツール バー ボタンなどのコマンドのユーザー インターフェイス オブジェクトからのコマンド メッセージを処理する関数を示します。  
  
 コマンド ターゲット オブジェクトが、Windows を受信すると**WM_COMMAND**指定の ID を持つメッセージ`ON_COMMAND`、メンバー関数を呼び出して`memberFxn`メッセージを処理します。  
  
 使用`ON_COMMAND`に&1; つのコマンドをメンバー関数にマップします。 使用[ON_COMMAND_RANGE](#on_command_range)コマンド id の範囲を&1; つのメンバー関数にマップします。 1 つだけのメッセージ マップ エントリは、指定されたコマンド id と一致できます。 つまり、1 つ以上のハンドラーにコマンドを割り当てることはできません。 詳細と例については、次を参照してください。[メッセージの処理とマップ」](../../mfc/message-handling-and-mapping.md)します。  
  
### <a name="example"></a>例  
```cpp  
BEGIN_MESSAGE_MAP(CMFCListViewDoc, CDocument)
   ON_COMMAND(ID_MYCOMMAND, &CMFCListViewDoc::OnMycommand)
END_MESSAGE_MAP()
``` 
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxmsg_.h  
  
## <a name="on_control"></a>ON_CONTROL
カスタム コントロールの通知メッセージを処理する関数を示します。  
  
### <a name="syntax"></a>構文  
  
```  
ON_CONTROL( wNotifyCode, id, memberFxn )  
```  
  
### <a name="parameters"></a>パラメーター  
 `wNotifyCode`  
 コントロールの通知コード。  
  
 `id`  
 コマンド ID。  
  
 `memberFxn`  
 コマンドがマップされているメッセージ ハンドラー関数の名前。  
  
### <a name="remarks"></a>コメント  
 コントロールの通知メッセージは、親ウィンドウに、コントロールから送信されたものです。  
  
 正確に&1; つあります`ON_CONTROL`メッセージ ハンドラー関数にマップする必要がある各コントロールの通知メッセージをメッセージ マップにマクロ ステートメントです。  
  
 詳細と例については、次を参照してください。[メッセージの処理とマップ」](../../mfc/message-handling-and-mapping.md)します。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxmsg_.h  
  

## <a name="on_message"></a>ON_MESSAGE  
ユーザー定義のメッセージを処理する関数を示します。  
  
### <a name="syntax"></a>構文  
  
```  
ON_MESSAGE( message, memberFxn )  
```  
  
### <a name="parameters"></a>パラメーター  
 `message`  
 メッセージ ID。  
  
 `memberFxn`  
 メッセージがマップされているメッセージ ハンドラー関数の名前。  
  
 関数の型である必要があります`afx_msg LRESULT (CWnd::*)(WPARAM, LPARAM)`します。  
  
### <a name="remarks"></a>コメント  
 ユーザー定義メッセージは、標準の Windows ではないすべてのメッセージ`WM_MESSAGE`メッセージです。 メッセージ ID を選択するときの範囲内の値を使用する必要があります`WM_USER`(0x0400) 0x7FFF にまたは`WM_APP`(0x8000) 0xBFFF にします。 メッセージ Id の詳細については、次を参照してください。 [WM_APP](http://msdn.microsoft.com/library/windows/desktop/ms644930)します。  
  
 正確に&1; つあります`ON_MESSAGE`メッセージ ハンドラー関数にマップされるすべてのユーザー定義メッセージに対して、メッセージ マップにマクロ ステートメントです。  
  
> [!NOTE]
>  ユーザー定義メッセージだけでなく`ON_MESSAGE`はあまり一般的では Windows メッセージを処理します。 詳細については、技術情報の記事を参照してください。 [99848: 情報: マップ頻度の低いメッセージに使用する ON_MESSAGE() マクロ](http://go.microsoft.com/fwlink/?linkId=192022)します。  
  
 詳細と例については、次を参照してください[メッセージの処理とマップ」](../../mfc/message-handling-and-mapping.md)と[ユーザー定義のハンドラー。](user-defined-handlers.md)  
  
### <a name="example"></a>例  
```cpp  
#define WM_MYMESSAGE (WM_USER + 100)

BEGIN_MESSAGE_MAP(CMyWnd2, CWnd)
   ON_MESSAGE(WM_MYMESSAGE, OnMyMessage)
END_MESSAGE_MAP()

// inside the class declaration
 afx_msg LRESULT OnMyMessage(WPARAM wParam, LPARAM lParam);

 LRESULT CMyWnd2::OnMyMessage(WPARAM wParam, LPARAM lParam)
{
   UNREFERENCED_PARAMETER(wParam);
   UNREFERENCED_PARAMETER(lParam);

   // Handle message here. 

   return 0;
}
```   
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxmsg_.h  

## <a name="on_olecmd"></a>ON_OLECMD    
コマンド、コマンドのディスパッチ インターフェイスを使用してルーティング`IOleCommandTarget`します。  
  
### <a name="syntax"></a>構文  
  
```  
ON_OLECMD( pguid, olecmdid, id )  
```  
  
### <a name="parameters"></a>パラメーター  
 `pguid`  
 コマンドが所属するコマンド グループの識別子です。 使用**NULL**標準的なグループです。  
  
 *olecmdid*  
 OLE コマンドの識別子です。  
  
 `id`  
 メニュー ID、ツールバー ID、ボタンの ID またはリソースまたはコマンドを発行したオブジェクトの他の ID。  
  
### <a name="remarks"></a>コメント  
 `IOleCommandTarget`DocObject のユーザー インターフェイスでは、コマンドを受信するためのコンテナーにでき、同じコマンドを送信するためのコンテナー (新規、開く、名前を付けて保存、および [ファイル] メニューで、印刷など、コピー、貼り付け、元に戻したり、[編集] メニュー) DocObject にします。  
  
 `IOleCommandTarget`OLE オートメーションのよりも単純です`IDispatch`します。 `IOleCommandTarget`コマンドの標準セットに完全に依存している引数を持つことはほとんどありませんし、型情報は必要ありません (タイプ セーフがコマンドの引数も低下している)。 引数を持つコマンドをディスパッチする場合を使用して[COleServerDoc::OnExecOleCmd](coleserverdoc-class.md#onexecolecmd)します。  
  
 `IOleCommandTarget`標準メニュー コマンドは、次のマクロで MFC によって実装されたもの。  
  
 **ON_OLECMD_CLEARSELECTION)**  
  
 Clear 編集コマンドをディスパッチします。 として実装されています。  
  
 `ON_OLECMD(NULL, OLECMDID_CLEARSELECTION, ID_EDIT_CLEAR)`  
  
 **ON_OLECMD_COPY)**  
  
 コピーの編集コマンドをディスパッチします。 として実装されています。  
  
 `ON_OLECMD(NULL, OLECMDID_COPY, ID_EDIT_COPY)`  
  
 **ON_OLECMD_CUT)**  
  
 切り取りの編集 コマンドをディスパッチします。 として実装されています。  
  
 `ON_OLECMD(NULL, OLECMDID_CUT, ID_EDIT_CUT)`  
  
 **ON_OLECMD_NEW)**  
  
 ファイルの新規作成 コマンドをディスパッチします。 として実装されています。  
  
 `ON_OLECMD(NULL, OLECMDID_NEW, ID_FILE_NEW)`  
  
 **ON_OLECMD_OPEN)**  
  
 ファイルを開くコマンドをディスパッチします。 として実装されています。  
  
 `ON_OLECMD(NULL, OLECMDID_OPEN, ID_FILE_OPEN)`  
  
 **ON_OLECMD_PAGESETUP)**  
  
 ファイルのページ設定 コマンドをディスパッチします。 として実装されています。  
  
 `ON_OLECMD(NULL, OLECMDID_PAGESETUP, ID_FILE_PAGE_SETUP)`  
  
 **ON_OLECMD_PASTE)**  
  
 編集の貼り付け コマンドをディスパッチします。 として実装されています。  
  
 `ON_OLECMD(NULL, OLECMDID_PASTE, ID_EDIT_PASTE)`  
  
 **ON_OLECMD_PASTESPECIAL)**  
  
 編集貼り付け コマンドをディスパッチします。 として実装されています。  
  
 `ON_OLECMD(NULL, OLECMDID_PASTESPECIAL, ID_EDIT_PASTE_SPECIAL)`  
  
 **ON_OLECMD_PRINT)**  
  
 ファイル [印刷] コマンドをディスパッチします。 として実装されています。  
  
 `ON_OLECMD(NULL, OLECMDID_PRINT, ID_FILE_PRINT)`  
  
 **ON_OLECMD_PRINTPREVIEW)**  
  
 ファイルの印刷プレビュー コマンドをディスパッチします。 として実装されています。  
  
 `ON_OLECMD(NULL, OLECMDID_PRINTPREVIEW, ID_FILE_PRINT_PREVIEW)`  
  
 **ON_OLECMD_REDO)**  
  
 [やり直し] コマンドをディスパッチします。 として実装されています。  
  
 `ON_OLECMD(NULL, OLECMDID_REDO, ID_EDIT_REDO)`  
  
 **ON_OLECMD_SAVE)**  
  
 ファイルの保存 コマンドをディスパッチします。 として実装されています。  
  
 `ON_OLECMD(NULL, OLECMDID_SAVE, ID_FILE_SAVE)`  
  
 **ON_OLECMD_SAVE_AS)**  
  
 ファイル名を付けて保存 をディスパッチします。 として実装されています。  
  
 `ON_OLECMD(NULL, OLECMDID_SAVEAS, ID_FILE_SAVE_AS)`  
  
 **ON_OLECMD_SAVE_COPY_AS)**  
  
 ファイルのコピーを付けて保存 コマンドをディスパッチします。 として実装されています。  
  
 `ON_OLECMD(NULL, OLECMDID_SAVECOPYAS, ID_FILE_SAVE_COPY_AS)`  
  
 **ON_OLECMD_SELECTALL)**  
  
 すべての編集コマンドをディスパッチします。 として実装されています。  
  
 `ON_OLECMD(NULL, OLECMDID_SELECTALL, ID_EDIT_SELECT_ALL)`  
  
 **ON_OLECMD_UNDO)**  
  
 編集を元に戻すコマンドをディスパッチします。 として実装されています。  
  
 `ON_OLECMD(NULL, OLECMDID_UNDO, ID_EDIT_UNDO)`  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxdocob.h  
  
### <a name="see-also"></a>関連項目  
 [COleCmdUI クラス](colecmdui-class.md)   
 [COleServerDoc::OnExecOleCmd](coleserverdoc-class.md#onexecolecmd)

## <a name="on_registered_message"></a>ON_REGISTERED_MESSAGE
Windows**を通じて**関数を使用して、システム全体で一意であることが保証されている新しいウィンドウ メッセージを定義します。  
  
### <a name="syntax"></a>構文  
  
```  
ON_REGISTERED_MESSAGE( nMessageVariable, memberFxn )  
```  
  
### <a name="parameters"></a>パラメーター  
 `nMessageVariable`  
 登録されたウィンドウ メッセージ ID 変数です。  
  
 `memberFxn`  
 メッセージがマップされているメッセージ ハンドラー関数の名前。  
  
### <a name="remarks"></a>コメント  
 このマクロは、登録済みのメッセージを処理する関数を示します。  
  
 詳細と例については、次を参照してください。[メッセージの処理とマップ」](../../mfc/message-handling-and-mapping.md)します。  
  
### <a name="example"></a>例  
```cpp  
static UINT NEAR WM_FIND = RegisterWindowMessage(_T("COMMDLG_FIND"));


BEGIN_MESSAGE_MAP(CMyWnd3, CWnd)
   ON_REGISTERED_MESSAGE(WM_FIND, OnFind)
END_MESSAGE_MAP()
```  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxmsg_.h  
  
### <a name="see-also"></a>関連項目  
 [を通じて](http://msdn.microsoft.com/library/windows/desktop/ms644947)   
 [ユーザー定義によるハンドラー](user-defined-handlers.md)

## <a name="on_registered_thread_message"></a>ON_REGISTERED_THREAD_MESSAGE    
Windows を通じて関数によって登録されたメッセージを処理する関数を示します。  
  
### <a name="syntax"></a>構文  
  
```  
ON_REGISTERED_THREAD_MESSAGE(nMessageVariable, memberFxn )  
```  
  
### <a name="parameters"></a>パラメーター  
 `nMessageVariable`  
 登録されたウィンドウ メッセージ ID 変数です。  
  
 `memberFxn`  
 メッセージがマップされている CWinThread メッセージ ハンドラー関数の名前。  
  
### <a name="remarks"></a>コメント  
 を通じてを使用して、システム全体で一意であることが保証されている新しいウィンドウ メッセージを定義します。 CWinThread クラスがある場合、システムではなく ON_REGISTERED_THREAD_MESSAGE を使用する必要があります。 
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxmsg_.h  

## <a name="on_thread_message"></a>ON_THREAD_MESSAGE    
ユーザー定義のメッセージを処理する関数を示します。  
  
### <a name="syntax"></a>構文  
  
```  
ON_THREAD_MESSAGE( message, memberFxn )  
```  
  
### <a name="parameters"></a>パラメーター  
 `message`  
 メッセージ ID。  
  
 `memberFxn`  
 名前、 `CWinThread`-メッセージのメッセージがマップされているハンドラー関数。  
  
### <a name="remarks"></a>コメント  
 `ON_THREAD_MESSAGE`代わりに使用する必要があります`ON_MESSAGE`がある場合、`CWinThread`クラスです。 ユーザー定義メッセージは、標準の Windows ではないすべてのメッセージ**WM_MESSAGE**メッセージです。 正確に&1; つあります`ON_THREAD_MESSAGE`メッセージ ハンドラー関数にマップされるすべてのユーザー定義メッセージに対して、メッセージ マップにマクロ ステートメントです。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxole.h  

## <a name="on_update_command_ui"></a>ON_UPDATE_COMMAND_UI    
このマクロは、ユーザー インターフェイスの更新コマンド メッセージを処理する関数を示します。  
  
### <a name="syntax"></a>構文  
  
```  
ON_UPDATE_COMMAND_UI( id, memberFxn )  
```  
  
### <a name="parameters"></a>パラメーター  
 `id`  
 メッセージ ID。  
  
 `memberFxn`  
 メッセージがマップされているメッセージ ハンドラー関数の名前。  
  
### <a name="remarks"></a>コメント  
 正確に&1; つあります`ON_UPDATE_COMMAND_UI`メッセージ ハンドラー関数にマップされるすべてのユーザー インターフェイス更新コマンドに対して、メッセージ マップにマクロ ステートメントです。  
  
 詳細と例については、次を参照してください。[メッセージの処理とマップ」](../../mfc/message-handling-and-mapping.md)します。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxole.h  
  
### <a name="see-also"></a>関連項目  
 [CCmdUI クラス](ccmdui-class.md)

## <a name="on_command_range"></a>割り当てるには  
コマンド Id の連続した範囲を&1; つのメッセージ ハンドラー関数にマップするのにには、このマクロを使用します。  
  
### <a name="syntax"></a>構文
  
```  
ON_COMMAND_RANGE( id1, id2, memberFxn )  
```  
  
### <a name="parameters"></a>パラメーター  
 `id1`  
 コマンド Id の連続した範囲の先頭にあるコマンド ID です。  
  
 `id2`  
 コマンド Id の連続した範囲の最後のコマンド ID です。  
  
 `memberFxn`  
 コマンドがマップされているメッセージ ハンドラー関数の名前。  
  
### <a name="remarks"></a>コメント  
 Id 範囲の始まり`id1`で終わります`id2`します。  
  
 使用`ON_COMMAND_RANGE`コマンド Id の範囲を&1; つのメンバー関数にマップします。 使用[ON_COMMAND](#on_command)に&1; つのコマンドをメンバー関数にマップします。 1 つだけのメッセージ マップ エントリが指定されたコマンド ID と一致できます。 つまり、1 つ以上のハンドラーにコマンドを割り当てることはできません。 メッセージの範囲のマッピングの詳細については、次を参照してください。[メッセージ マップの範囲内のハンドラー](../../mfc/handlers-for-message-map-ranges.md)します。  
  
 自分でこのマクロを記述する必要がありますので、メッセージ マップの範囲の自動サポートはありません。  
  
### <a name="example"></a>例  
```cpp  
// The code fragment below shows how to use ON_COMMAND_RANGE macro 
// to map a contiguous range of command IDs to a single message  
// handler function (i.e. OnRangeCmds() in the sample below). In  
// addition, it also shows how to use CheckMenuRadioItem() to check a  
// selected menu item and makes it a radio item.

BEGIN_MESSAGE_MAP(CChildFrame, CMDIChildWnd)
   ON_COMMAND_RANGE(ID_COMMAND_RANGECMD1, ID_COMMAND_RANGECMD3, &CChildFrame::OnRangeCmds)
END_MESSAGE_MAP()

void CChildFrame::OnRangeCmds(UINT nID)
{
   CMenu* mmenu = AfxGetMainWnd()->GetMenu();
   CMenu* submenu = mmenu->GetSubMenu(5);
   submenu->CheckMenuRadioItem(ID_COMMAND_RANGECMD1, ID_COMMAND_RANGECMD3, 
      nID, MF_BYCOMMAND);
}
```
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxmsg_.h  

## <a name="on_update_command_ui_range"></a>ON_UPDATE_COMMAND_UI_RANGE    
コマンド Id の連続した範囲を&1; つの更新メッセージ ハンドラー関数にマップします。  
  
### <a name="syntax"></a>構文  
  
```  
ON_UPDATE_COMMAND_UI_RANGE( id1, id2, memberFxn )  
```  
  
### <a name="parameters"></a>パラメーター  
 `id1`  
 コマンド Id の連続した範囲の先頭にあるコマンド ID です。  
  
 `id2`  
 コマンド Id の連続した範囲の最後のコマンド ID です。  
  
 `memberFxn`  
 コマンドがマップされている更新プログラムのメッセージ ハンドラー関数の名前。  
  
### <a name="remarks"></a>コメント  
 更新メッセージ ハンドラーは、メニュー項目と、コマンドに関連付けられたツール バー ボタンの状態を更新します。 Id 範囲の始まり`id1`で終わります`id2`します。  
  
 自分でこのマクロを記述する必要がありますので、メッセージ マップの範囲の自動サポートはありません。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxmsg_.h  

## <a name="on_control_range"></a>ON_CONTROL_RANGE     
このマクロを使用してなどコントロール Id の連続した範囲を指定した Windows の通知メッセージの&1; つのメッセージ ハンドラー関数にマップ**BN_CLICKED**します。  
  
### <a name="syntax"></a>構文  
  
```  
ON_CONTROL_RANGE( wNotifyCode, id1, id2, memberFxn )  
```  
  
### <a name="parameters"></a>パラメーター  
 `wNotifyCode`  
 ハンドラーが応答して通知コード。  
  
 `id1`  
 コントロール Id の連続した範囲の先頭にあるコマンド ID です。  
  
 `id2`  
 コントロール Id の連続した範囲の最後のコマンド ID です。  
  
 `memberFxn`  
 コントロールがマップされているメッセージ ハンドラー関数の名前。  
  
### <a name="remarks"></a>コメント  
 Id 範囲の始まり`id1`で終わります`id2`します。 マップされたコントロールのいずれかから指定された通知のハンドラーが呼び出されます。  
  
 自分でこのマクロを記述する必要がありますので、メッセージ マップの範囲の自動サポートはありません。  
  
 コントロール Id の範囲のハンドラー関数の実装の詳細についてを参照してください[メッセージ マップの範囲内のハンドラー](../../mfc/handlers-for-message-map-ranges.md)します。  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** afxmsg_.h  
  



