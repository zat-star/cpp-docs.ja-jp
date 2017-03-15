---
title: "CAnimationColor クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationColor
- afxanimationcontroller/CAnimationColor
dev_langs:
- C++
helpviewer_keywords:
- CAnimationColor class
ms.assetid: 88bfabd4-efeb-4652-87e8-304253d8e48c
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: e053986737b8e62103666787b99b01cbf19cdc60
ms.lasthandoff: 02/24/2017

---
# <a name="canimationcolor-class"></a>CAnimationColor クラス
赤、緑、および青の各色要素をアニメーション化できる機能を実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CAnimationColor : public CAnimationBaseObject;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationColor::CAnimationColor](#canimationcolor)|オーバーロードされます。 アニメーションの色のオブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationColor::AddTransition](#addtransition)|赤、緑、および青のコンポーネントの遷移を追加します。|  
|[CAnimationColor::GetB](#getb)|青の要素を表す CAnimationVariable へのアクセスを提供します。|  
|[CAnimationColor::GetDefaultValue](#getdefaultvalue)|色の要素の既定値を返します。|  
|[CAnimationColor::GetG](#getg)|緑の成分を表す CAnimationVariable へのアクセスを提供します。|  
|[CAnimationColor::GetR](#getr)|赤の要素を表す CAnimationVariable へのアクセスを提供します。|  
|[CAnimationColor::GetValue](#getvalue)|現在の値を返します。|  
|[CAnimationColor::SetDefaultValue](#setdefaultvalue)|既定値を設定します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationColor::GetAnimationVariableList](#getanimationvariablelist)|一覧にカプセル化されたアニメーション変数を追加します。 (上書き[CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist))。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationColor::operator COLORREF](#operator_colorref)||  
|[CAnimationColor::operator =](#operator_eq)|CAnimationColor に色を割り当てます。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationColor::m_bValue](#m_bvalue)|アニメーションの色の青の要素を表すアニメーションをカプセル化された変数です。|  
|[CAnimationColor::m_gValue](#m_gvalue)|アニメーションの色の緑の成分を表すアニメーションをカプセル化された変数です。|  
|[CAnimationColor::m_rValue](#m_rvalue)|アニメーションの色の赤の要素を表すアニメーションをカプセル化された変数です。|  
  
## <a name="remarks"></a>コメント  
 CAnimationColor クラスでは、3 つの CAnimationVariable オブジェクトをカプセル化して、色アプリケーションで表すことができます。 たとえば、画面上の任意のオブジェクトの色をアニメーション化するこのクラスを使用できます (テキストの色のように背景色など)。 アプリケーションでこのクラスを使用するには、このクラスのオブジェクトをインスタンス化、CAnimationController::AddAnimationObject を使用してアニメーション コント ローラーに追加し、説明しました赤、緑、および青のコンポーネントに適用される各移行につき AddTransition を呼び出します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 `CAnimationColor`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxanimationcontroller.h  
  
##  <a name="a-nameaddtransitiona--canimationcoloraddtransition"></a><a name="addtransition"></a>CAnimationColor::AddTransition  
 赤、緑、および青のコンポーネントの遷移を追加します。  
  
```  
void AddTransition(
    CBaseTransition* pRTransition,  
    CBaseTransition* pGTransition,  
    CBaseTransition* pBTransition);
```  
  
### <a name="parameters"></a>パラメーター  
 `pRTransition`  
 赤の成分に移行します。  
  
 `pGTransition`  
 緑の成分に移行します。  
  
 `pBTransition`  
 青の成分に移行します。  
  
### <a name="remarks"></a>コメント  
 色要素を表すアニメーション変数に適用する遷移の内部リストに指定された遷移を追加するには、この関数を呼び出します。 切り替え効果を追加すると、いないすぐに適用されるとなり内部リストに格納されています。 遷移 (特定の値のストーリー ボードへの追加) 適用 CAnimationController::AnimateGroup を呼び出すとします。 色の要素のいずれかに遷移を適用する必要としない場合は、NULL を渡すことができます。  
  
##  <a name="a-namecanimationcolora--canimationcolorcanimationcolor"></a><a name="canimationcolor"></a>CAnimationColor::CAnimationColor  
 CAnimationColor オブジェクトを構築します。  
  
```  
CAnimationColor();
 
CAnimationColor(
    COLORREF color,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `color`  
 既定の色を指定します。  
  
 `nGroupID`  
 グループ ID を指定します  
  
 `nObjectID`  
 オブジェクト ID を指定します  
  
 `dwUserData`  
 ユーザー定義データを指定します。  
  
### <a name="remarks"></a>コメント  
 オブジェクトの構築の既定値で赤、緑、青、オブジェクト ID およびグループ ID は、0 に設定されます。 SetDefaultValue と SetID を使用して実行時に後で変更できます。  
  
##  <a name="a-namegetanimationvariablelista--canimationcolorgetanimationvariablelist"></a><a name="getanimationvariablelist"></a>CAnimationColor::GetAnimationVariableList  
 一覧にカプセル化されたアニメーション変数を追加します。  
  
```  
virtual void GetAnimationVariableList(CList<CAnimationVariable*>& lst);
```  
  
### <a name="parameters"></a>パラメーター  
 `lst`  
 関数から返されたときに、赤、緑、青のコンポーネントを表す&3; つの CAnimationVariable オブジェクトへのポインターを格納します。  
  
##  <a name="a-namegetba--canimationcolorgetb"></a><a name="getb"></a>CAnimationColor::GetB  
 青の要素を表す CAnimationVariable へのアクセスを提供します。  
  
```  
CAnimationVariable& GetB();
```  
  
### <a name="return-value"></a>戻り値  
 青の要素を表すカプセル化された CAnimationVariable への参照。  
  
### <a name="remarks"></a>コメント  
 青の要素を表す、基になる CAnimationVariable への直接アクセスを取得するには、このメソッドを呼び出すことができます。  
  
##  <a name="a-namegetdefaultvaluea--canimationcolorgetdefaultvalue"></a><a name="getdefaultvalue"></a>CAnimationColor::GetDefaultValue  
 色の要素の既定値を返します。  
  
```  
COLORREF GetDefaultValue();
```  
  
### <a name="return-value"></a>戻り値  
 RGB コンポーネントの既定値を表す値を格納します。  
  
### <a name="remarks"></a>コメント  
 コンス トラクターまたは SetDefaultValue で以前に設定された既定値を取得するには、この関数を呼び出します。  
  
##  <a name="a-namegetga--canimationcolorgetg"></a><a name="getg"></a>CAnimationColor::GetG  
 緑の成分を表す CAnimationVariable へのアクセスを提供します。  
  
```  
CAnimationVariable& GetG();
```  
  
### <a name="return-value"></a>戻り値  
 カプセル化された CAnimationVariable を表す緑の要素への参照。  
  
### <a name="remarks"></a>コメント  
 基になる CAnimationVariable を表す緑の要素への直接アクセスを取得するには、このメソッドを呼び出すことができます。  
  
##  <a name="a-namegetra--canimationcolorgetr"></a><a name="getr"></a>CAnimationColor::GetR  
 赤の要素を表す CAnimationVariable へのアクセスを提供します。  
  
```  
CAnimationVariable& GetR();
```  
  
### <a name="return-value"></a>戻り値  
 赤の要素を表すカプセル化された CAnimationVariable への参照。  
  
### <a name="remarks"></a>コメント  
 赤の要素を表す、基になる CAnimationVariable への直接アクセスを取得するには、このメソッドを呼び出すことができます。  
  
##  <a name="a-namegetvaluea--canimationcolorgetvalue"></a><a name="getvalue"></a>CAnimationColor::GetValue  
 現在の値を返します。  
  
```  
BOOL GetValue(COLORREF& color);
```  
  
### <a name="parameters"></a>パラメーター  
 `color`  
 出力します。 このメソッドが戻るとき、現在の値が含まれます。  
  
### <a name="return-value"></a>戻り値  
 現在の値の取得が成功した場合は TRUE。それ以外の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
 アニメーションの色の現在の値を取得するには、この関数を呼び出します。 このメソッドは失敗、または色の要素の基になる COM オブジェクトが初期化されていない、色には、コンス トラクターまたは SetDefaultValue によって以前に設定された既定値が含まれています。  
  
##  <a name="a-namembvaluea--canimationcolormbvalue"></a><a name="m_bvalue"></a>CAnimationColor::m_bValue  
 アニメーションの色の青の要素を表すアニメーションをカプセル化された変数です。  
  
```  
CAnimationVariable m_bValue;  
```  
  
##  <a name="a-namemgvaluea--canimationcolormgvalue"></a><a name="m_gvalue"></a>CAnimationColor::m_gValue  
 アニメーションの色の緑の成分を表すアニメーションをカプセル化された変数です。  
  
```  
CAnimationVariable m_gValue;  
```  
  
##  <a name="a-namemrvaluea--canimationcolormrvalue"></a><a name="m_rvalue"></a>CAnimationColor::m_rValue  
 アニメーションの色の赤の要素を表すアニメーションをカプセル化された変数です。  
  
```  
CAnimationVariable m_rValue;  
```  
  
##  <a name="a-nameoperatorcolorrefa--canimationcoloroperator-colorref"></a><a name="operator_colorref"></a>CAnimationColor::operator COLORREF  
  
```  
operator COLORREF();
```   
  
### <a name="return-value"></a>戻り値  
  
##  <a name="a-nameoperatoreqa--canimationcoloroperator"></a><a name="operator_eq"></a>CAnimationColor::operator =  
 CAnimationColor に色を割り当てます。  
  
```  
void operator=(COLORREF color);
```  
  
### <a name="parameters"></a>パラメーター  
 `color`  
 新しい値のアニメーションの色を指定します。  
  
### <a name="remarks"></a>コメント  
 お勧めするアニメーションの開始する前にこの演算子は、作成された場合は、色の要素の基になる COM オブジェクトを作成し直さ SetDefaultValue を呼び出すためです。 このアニメーション オブジェクト (ValueChanged または IntegerValueChanged) イベントをサブスクライブしている場合は、これらのイベントを再度有効にする必要があります。  
  
##  <a name="a-namesetdefaultvaluea--canimationcolorsetdefaultvalue"></a><a name="setdefaultvalue"></a>CAnimationColor::SetDefaultValue  
 既定値を設定します。  
  
```  
void SetDefaultValue(COLORREF color);
```  
  
### <a name="parameters"></a>パラメーター  
 `color`  
 赤、緑、青のコンポーネントの新しい既定値を指定します。  
  
### <a name="remarks"></a>コメント  
 この関数を使用すると、アニメーション オブジェクトを既定値を設定できます。 このメソッドは、既定値をアニメーションの色の色成分に代入します。 作成された場合は、基になる COM オブジェクトも再作成します。 このアニメーション オブジェクト (ValueChanged または IntegerValueChanged) イベントをサブスクライブしている場合は、これらのイベントを再度有効にする必要があります。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

