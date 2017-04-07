---
title: "CMDIChildWnd クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMDIChildWnd
- AFXWIN/CMDIChildWnd
- AFXWIN/CMDIChildWnd::CMDIChildWnd
- AFXWIN/CMDIChildWnd::Create
- AFXWIN/CMDIChildWnd::GetMDIFrame
- AFXWIN/CMDIChildWnd::MDIActivate
- AFXWIN/CMDIChildWnd::MDIDestroy
- AFXWIN/CMDIChildWnd::MDIMaximize
- AFXWIN/CMDIChildWnd::MDIRestore
- AFXWIN/CMDIChildWnd::SetHandles
dev_langs:
- C++
helpviewer_keywords:
- MDI [C++], child windows
- windows [C++], MDI
- CMDIChildWnd class
- child windows, CMDIChildWnd class
ms.assetid: 6d07f5d4-9a3e-4723-9fa5-e65bb669fdd5
caps.latest.revision: 22
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
ms.openlocfilehash: 240af1fe5f3afa4cdb7d4d585dc74cc4836799cc
ms.lasthandoff: 02/24/2017

---
# <a name="cmdichildwnd-class"></a>CMDIChildWnd クラス
ウィンドウ管理用のメンバーも含めて、Windows のマルチ ドキュメント インターフェイス (MDI: multiple document interface) の子ウィンドウの機能が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class CMDIChildWnd : public CFrameWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMDIChildWnd::CMDIChildWnd](#cmdichildwnd)|`CMDIChildWnd` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMDIChildWnd::Create](#create)|関連付けられている Windows の MDI 子ウィンドウを作成、`CMDIChildWnd`オブジェクトです。|  
|[CMDIChildWnd::GetMDIFrame](#getmdiframe)|親の MDI クライアント ウィンドウの MDI フレームを返します。|  
|[CMDIChildWnd::MDIActivate](#mdiactivate)|MDI 子ウィンドウをアクティブにします。|  
|[CMDIChildWnd::MDIDestroy](#mdidestroy)|MDI 子ウィンドウを破棄します。|  
|[CMDIChildWnd::MDIMaximize](#mdimaximize)|MDI 子ウィンドウを最大化します。|  
|[CMDIChildWnd::MDIRestore](#mdirestore)|MDI 子ウィンドウを最大化または最小化されているサイズから復元します。|  
|[CMDIChildWnd::SetHandles](#sethandles)|メニューとアクセラレータのリソース ハンドルを設定します。|  
  
## <a name="remarks"></a>コメント  
 デスクトップではなく、MDI フレーム ウィンドウ内に MDI 子ウィンドウが表示されますが、一般的なフレーム ウィンドウと同様 MDI 子ウィンドウを検索します。 MDI 子ウィンドウは、独自のメニュー バーではありませんが、代わりに、MDI フレーム ウィンドウのメニューを共有します。 フレームワークでは、現在アクティブな MDI 子ウィンドウを表すため、MDI フレームのメニューに自動的に変更します。  
  
 アプリケーションの便利な MDI 子ウィンドウを作成するには、派生クラスを`CMDIChildWnd`します。 メンバー変数をアプリケーションに固有のデータを格納する派生クラスに追加します。 ウィンドウにメッセージが送られたときに行われる処理を指定するには、派生クラスにメッセージ処理メンバー関数とメッセージ マップを実装します。  
  
 MDI 子ウィンドウを作成する&3; つの方法があります。  
  
-   使用してページを直接構築**作成**します。  
  
-   使用してページを直接構築`LoadFrame`します。  
  
-   間接的に構築、ドキュメント テンプレートを使用します。  
  
 呼び出す前に**作成**または`LoadFrame`、C++ を使用して、ヒープ上のフレーム ウィンドウ オブジェクトを構築する必要があります**新しい**演算子。 呼び出しの前に**作成**でウィンドウ クラスを登録することも、 [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass)グローバル関数、フレームのアイコンとクラスのスタイルを設定します。  
  
 使用して、**作成**引数を渡すフレームの作成パラメーターに直接のメンバー関数。  
  
 `LoadFrame`も少ない数の引数を必要と**作成**、し、代わりに、フレームのキャプション、アイコン、アクセラレータ テーブル、およびメニューなどのリソースから、既定の値のほとんどを取得します。 アクセスできる`LoadFrame`、これらすべてのリソースが同じリソース ID を持つ必要があります (たとえば、 **IDR_MAINFRAME**)。  
  
 ときに、`CMDIChildWnd`オブジェクトには、ビューやドキュメントが含まれています、これらは間接的に作成、プログラマが直接は代わりに、フレームワークができます。 `CDocTemplate`オブジェクトは、フレームの作成、コンテナーのビューの作成と適切なドキュメント ビューの接続を調整します。 パラメーター、`CDocTemplate`コンス トラクターを指定、 `CRuntimeClass`&3; つのクラスの関係 (ドキュメント、フレーム、および表示)。 A`CRuntimeClass`オブジェクトは動的に (たとえば、ファイルの新規作成 コマンドまたは MDI ウィンドウの新しいコマンドを使用して) を指定すると、ユーザーが新しいフレームを作成するために、フレームワークによって使用されます。  
  
 フレーム ウィンドウ クラスから派生`CMDIChildWnd`で宣言する必要があります`DECLARE_DYNCREATE`上記の順序で`RUNTIME_CLASS`正常に動作するためのメカニズムです。  
  
 `CMDIChildWnd`クラスは継承から既定の実装の大部分`CFrameWnd`します。 これらの機能の詳細な一覧を参照してください、 [CFrameWnd](../../mfc/reference/cframewnd-class.md)クラスの記述。 `CMDIChildWnd`クラスには次の追加機能。  
  
-   組み合わせて、`CMultiDocTemplate`クラスの中で複数`CMDIChildWnd`同じドキュメント テンプレートからのオブジェクトが Windows システム リソースを保存する、同じメニューを共有します。  
  
-   現在アクティブな MDI 子ウィンドウのメニューが完全に MDI フレーム ウィンドウのメニューを置き換え、MDI フレーム ウィンドウのキャプションに現在アクティブな MDI 子ウィンドウのキャプションを追加します。 MDI フレーム ウィンドウと共に実装されている MDI 子ウィンドウ関数の詳細例については、次を参照してください。、`CMDIFrameWnd`クラスの記述。  
  
 C++ を使用しないで**削除**フレーム ウィンドウを破棄する演算子です。 代わりに、 `CWnd::DestroyWindow` を使用してください。 `CFrameWnd`の実装`PostNcDestroy`ウィンドウが破棄されるときに、C++ オブジェクトを削除します。 ユーザーが、既定のフレーム ウィンドウを閉じたときに`OnClose`ハンドラーが呼び出す`DestroyWindow`します。  
  
 詳細については`CMDIChildWnd`を参照してください[フレーム ウィンドウ](../../mfc/frame-windows.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `CMDIChildWnd`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="cmdichildwnd"></a>CMDIChildWnd::CMDIChildWnd  
 構築する呼び出し、`CMDIChildWnd`オブジェクトです。  
  
```  
CMDIChildWnd();
```  
  
### <a name="remarks"></a>コメント  
 呼び出す**作成**表示のウィンドウを作成します。  
  
### <a name="example"></a>例  
  例を参照してください[CMDIChildWnd::Create](#create)します。  
  
##  <a name="create"></a>CMDIChildWnd::Create  
 Windows MDI 子ウィンドウを作成し、接続するには、このメンバー関数を呼び出して、`CMDIChildWnd`オブジェクトです。  
  
```  
virtual BOOL Create(
    LPCTSTR lpszClassName,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_OVERLAPPEDWINDOW,  
    const RECT& rect = rectDefault,  
    CMDIFrameWnd* pParentWnd = NULL,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszClassName`  
 Windows クラスの名前を示す文字の null で終わる文字列へのポインター (、 [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576)構造) です。 クラス名に登録されている任意の名前を使用でき、 [AfxRegisterWndClass](http://msdn.microsoft.com/library/62c7d4b1-7a29-4abb-86f7-dec541659db0)グローバル関数。 必要があります**NULL**標準の`CMDIChildWnd`です。  
  
 `lpszWindowName`  
 ウィンドウの名前を表す文字の null で終わる文字列へのポインター。 タイトル バーのテキストとして使用します。  
  
 `dwStyle`  
 期間を指定[スタイル](../../mfc/reference/window-styles.md)属性です。 **WS_CHILD**スタイルが必要です。  
  
 `rect`  
 サイズとウィンドウの位置が含まれています。 `rectDefault`値により、サイズとの新しい位置を指定する Windows`CMDIChildWnd`します。  
  
 `pParentWnd`  
 ウィンドウの親を指定します。 場合**NULL**アプリケーションのメイン ウィンドウを使用します。  
  
 `pContext`  
 指定する[CCreateContext](../../mfc/reference/ccreatecontext-structure.md)構造体。 このパラメーターを指定できます**NULL**します。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 現在アクティブな MDI 子フレーム ウィンドウは親フレーム ウィンドウのキャプションを確認できます。 この機能はオフになっている、 **FWS_ADDTOTITLE**子フレーム ウィンドウのスタイル ビットです。  
  
 フレームワークが子ウィンドウを作成するユーザー コマンドでこのメンバー関数を呼び出すと、フレームワーク、`pContext`子ウィンドウをアプリケーションに正しく接続するパラメーターです。 呼び出すと**作成**、`pContext`できる**NULL**します。  
  
### <a name="example"></a>例  
 例 1:  
  
 [!code-cpp[NVC_MFCWindowing&#7;](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_1.cpp)]  
  
### <a name="example"></a>例  
 例 2:  
  
 [!code-cpp[NVC_MFCWindowing&#8;](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_2.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing&#9;](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_3.cpp)]  
  
##  <a name="getmdiframe"></a>CMDIChildWnd::GetMDIFrame  
 MDI 親フレームを返すには、この関数を呼び出します。  
  
```  
CMDIFrameWnd* GetMDIFrame();
```  
  
### <a name="return-value"></a>戻り値  
 MDI 親フレーム ウィンドウへのポインター。  
  
### <a name="remarks"></a>コメント  
 返されたフレームは、2 つの親から削除、`CMDIChildWnd`型のウィンドウの親であると**MDICLIENT**を管理する、`CMDIChildWnd`オブジェクトです。 呼び出す、 [GetParent](../../mfc/reference/cwnd-class.md#getparent)を返すメンバー関数、`CMDIChildWnd`オブジェクトの即時**MDICLIENT**一時と親`CWnd`ポインター。  
  
### <a name="example"></a>例  
  例を参照してください[CMDIFrameWnd::MDISetMenu](../../mfc/reference/cmdiframewnd-class.md#mdisetmenu)します。  
  
##  <a name="mdiactivate"></a>CMDIChildWnd::MDIActivate  
 MDI フレーム ウィンドウとは無関係に MDI 子ウィンドウをアクティブにするには、このメンバー関数を呼び出します。  
  
```  
void MDIActivate();
```  
  
### <a name="remarks"></a>コメント  
 フレームがアクティブになったときにも最後にアクティブになった子ウィンドウをアクティブ化されます。  
  
### <a name="example"></a>例  
  例を参照してください[CMDIFrameWnd::GetWindowMenuPopup](../../mfc/reference/cmdiframewnd-class.md#getwindowmenupopup)します。  
  
##  <a name="mdidestroy"></a>CMDIChildWnd::MDIDestroy  
 MDI 子ウィンドウを破棄するには、このメンバー関数を呼び出します。  
  
```  
void MDIDestroy();
```  
  
### <a name="remarks"></a>コメント  
 メンバー関数は、フレーム ウィンドウから、子ウィンドウのタイトルを削除し、子ウィンドウを非アクティブにします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing&#10;](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_4.cpp)]  
  
##  <a name="mdimaximize"></a>CMDIChildWnd::MDIMaximize  
 MDI 子ウィンドウを最大化するには、このメンバー関数を呼び出します。  
  
```  
void MDIMaximize();
```  
  
### <a name="remarks"></a>コメント  
 子ウィンドウが最大化されたときに、クライアント領域のフレーム ウィンドウのクライアント領域を入力するために Windows がサイズ変更します。 Windows は、ユーザーは、復元したり、子ウィンドウを閉じるようにフレームのメニュー バーで、子ウィンドウのコントロールのメニューを配置し、フレーム ウィンドウのタイトルに子ウィンドウのタイトルを追加します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing&#11;](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_5.cpp)]  
  
##  <a name="mdirestore"></a>CMDIChildWnd::MDIRestore  
 MDI 子ウィンドウを最大化または最小化されているサイズから復元するには、このメンバー関数を呼び出します。  
  
```  
void MDIRestore();
```  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCWindowing&#12;](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_6.cpp)]  
  
##  <a name="sethandles"></a>CMDIChildWnd::SetHandles  
 メニューとアクセラレータのリソース ハンドルを設定します。  
  
```  
void SetHandles(
    HMENU hMenu,  
    HACCEL hAccel);
```  
  
### <a name="parameters"></a>パラメーター  
 `hMenu`  
 メニュー リソースのハンドル。  
  
 `hAccel`  
 アクセラレータ リソースのハンドル。  
  
### <a name="remarks"></a>コメント  
 MDI 子ウィンドウのオブジェクトによって使用されているメニューのアクセラレータのリソースを設定するには、この関数を呼び出します。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル MDI](../../visual-cpp-samples.md)   
 [MFC のサンプルは](../../visual-cpp-samples.md)   
 [MFC サンプル SNAPVW](../../visual-cpp-samples.md)   
 [CFrameWnd クラス](../../mfc/reference/cframewnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [CMDIFrameWnd クラス](../../mfc/reference/cmdiframewnd-class.md)

