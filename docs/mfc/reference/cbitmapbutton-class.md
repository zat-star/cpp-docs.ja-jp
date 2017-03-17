---
title: "CBitmapButton クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CBitmapButton
- AFXEXT/CBitmapButton
- AFXEXT/CBitmapButton::CBitmapButton
- AFXEXT/CBitmapButton::AutoLoad
- AFXEXT/CBitmapButton::LoadBitmaps
- AFXEXT/CBitmapButton::SizeToContent
dev_langs:
- C++
helpviewer_keywords:
- buttons, bitmap
- CBitmapButton class
- bitmaps, button controls
ms.assetid: 9ad6cb45-c3c4-4fb1-96d3-1fe3df7bbcfc
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
ms.sourcegitcommit: 0b07f6b12e178d8e324313ea3b0f6de9ae7420c9
ms.openlocfilehash: 16d39cb380b75e6dcef71dda01626f120d5c12fb
ms.lasthandoff: 02/24/2017

---
# <a name="cbitmapbutton-class"></a>CBitmapButton クラス
ラベルがテキストではなくビットマップ イメージのプッシュ ボタン コントロールを作成します。  
  
## <a name="syntax"></a>構文  
  
```  
class CBitmapButton : public CButton  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CBitmapButton::CBitmapButton](#cbitmapbutton)|`CBitmapButton` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CBitmapButton::AutoLoad](#autoload)|ダイアログ ボックスのボタンのオブジェクトに関連付け、`CBitmapButton`クラス、名前で、ビットマップを読み込みおよびサイズをビットマップに合わせて ボタンをクリックします。|  
|[CBitmapButton::LoadBitmaps](#loadbitmaps)|アプリケーションのリソース ファイルから&1; つまたは複数の名前付きのビットマップ リソースを読み込み、オブジェクトへのビットマップをアタッチするには、オブジェクトを初期化します。|  
|[CBitmapButton::SizeToContent](#sizetocontent)|ビットマップが収まるように、ボタンのサイズを設定します。|  
  
## <a name="remarks"></a>コメント  
 `CBitmapButton`オブジェクトに含める最大&4; つのビットマップは、さまざまな状態と見なすことが、ボタンの画像を含む: 最新 (または通常) 下 (または選択した) フォーカス、および無効になっています。 最初のビットマップだけが必要です。その他はオプションです。  
  
 ビットマップ ボタンのイメージには、イメージ自体だけでなく、イメージを囲む境界線が含まれます。 罫線は、通常、ボタンの状態の表示中に役割を果たします。 たとえば、フォーカスのある状態のビットマップは、状態を表すが、枠線の太い直線には境界の破線の四角形の内側にあるように通常です。 ビットマップ、無効な状態を通常のと似ていますが (淡色表示のメニューの選択) のようなコントラストがはっきりして最新の状態にします。  
  
 あらゆる規模のこれらのビットマップを指定できますが、すべてものとして扱われますが、最新の状態のビットマップと同じサイズです。  
  
 さまざまなアプリケーションでは、ビットマップ イメージのさまざまな組み合わせを要求します。  
  
|上へ|[下へ移動]|Focused|無効|アプリケーション|  
|--------|----------|-------------|--------------|-----------------|  
|×||||ビットマップ|  
|×|×|||ボタンをクリックしてせず**WS_TABSTOP**スタイル|  
|×|×|×|×|すべての状態を持つダイアログ ボタン|  
|×|×|×||ダイアログ ボタン**WS_TABSTOP**スタイル|  
  
 ビットマップ ボタン コントロールを作成する設定、 **BS_OWNERDRAW**  ボタンがオーナー描画を指定するスタイル。 これが原因で送信する Windows、`WM_MEASUREITEM`と`WM_DRAWITEM`ボタン メッセージ フレームワークは、これらのメッセージを処理しするためのボタンの外観を管理します。  
  
### <a name="to-create-a-bitmap-button-control-in-a-windows-client-area"></a>ウィンドウのクライアント領域のビットマップ ボタン コントロールを作成するには  
  
1.  ボタンの&1; ~&4; 個のビットマップ イメージを作成します。  
  
2.  構築、 [CBitmapButton](#cbitmapbutton)オブジェクトです。  
  
3.  呼び出す、[作成](../../mfc/reference/cbutton-class.md#create)を Windows の button コントロールを作成し、添付、`CBitmapButton`オブジェクトです。  
  
4.  呼び出す、 [LoadBitmaps](#loadbitmaps)ビットマップ ボタンが構築した後に、ビットマップ リソースを読み込むためのメンバー関数。  
  
### <a name="to-include-a-bitmap-button-control-in-a-dialog-box"></a>ダイアログ ボックスにビットマップ ボタン コントロールを含める  
  
1.  ボタンの&1; ~&4; 個のビットマップ イメージを作成します。  
  
2.  オーナー描画ボタン、[ビットマップ] ボタンを配置を含むダイアログ テンプレートを作成します。 テンプレート内のボタンのサイズは関係ありません。  
  
3.  などの値に、ボタンのキャプションを設定" **MYIMAGE**"など、ボタンの記号の定義と**IDC_MYIMAGE**します。  
  
4.  アプリケーションのリソースのスクリプトでの各ボタンの文字"U"、"D"、"F"のいずれかの操作を追加することによって構築された ID を作成したイメージを提供または"X"(、重点を置いて、および無効になっています) についてのボタンのキャプションに使用される文字列に手順 3. です。 ボタンのキャプションを" **MYIMAGE**、"などの Id が必要" **MYIMAGEU**、"" **MYIMAGED**、"" **MYIMAGEF**、"と"**手順&3;**"。 **必要があります**二重引用符で囲んで、ビットマップの ID を指定します。 それ以外の場合、リソース エディターは、リソースへの整数を代入し、MFC は、イメージの読み込み時にできません。  
  
5.  アプリケーションのダイアログ クラスで (から派生した`CDialog`)、追加、`CBitmapButton`メンバー オブジェクトです。  
  
6.  `CDialog`オブジェクトの[OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog)ルーチンを呼び出し、`CBitmapButton`オブジェクトの[AutoLoad](#autoload)関数をボタンのコントロール ID をパラメーターとして使用して、`CDialog`オブジェクトの**この**ポインター。  
  
 Windows の通知メッセージを処理する**BN_CLICKED**、ビットマップ ボタン コントロールをその親によって送信された (から派生するクラスの通常**CDialog)**に追加、 `CDialog`-メッセージごとに、オブジェクトのメッセージ マップ エントリとメッセージ ハンドラー メンバー関数を派生します。 送信された通知、`CBitmapButton`オブジェクトは、によって送信されたものと同じ、 [CButton](../../mfc/reference/cbutton-class.md)オブジェクトです。  
  
 クラス[CToolBar](../../mfc/reference/ctoolbar-class.md)ビットマップ ボタンに別のアプローチを採用します。  
  
 詳細については`CBitmapButton`を参照してください[コントロール](../../mfc/controls-mfc.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 `CBitmapButton`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxext.h  
  
##  <a name="autoload"></a>CBitmapButton::AutoLoad  
 ダイアログ ボックスのボタンのオブジェクトに関連付け、`CBitmapButton`クラス、名前で、ビットマップを読み込みおよびサイズをビットマップに合わせて ボタンをクリックします。  
  
```  
BOOL AutoLoad(
    UINT nID,  
    CWnd* pParent);
```  
  
### <a name="parameters"></a>パラメーター  
 `nID`  
 ボタンのコントロールの id。  
  
 `pParent`  
 ボタンを所有するオブジェクトへのポインター。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 使用して、`AutoLoad`ビットマップ ボタンとして ダイアログ ボックスのオーナー描画ボタンを初期化します。 この関数を使用して手順については、「解説」で、`CBitmapButton`クラスです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCControlLadenDialog #&75;](../../mfc/codesnippet/cpp/cbitmapbutton-class_1.cpp)]  
  
##  <a name="cbitmapbutton"></a>CBitmapButton::CBitmapButton  
 
          `CBitmapButton` オブジェクトを作成します。  
  
```  
CBitmapButton();
```  
  
### <a name="remarks"></a>コメント  
 C++ で作成した後`CBitmapButton`オブジェクトで呼び出す[CButton::Create](../../mfc/reference/cbutton-class.md#create) Windows のボタン コントロールを作成し、添付、`CBitmapButton`オブジェクトです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCControlLadenDialog #&57;](../../mfc/codesnippet/cpp/cbitmapbutton-class_2.cpp)]  
  
##  <a name="loadbitmaps"></a>CBitmapButton::LoadBitmaps  
 識別された、リソースの名前または ID 番号を使用できない場合、ビットマップ イメージを読み込む場合、この関数を使用して、 `AutoLoad` 、たとえば、ダイアログ ボックスの一部ではないビットマップ ボタンを作成するために機能します。  
  
```  
BOOL LoadBitmaps(
    LPCTSTR lpszBitmapResource,  
    LPCTSTR lpszBitmapResourceSel = NULL,  
    LPCTSTR lpszBitmapResourceFocus = NULL,  
    LPCTSTR lpszBitmapResourceDisabled = NULL);

 
BOOL LoadBitmaps(
    UINT nIDBitmapResource,  
    UINT nIDBitmapResourceSel = 0,  
    UINT nIDBitmapResourceFocus = 0,  
    UINT nIDBitmapResourceDisabled = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 *lpszBitmapResource*  
 「を」状態またはビットマップ ボタンの通常のビットマップの名前を表す null で終わる文字列へのポインター。 必須です。  
  
 *lpszBitmapResourceSel*  
 「停止」状態またはビットマップのボタンの選択のビットマップの名前を含む null で終わる文字列へのポインター。 あります**NULL**します。  
  
 *lpszBitmapResourceFocus*  
 ビットマップのボタンのビットマップの名前を表す null で終わる文字列へのポインターには、状態が重点を置いています。 あります**NULL**します。  
  
 *lpszBitmapResourceDisabled*  
 ビットマップのボタンのビットマップの名前を表す null で終わる文字列へのポインターには、状態が無効になります。 あります**NULL**します。  
  
 *nIDBitmapResource*  
 ビットマップ リソースのビットマップ ボタンの通常の状態「を」リソースの ID 番号を指定します。 必須です。  
  
 *nIDBitmapResourceSel*  
 ビットマップのボタンの選択または「停止」状態は、ビットマップ リソースのリソース ID 番号を指定します。 0 である可能性があります。  
  
 *nIDBitmapResourceFocus*  
 フォーカスのある状態のビットマップ リソースのリソース ID 番号を指定します。 0 である可能性があります。  
  
 *nIDBitmapResourceDisabled*  
 ビットマップ ボタンの無効状態のビットマップ リソースのリソース ID 番号を指定します。 0 である可能性があります。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCControlLadenDialog #&58;](../../mfc/codesnippet/cpp/cbitmapbutton-class_3.cpp)]  
  
##  <a name="sizetocontent"></a>CBitmapButton::SizeToContent  
 ビットマップのサイズをビットマップ ボタンのサイズを変更するには、この関数を呼び出します。  
  
```  
void SizeToContent();
```  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCControlLadenDialog #&59;](../../mfc/codesnippet/cpp/cbitmapbutton-class_4.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル CTRLTEST](../../visual-cpp-samples.md)   
 [CButton クラス](../../mfc/reference/cbutton-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)


