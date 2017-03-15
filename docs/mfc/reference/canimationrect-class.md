---
title: "CAnimationRect クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationRect
- afxanimationcontroller/CAnimationRect
dev_langs:
- C++
helpviewer_keywords:
- CAnimationRect class
ms.assetid: 0294156d-241e-4a57-92b2-31234fe557d6
caps.latest.revision: 17
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
ms.sourcegitcommit: 73410ae17465880f455e5b15026f6cc010803c19
ms.openlocfilehash: f935884301030166572e356fffe88439f843f2c7
ms.lasthandoff: 02/24/2017

---
# <a name="canimationrect-class"></a>CAnimationRect クラス
四角形の&4; 辺をアニメーション化できる機能を実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CAnimationRect : public CAnimationBaseObject;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationRect::CAnimationRect](#canimationrect)|オーバーロードされます。 アニメーションの rect オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationRect::AddTransition](#addtransition)|左、上、右下隅の座標の遷移を追加します。|  
|[CAnimationRect::GetBottom](#getbottom)|下部の座標を表す CAnimationVariable へのアクセスを提供します。|  
|[CAnimationRect::GetDefaultValue](#getdefaultvalue)|四角形の境界の既定値を返します。|  
|[CAnimationRect::GetLeft](#getleft)|左座標を表す CAnimationVariable へのアクセスを提供します。|  
|[CAnimationRect::GetRight](#getright)|右の座標を表す CAnimationVariable へのアクセスを提供します。|  
|[CAnimationRect::GetTop](#gettop)|上部の座標を表す CAnimationVariable にアクセスを提供します。|  
|[CAnimationRect::GetValue](#getvalue)|現在の値を返します。|  
|[CAnimationRect::SetDefaultValue](#setdefaultvalue)|既定値を設定します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationRect::GetAnimationVariableList](#getanimationvariablelist)|一覧にカプセル化されたアニメーション変数を追加します。 (上書き[CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist))。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationRect::operator RECT](#operator_rect)|CAnimationRect を可変噴出口に変換します。|  
|[CAnimationRect::operator =](#operator_eq)|Rect を CAnimationRect に割り当てます。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationRect::m_bFixedSize](#m_bfixedsize)|四角形に固定サイズがあるかどうかを指定します。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationRect::m_bottomValue](#m_bottomvalue)|アニメーションの四角形の下端を表すカプセル化されたアニメーション変数をバインドします。|  
|[CAnimationRect::m_leftValue](#m_leftvalue)|アニメーションの四角形の左を表すアニメーションをカプセル化された変数がバインドされます。|  
|[CAnimationRect::m_rightValue](#m_rightvalue)|権限を表すアニメーションをカプセル化された変数は、アニメーションの四角形のバインド。|  
|[CAnimationRect::m_szInitial](#m_szinitial)|アニメーションの四角形の初期サイズを指定します。|  
|[CAnimationRect::m_topValue](#m_topvalue)|アニメーションの四角形の上部を表すカプセル化されたアニメーション変数をバインドします。|  
  
## <a name="remarks"></a>コメント  
 CAnimationRect クラスは、4 つの CAnimationVariable オブジェクトをカプセル化して、四角形のアプリケーションで表すことができます。 アプリケーションでこのクラスを使用するには、だけこのクラスのオブジェクトをインスタンス化、CAnimationController::AddAnimationObject を使用してアニメーション コント ローラーに追加および左、右の上端と下端の座標に適用される各移行につき AddTransition を呼び出します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 `CAnimationRect`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxanimationcontroller.h  
  
##  <a name="a-nameaddtransitiona--canimationrectaddtransition"></a><a name="addtransition"></a>CAnimationRect::AddTransition  
 左、上、右下隅の座標の遷移を追加します。  
  
```  
void AddTransition(
    CBaseTransition* pLeftTransition,  
    CBaseTransition* pTopTransition,  
    CBaseTransition* pRightTransition,  
    CBaseTransition* pBottomTransition);
```  
  
### <a name="parameters"></a>パラメーター  
 `pLeftTransition`  
 左側の遷移を指定します。  
  
 `pTopTransition`  
 上側の遷移を指定します。  
  
 `pRightTransition`  
 右側の遷移を指定します。  
  
 `pBottomTransition`  
 下の辺の遷移を指定します。  
  
### <a name="remarks"></a>コメント  
 各四角形の辺のアニメーション変数に適用する遷移の内部リストに指定された遷移を追加するには、この関数を呼び出します。 切り替え効果を追加すると、いないすぐに適用されるとなり内部リストに格納されています。 遷移 (特定の値のストーリー ボードへの追加) 適用 CAnimationController::AnimateGroup を呼び出すとします。 四角形の辺のいずれかの遷移を適用する必要としない場合は、NULL を渡すことができます。  
  
##  <a name="a-namecanimationrecta--canimationrectcanimationrect"></a><a name="canimationrect"></a>CAnimationRect::CAnimationRect  
 CAnimationRect オブジェクトを構築します。  
  
```  
CAnimationRect();

 
CAnimationRect(
    const CRect& rect,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);

 
CAnimationRect(
    const CPoint& pt,  
    const CSize& sz,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);

 
CAnimationRect(
    int nLeft,  
    int nTop,  
    int nRight,  
    int nBottom,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `rect`  
 既定の四角形を指定します。  
  
 `nGroupID`  
 グループ ID を指定します  
  
 `nObjectID`  
 オブジェクト ID を指定します  
  
 `dwUserData`  
 ユーザー定義データを指定します。  
  
 `pt`  
 左上隅の座標。  
  
 `sz`  
 四角形のサイズ。  
  
 `nLeft`  
 左側のバインドの座標を指定します。  
  
 `nTop`  
 バインドされている最上位の座標を指定します。  
  
 `nRight`  
 右側のバインドの座標を指定します。  
  
 `nBottom`  
 下限の座標を指定します。  
  
### <a name="remarks"></a>コメント  
 オブジェクトの構築の既定値で左、上、右下、およびオブジェクト ID およびグループ ID は、0 に設定されます。 SetDefaultValue と SetID を使用して実行時に後で変更できます。  
  
##  <a name="a-namegetanimationvariablelista--canimationrectgetanimationvariablelist"></a><a name="getanimationvariablelist"></a>CAnimationRect::GetAnimationVariableList  
 一覧にカプセル化されたアニメーション変数を追加します。  
  
```  
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*, 
    CAnimationVariable*>& lst);
```  
  
### <a name="parameters"></a>パラメーター  
 `lst`  
 関数から返されたときに、四角形の座標を表す&4; つの CAnimationVariable オブジェクトへのポインターを格納します。  
  
##  <a name="a-namegetbottoma--canimationrectgetbottom"></a><a name="getbottom"></a>CAnimationRect::GetBottom  
 下部の座標を表す CAnimationVariable へのアクセスを提供します。  
  
```  
CAnimationVariable& GetBottom();
```  
  
### <a name="return-value"></a>戻り値  
 下部の座標を表すカプセル化された CAnimationVariable への参照。  
  
### <a name="remarks"></a>コメント  
 下部にある座標を表す、基になる CAnimationVariable への直接アクセスを取得するには、このメソッドを呼び出すことができます。  
  
##  <a name="a-namegetdefaultvaluea--canimationrectgetdefaultvalue"></a><a name="getdefaultvalue"></a>CAnimationRect::GetDefaultValue  
 四角形の境界の既定値を返します。  
  
```  
CRect GetDefaultValue();
```  
  
### <a name="return-value"></a>戻り値  
 左、右、上と下の既定値を含む CRect 値です。  
  
### <a name="remarks"></a>コメント  
 コンス トラクターまたは SetDefaultValue で以前に設定された既定値を取得するには、この関数を呼び出します。  
  
##  <a name="a-namegetlefta--canimationrectgetleft"></a><a name="getleft"></a>CAnimationRect::GetLeft  
 左座標を表す CAnimationVariable へのアクセスを提供します。  
  
```  
CAnimationVariable& GetLeft();
```  
  
### <a name="return-value"></a>戻り値  
 左側の座標を表すカプセル化された CAnimationVariable への参照。  
  
### <a name="remarks"></a>コメント  
 左側の座標を表す、基になる CAnimationVariable への直接アクセスを取得するには、このメソッドを呼び出すことができます。  
  
##  <a name="a-namegetrighta--canimationrectgetright"></a><a name="getright"></a>CAnimationRect::GetRight  
 右の座標を表す CAnimationVariable へのアクセスを提供します。  
  
```  
CAnimationVariable& GetRight();
```  
  
### <a name="return-value"></a>戻り値  
 右側の座標を表すカプセル化された CAnimationVariable への参照。  
  
### <a name="remarks"></a>コメント  
 右側の座標を表す、基になる CAnimationVariable への直接アクセスを取得するには、このメソッドを呼び出すことができます。  
  
##  <a name="a-namegettopa--canimationrectgettop"></a><a name="gettop"></a>CAnimationRect::GetTop  
 上部の座標を表す CAnimationVariable にアクセスを提供します。  
  
```  
CAnimationVariable& GetTop();
```  
  
### <a name="return-value"></a>戻り値  
 上部の座標を表すカプセル化された CAnimationVariable への参照。  
  
### <a name="remarks"></a>コメント  
 上部の座標を表す、基になる CAnimationVariable への直接アクセスを取得するには、このメソッドを呼び出すことができます。  
  
##  <a name="a-namegetvaluea--canimationrectgetvalue"></a><a name="getvalue"></a>CAnimationRect::GetValue  
 現在の値を返します。  
  
```  
BOOL GetValue(CRect& rect);
```  
  
### <a name="parameters"></a>パラメーター  
 `rect`  
 出力します。 このメソッドが戻るとき、現在の値が含まれます。  
  
### <a name="return-value"></a>戻り値  
 現在の値の取得が成功した場合は TRUE。それ以外の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
 アニメーションの四角形の現在の値を取得するには、この関数を呼び出します。 このメソッドが失敗したか、基になる COM オブジェクトを左に、上、右、下は初期化されていません、rect には SetDefaultValue、コンス トラクターで以前に設定された既定値が含まれています。  
  
##  <a name="a-namembfixedsizea--canimationrectmbfixedsize"></a><a name="m_bfixedsize"></a>CAnimationRect::m_bFixedSize  
 四角形に固定サイズがあるかどうかを指定します。  
  
```  
BOOL m_bFixedSize;  
```  
  
### <a name="remarks"></a>コメント  
 このメンバーが true の場合は、右側の四角形のサイズが固定されてし、下部にある値が固定サイズに応じて左上を移動するたびに再計算します。 この値を簡単に四角形を画面上を移動する場合は TRUE に設定します。 ここでは右下隅の座標に適用される遷移は無視されます。 サイズは、オブジェクトの構築や、SetDefaultValue を呼び出すときに、内部的に格納されます。 既定では、このメンバーは FALSE に設定します。  
  
##  <a name="a-namembottomvaluea--canimationrectmbottomvalue"></a><a name="m_bottomvalue"></a>CAnimationRect::m_bottomValue  
 アニメーションの四角形の下端を表すカプセル化されたアニメーション変数をバインドします。  
  
```  
CAnimationVariable m_bottomValue;  
```  
  
##  <a name="a-namemleftvaluea--canimationrectmleftvalue"></a><a name="m_leftvalue"></a>CAnimationRect::m_leftValue  
 アニメーションの四角形の左を表すアニメーションをカプセル化された変数がバインドされます。  
  
```  
CAnimationVariable m_leftValue;  
```  
  
##  <a name="a-namemrightvaluea--canimationrectmrightvalue"></a><a name="m_rightvalue"></a>CAnimationRect::m_rightValue  
 権限を表すアニメーションをカプセル化された変数は、アニメーションの四角形のバインド。  
  
```  
CAnimationVariable m_rightValue;  
```  
  
##  <a name="a-namemszinitiala--canimationrectmszinitial"></a><a name="m_szinitial"></a>CAnimationRect::m_szInitial  
 アニメーションの四角形の初期サイズを指定します。  
  
```  
CSize m_szInitial;  
```  
  
##  <a name="a-namemtopvaluea--canimationrectmtopvalue"></a><a name="m_topvalue"></a>CAnimationRect::m_topValue  
 アニメーションの四角形の上部を表すカプセル化されたアニメーション変数をバインドします。  
  
```  
CAnimationVariable m_topValue;  
```  
  
##  <a name="a-nameoperatorrecta--canimationrectoperator-rect"></a><a name="operator_rect"></a>CAnimationRect::operator RECT  
 CAnimationRect を可変噴出口に変換します。  
  
```  
operator RECT();
```   
  
### <a name="return-value"></a>戻り値  
 可変噴出口四角形のアニメーションの現在の値  
  
### <a name="remarks"></a>コメント  
 この関数は、GetValue を内部的に呼び出します。 GetValue 何らかの理由で失敗すると、返された RECT は、すべての四角形の座標の既定値が含まれます。  
  
##  <a name="a-nameoperatoreqa--canimationrectoperator"></a><a name="operator_eq"></a>CAnimationRect::operator =  
 Rect を CAnimationRect に割り当てます。  
  
```  
void operator=(const RECT& rect);
```  
  
### <a name="parameters"></a>パラメーター  
 `rect`  
 アニメーションの四角形の新しい値。  
  
### <a name="remarks"></a>コメント  
 お勧めするアニメーションの開始する前にこの演算子は、作成された場合は、色の要素の基になる COM オブジェクトを作成し直さ SetDefaultValue を呼び出すためです。 このアニメーション オブジェクト (ValueChanged または IntegerValueChanged) イベントをサブスクライブしている場合は、これらのイベントを再度有効にする必要があります。  
  
##  <a name="a-namesetdefaultvaluea--canimationrectsetdefaultvalue"></a><a name="setdefaultvalue"></a>CAnimationRect::SetDefaultValue  
 既定値を設定します。  
  
```  
void SetDefaultValue(const CRect& rect);
```  
  
### <a name="parameters"></a>パラメーター  
 `rect`  
 左、上、右および下の新しい既定値を指定します。  
  
### <a name="remarks"></a>コメント  
 この関数を使用すると、アニメーション オブジェクトを既定値を設定できます。 このメソッドは、四角形の境界内に既定値を割り当てます。 作成された場合は、基になる COM オブジェクトも再作成します。 このアニメーション オブジェクト (ValueChanged または IntegerValueChanged) イベントをサブスクライブしている場合は、これらのイベントを再度有効にする必要があります。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

