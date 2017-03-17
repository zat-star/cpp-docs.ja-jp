---
title: "CProgressCtrl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CProgressCtrl
- AFXCMN/CProgressCtrl
- AFXCMN/CProgressCtrl::CProgressCtrl
- AFXCMN/CProgressCtrl::Create
- AFXCMN/CProgressCtrl::CreateEx
- AFXCMN/CProgressCtrl::GetBarColor
- AFXCMN/CProgressCtrl::GetBkColor
- AFXCMN/CProgressCtrl::GetPos
- AFXCMN/CProgressCtrl::GetRange
- AFXCMN/CProgressCtrl::GetState
- AFXCMN/CProgressCtrl::GetStep
- AFXCMN/CProgressCtrl::OffsetPos
- AFXCMN/CProgressCtrl::SetBarColor
- AFXCMN/CProgressCtrl::SetBkColor
- AFXCMN/CProgressCtrl::SetMarquee
- AFXCMN/CProgressCtrl::SetPos
- AFXCMN/CProgressCtrl::SetRange
- AFXCMN/CProgressCtrl::SetState
- AFXCMN/CProgressCtrl::SetStep
- AFXCMN/CProgressCtrl::StepIt
dev_langs:
- C++
helpviewer_keywords:
- CProgressCtrl class
- progress controls [C++], CProgressCtrl class
- Internet Explorer 4.0 common controls
ms.assetid: 222630f4-1598-4026-8198-51649b1192ab
caps.latest.revision: 25
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
ms.openlocfilehash: 6c0e9bc16f88018c9f258504924670cc2be31d28
ms.lasthandoff: 02/24/2017

---
# <a name="cprogressctrl-class"></a>CProgressCtrl クラス
Windows コモン プログレス バー コントロールの機能が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class CProgressCtrl : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CProgressCtrl::CProgressCtrl](#cprogressctrl)|`CProgressCtrl` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CProgressCtrl::Create](#create)|進行状況バー コントロールを作成し、それをアタッチ、`CProgressCtrl`オブジェクトです。|  
|[CProgressCtrl::CreateEx](#createex)|指定した Windows 拡張スタイルを使用して進行状況コントロールを作成し、それにアタッチ、`CProgressCtrl`オブジェクトです。|  
|[CProgressCtrl::GetBarColor](#getbarcolor)|現在の進行状況バー コントロールの進行状況インジケーターのバーの色を取得します。|  
|[CProgressCtrl::GetBkColor](#getbkcolor)|現在の進行状況バーの背景色を取得します。|  
|[CProgressCtrl::GetPos](#getpos)|進行状況バーの現在位置を取得します。|  
|[CProgressCtrl::GetRange](#getrange)|進行状況バー コントロールの範囲の下限と上限の制限を取得します。|  
|[CProgressCtrl::GetState](#getstate)|現在の進行状況バー コントロールの状態を取得します。|  
|[CProgressCtrl::GetStep](#getstep)|現在の進行状況バー コントロールの進行状況バーの増分値を取得します。|  
|[CProgressCtrl::OffsetPos](#offsetpos)|指定された増分値で進行状況バー コントロールの現在位置を進め、新しい位置を反映するバーを再描画します。|  
|[CProgressCtrl::SetBarColor](#setbarcolor)|現在の進行状況バー コントロールの進行状況インジケーターのバーの色を設定します。|  
|[CProgressCtrl::SetBkColor](#setbkcolor)|進行状況バーの背景色を設定します。|  
|[CProgressCtrl::SetMarquee](#setmarquee)|現在の進行状況バー コントロールのマーキー モードをオンまたはオフになります。|  
|[CProgressCtrl::SetPos](#setpos)|進行状況バー コントロールの現在位置を設定し、新しい位置を反映するバーを再描画します。|  
|[CProgressCtrl::SetRange](#setrange)|進行状況バー コントロールの最小値と最大の範囲を設定し、新しい範囲を反映するように、バーを再描画します。|  
|[CProgressCtrl::SetState](#setstate)|現在の進行状況バー コントロールの状態を設定します。|  
|[増分](#setstep)|進行状況バー コントロールの増分を指定します。|  
|[CProgressCtrl::StepIt](#stepit)|増分の進行状況バー コントロールの現在位置を進めます (を参照してください[SetStep](#setstep)) し、新しい位置を反映するように、バーを再描画します。|  
  
## <a name="remarks"></a>コメント  
 進行状況バー コントロールは、アプリケーションは、時間のかかる操作の進行状況を示すために使用できるウィンドウです。 左から右、システムで強調表示色として処理の進行状況に徐々 に塗りつぶされた四角形で構成されます。  
  
 進行状況バー コントロールでは、範囲と現在の位置を持ちます。 範囲は、操作の合計実行時間を表し、現在の位置は、アプリケーションが行った操作の完了に向けた進行状況を表します。 ウィンドウ プロシージャは、範囲と現在の位置を使用して、強調表示色で塗りつぶすに進行状況バーの割合を決定します。 範囲と現在位置の値が符号付き整数として表されるので現在位置の値の可能な範囲は â €"2,147, 483,648 を 2,147, 483,647 包括的です。  
  
 使用する方法について`CProgressCtrl`を参照してください[コントロール](../../mfc/controls-mfc.md)と[を使用して CProgressCtrl](../../mfc/using-cprogressctrl.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CProgressCtrl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcmn.h  
  
##  <a name="cprogressctrl"></a>CProgressCtrl::CProgressCtrl  
 `CProgressCtrl` オブジェクトを構築します。  
  
```  
CProgressCtrl();
```  
  
### <a name="remarks"></a>コメント  
 構築した後、`CProgressCtrl`オブジェクトで呼び出す`CProgressCtrl::Create`進行状況バー コントロールを作成します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CProgressCtrl&#1;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_1.cpp)]  
  
##  <a name="create"></a>CProgressCtrl::Create  
 進行状況バー コントロールを作成し、それをアタッチ、`CProgressCtrl`オブジェクトです。  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwStyle`  
 進行状況バー コントロールのスタイルを指定します。 ウィンドウ stylesdescribed 内の任意の組み合わせを適用[CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679)で、 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]、だけでなく、以下のプログレス バー コントロールのスタイルをコントロールにします。  
  
- `PBS_VERTICAL`表示は、進行状況を垂直方向に、上下からです。 このフラグが進行状況バー コントロールは、右側に水平方向に、左を表示します。  
  
- `PBS_SMOOTH`段階的な移行がスムーズに進行状況バー コントロールの入力が表示されます。 このフラグを設定せず、コントロールがブロックで入力されます。  
  
 `rect`  
 進行状況バー コントロールのサイズと位置を指定します。 いずれかになります、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体。 指定された座標のクライアント領域を基準と、コントロールは、子ウィンドウをある必要があるため、`pParentWnd`です。  
  
 `pParentWnd`  
 通常、進行状況バー コントロールの親ウィンドウの指定、`CDialog`です。 ことはできません**NULL です。**  
  
 `nID`  
 進行状況バー コントロールの ID を指定します  
  
### <a name="return-value"></a>戻り値  
 **TRUE**場合、`CProgressCtrl`オブジェクトが正常に作成された以外の場合**FALSE**します。  
  
### <a name="remarks"></a>コメント  
 構築する、 `CProgressCtrl`&2; つのステップ内のオブジェクト。 最初に、作成するコンス トラクターを呼び出す、`CProgressCtrl`オブジェクト、し、呼び出す**作成**、進行状況バー コントロールを作成します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CProgressCtrl&#2;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_2.cpp)]  
  
##  <a name="createex"></a>CProgressCtrl::CreateEx  
 コントロール (子ウィンドウ) を作成し、関連付けます、`CProgressCtrl`オブジェクトです。  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwExStyle`  
 作成されるコントロールの拡張スタイルを指定します。 拡張ウィンドウ スタイルの一覧は、次を参照してください。、`dwExStyle`パラメーター [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `dwStyle`  
 進行状況バー コントロールのスタイルを指定します。 ウィンドウ スタイル」に記載の任意の組み合わせを適用[CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `rect`  
 参照、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造体のサイズとのクライアント座標で、作成するウィンドウの位置を表す`pParentWnd`します。  
  
 `pParentWnd`  
 コントロールの親ウィンドウへのポインター。  
  
 `nID`  
 コントロールの子ウィンドウの id。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 使用`CreateEx`の代わりに[作成](#create)、Windows 拡張スタイルの先頭で指定された、Windows の拡張スタイルを適用する**WS_EX**します。  
  
##  <a name="getbarcolor"></a>CProgressCtrl::GetBarColor  
 現在の進行状況バー コントロールの進行状況インジケーターのバーの色を取得します。  
  
```  
COLORREF GetBarColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 として表される現在の進行状況バーの色、 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)値、または`CLR_DEFAULT`場合、進行状況インジケーターのバーの色は既定の色。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [PBM_GETBARCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760826)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="getbkcolor"></a>CProgressCtrl::GetBkColor  
 現在の進行状況バーの背景色を取得します。  
  
```  
COLORREF GetBkColor() const;  
```  
  
### <a name="return-value"></a>戻り値  
 として表される現在の進行状況バーの背景色、 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)値。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [PBM_GETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760828)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="getpos"></a>CProgressCtrl::GetPos  
 進行状況バーの現在位置を取得します。  
  
```  
int GetPos();
```  
  
### <a name="return-value"></a>戻り値  
 進行状況バー コントロールの位置。  
  
### <a name="remarks"></a>コメント  
 進行状況バー コントロールの位置が画面で、物理的な場所ではありませんではなく、上部と下部の範囲に示されている[SetRange](#setrange)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CProgressCtrl&#3;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_3.cpp)]  
  
##  <a name="getrange"></a>CProgressCtrl::GetRange  
 現在の下限と上限の制限または進行状況バー コントロールの範囲を取得します。  
  
```  
void GetRange(
    int& nLower,  
    int& nUpper);
```  
  
### <a name="parameters"></a>パラメーター  
 `nLower`  
 進行状況バー コントロールの下限値を受け取る整数への参照。  
  
 `nUpper`  
 進行状況バー コントロールの数の上限を受け取る整数への参照。  
  
### <a name="remarks"></a>コメント  
 この関数によって参照される整数への下限と上限値の範囲の値をコピーする`nLower`と`nUpper`、それぞれします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CProgressCtrl&4;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_4.cpp)]  
  
##  <a name="getstate"></a>CProgressCtrl::GetState  
 現在の進行状況バー コントロールの状態を取得します。  
  
```  
int GetState() const;  
```  
  
### <a name="return-value"></a>戻り値  
 次の値の&1; つは、現在の進行状況バー コントロールの状態:  
  
|値|状態|  
|-----------|-----------|  
|`PBST_NORMAL`|処理中|  
|`PBST_ERROR`|Error|  
|`PBST_PAUSED`|Paused|  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [PBM_GETSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760834)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 次のコード例では、進行状況バー コントロールにプログラムでアクセスするために使用される `m_progressCtrl` 変数を定義します。 この変数は次の例で使用されています。  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s&#1;9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]  
  
### <a name="example"></a>例  
 次のコード例では、現在の進行状況バー コントロールの状態を取得します。  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s&#1;5](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_6.cpp)]  
  
##  <a name="getstep"></a>CProgressCtrl::GetStep  
 現在の進行状況バー コントロールの進行状況バーの増分値を取得します。  
  
```  
int GetStep() const;  
```  
  
### <a name="return-value"></a>戻り値  
 進行状況バーの増分値。  
  
### <a name="remarks"></a>コメント  
 増分する量は、呼び出しを[CProgressCtrl::StepIt](#stepit)進行状況バーの現在位置が増加します。  
  
 このメソッドは、送信、 [PBM_GETSTEP](http://msdn.microsoft.com/library/windows/desktop/bb760836)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 次のコード例では、進行状況バー コントロールにプログラムでアクセスするために使用される `m_progressCtrl` 変数を定義します。 この変数は次の例で使用されています。  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s&#1;9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]  
  
### <a name="example"></a>例  
 次のコード例では、現在の進行状況バー コントロールの増分値を取得します。  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s&#1;3](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_7.cpp)]  
  
##  <a name="offsetpos"></a>CProgressCtrl::OffsetPos  
 指定された増分値で、進行状況バー コントロールの現在位置を進めます`nPos`し、新しい位置を反映するように、バーを再描画します。  
  
```  
int OffsetPos(int nPos);
```  
  
### <a name="parameters"></a>パラメーター  
 `nPos`  
 位置を進める量。  
  
### <a name="return-value"></a>戻り値  
 進行状況バー コントロールの前の位置。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CProgressCtrl&#5;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_8.cpp)]  
  
##  <a name="setbarcolor"></a>CProgressCtrl::SetBarColor  
 現在の進行状況バー コントロールの進行状況インジケーターのバーの色を設定します。  
  
```  
COLORREF SetBarColor(COLORREF clrBar);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `clrBar`|A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)新しい進行状況インジケーターのバーの色を指定する値。 指定`CLR_DEFAULT`既定の色を使用する進行状況バーが発生します。|  
  
### <a name="return-value"></a>戻り値  
 として表される、進行状況インジケーターのバーの前のカラー、 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)値、または`CLR_DEFAULT`進行状況インジケーターのバーの色が既定の色である場合。  
  
### <a name="remarks"></a>コメント  
 `SetBarColor`メソッドは、進行状況バーの場合にのみ、色を設定、 [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)][テーマ](https://msdn.microsoft.com/library/windows/desktop/hh270423.aspx)が有効でないです。  
  
 このメソッドは、送信、 [PBM_SETBARCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb760838)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 次のコード例では、進行状況バー コントロールにプログラムでアクセスするために使用される `m_progressCtrl` 変数を定義します。 この変数は次の例で使用されています。  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s&#1;9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]  
  
### <a name="example"></a>例  
 次のコード例では、進行状況バーの色を赤、緑、青、または既定値に変更します。  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_9.cpp)]  
  
##  <a name="setbkcolor"></a>CProgressCtrl::SetBkColor  
 進行状況バーの背景色を設定します。  
  
```  
COLORREF SetBkColor(COLORREF clrNew);
```  
  
### <a name="parameters"></a>パラメーター  
 `clrNew`  
 A **COLORREF**新しい背景色を指定する値。 指定の`CLR_DEFAULT`進行状況バーの既定の背景色を使用する値。  
  
### <a name="return-value"></a>戻り値  
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449)直前の背景色を示す値、または**とき**場合は、既定の色の背景色です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CProgressCtrl&6;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_10.cpp)]  
  
##  <a name="setmarquee"></a>CProgressCtrl::SetMarquee  
 現在の進行状況バー コントロールのマーキー モードをオンまたはオフになります。  
  
```  
BOOL SetMarquee(
    BOOL fMarqueeMode,   
    int nInterval);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `fMarqueeMode`|`true`、マーキー モードを有効にするか、`false`マーキー モードをオフにします。|  
|[入力] `nInterval`|マーキー アニメーションの更新間隔をミリ秒単位の時間。|  
  
### <a name="return-value"></a>戻り値  
 このメソッドは常に `true` を返します。  
  
### <a name="remarks"></a>コメント  
 マーキー モードがオンになっていると、進行状況バーがアニメーション化されようにスクロール シアター マーキー サインオンします。  
  
 このメソッドは、送信、 [PBM_SETMARQUEE](http://msdn.microsoft.com/library/windows/desktop/bb760842)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 次のコード例では、進行状況バー コントロールにプログラムでアクセスするために使用される `m_progressCtrl` 変数を定義します。 この変数は次の例で使用されています。  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s&#1;9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]  
  
### <a name="example"></a>例  
 次のコード例では、開始時およびマーキー スクロール アニメーションを停止します。  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s&#1;2](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_11.cpp)]  
  
##  <a name="setpos"></a>CProgressCtrl::SetPos  
 コントロールの現在の位置で指定されたバーの進行状況の設定`nPos`し、新しい位置を反映するように、バーを再描画します。  
  
```  
int SetPos(int nPos);
```  
  
### <a name="parameters"></a>パラメーター  
 `nPos`  
 進行状況バー コントロールの新しい位置。  
  
### <a name="return-value"></a>戻り値  
 進行状況バー コントロールの前の位置。  
  
### <a name="remarks"></a>コメント  
 進行状況バー コントロールの位置が画面で、物理的な場所ではありませんではなく、上部と下部の範囲に示されている[SetRange](#setrange)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CProgressCtrl&#7;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_12.cpp)]  
  
##  <a name="setrange"></a>CProgressCtrl::SetRange  
 進行状況バーのコントロールの範囲の上限と下限を設定し、新しい範囲を反映するように、バーを再描画します。  
  
```  
void SetRange(
    short nLower,  
    short nUpper);

 
void SetRange32(
    int nLower,  
    int nUpper);
```  
  
### <a name="parameters"></a>パラメーター  
 `nLower`  
 範囲の下限を指定 (既定値は&0;)。  
  
 `nUpper`  
 範囲の上限を指定します (既定値は 100)。  
  
### <a name="remarks"></a>コメント  
 メンバー関数は、`SetRange32`プログレス コントロールの 32 ビットの範囲を設定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CProgressCtrl&#8;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_13.cpp)]  
  
##  <a name="setstate"></a>CProgressCtrl::SetState  
 現在の進行状況バー コントロールの状態を設定します。  
  
```  
int SetState(int iState);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `iState`|進行状況バーに設定する状態。 次のいずれかの値を使用します。<br /><br /> - `PBST_NORMAL`-進行中<br />- `PBST_ERROR`-エラー<br />- `PBST_PAUSED`-一時停止|  
  
### <a name="return-value"></a>戻り値  
 現在の進行状況バー コントロールの直前の状態。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [PBM_SETSTATE](http://msdn.microsoft.com/library/windows/desktop/bb760850)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 次のコード例では、進行状況バー コントロールにプログラムでアクセスするために使用される `m_progressCtrl` 変数を定義します。 この変数は次の例で使用されています。  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s&#1;9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]  
  
### <a name="example"></a>例  
 次のコード例は、現在の進行状況バー コントロールの状態を一時停止または処理中に設定します。  
  
 [!code-cpp[NVC_MFC_CProgressCtrl_s1&4;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_14.cpp)]  
  
##  <a name="setstep"></a>増分  
 進行状況バー コントロールの増分を指定します。  
  
```  
int SetStep(int nStep);
```  
  
### <a name="parameters"></a>パラメーター  
 *nStep*  
 新しい増分値です。  
  
### <a name="return-value"></a>戻り値  
 直前の増分します。  
  
### <a name="remarks"></a>コメント  
 増分値は、大量の呼び出し`CProgressCtrl::StepIt`進行状況が向上バーの現在の位置。  
  
 既定の増分は 10 です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CProgressCtrl&#9;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_15.cpp)]  
  
##  <a name="stepit"></a>CProgressCtrl::StepIt  
 増分の進行状況バー コントロールの現在位置を進め、新しい位置を反映するバーを再描画します。  
  
```  
int StepIt();
```  
  
### <a name="return-value"></a>戻り値  
 進行状況バー コントロールの前の位置。  
  
### <a name="remarks"></a>コメント  
 増分値が設定されて、`CProgressCtrl::SetStep`メンバー関数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CProgressCtrl&#10;](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_16.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル CMNCTRL2](../../visual-cpp-samples.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)



