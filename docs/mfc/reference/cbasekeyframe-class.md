---
title: "CBaseKeyFrame クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CBaseKeyFrame
- AFXANIMATIONCONTROLLER/CBaseKeyFrame
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::CBaseKeyFrame
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::AddToStoryboard
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::GetAnimationKeyframe
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::IsAdded
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::IsKeyframeAtOffset
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::m_bAdded
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::m_bIsKeyframeAtOffset
- AFXANIMATIONCONTROLLER/CBaseKeyFrame::m_keyframe
dev_langs:
- C++
helpviewer_keywords:
- CBaseKeyFrame class
ms.assetid: 285a2eff-e7c4-43be-b5aa-737727e6866d
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: cfbaac379097c89b5dcb52fa36c0cd1f6e3d2c7f
ms.lasthandoff: 02/24/2017

---
# <a name="cbasekeyframe-class"></a>CBaseKeyFrame クラス
キーフレームの基本機能を実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CBaseKeyFrame : public CObject;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CBaseKeyFrame::CBaseKeyFrame](#cbasekeyframe)|キーフレームのオブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CBaseKeyFrame::AddToStoryboard](#addtostoryboard)|ストーリー ボードにキーフレームを追加します。|  
|[CBaseKeyFrame::GetAnimationKeyframe](#getanimationkeyframe)|基になるキーフレーム値を返します。|  
|[CBaseKeyFrame::IsAdded](#isadded)|キーフレームをストーリー ボードに追加されているかどうかを指示します。|  
|[CBaseKeyFrame::IsKeyframeAtOffset](#iskeyframeatoffset)|ストーリー ボードのオフセット、または移行後に、キーフレームを追加するかどうかを指定します。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CBaseKeyFrame::m_bAdded](#m_badded)|このキーフレームをストーリー ボードに追加されているかどうかを指定します。|  
|[CBaseKeyFrame::m_bIsKeyframeAtOffset](#m_biskeyframeatoffset)|ストーリー ボードの別の既存のキーフレームからのオフセットまたはいくつかの遷移の終了時にこのキーフレームを追加するかどうかを指定します。|  
|[CBaseKeyFrame::m_keyframe](#m_keyframe)|Windows Animation API キーフレームを表します。 キーフレームが初期化されていない場合は、UI_ANIMATION_KEYFRAME_STORYBOARD_START の定義済みの値に設定されます。|  
  
## <a name="remarks"></a>コメント  
 UI_ANIMATION_KEYFRAME 変数をカプセル化します。 すべてのキーフレームの実装の基本クラスとして機能します。 キーフレームは、ストーリー ボード内の特定の時点を表し、遷移の開始と終了時刻を指定するために使用できます。 キーフレームのキーフレーム (時間) 単位で指定したオフセットでストーリー ボードに追加または指定された移行後に追加のキーフレームの&2; 種類があります。 アニメーションが開始する前に一部の切り替え効果の期間を特定できないために、いくつかのキーフレームの実際の値は、実行時のみに決定されます。 キーフレームは、キーフレームに依存している順番である遷移に依存している可能性があります、キーフレームのチェーンを構築する際に、無限再帰を防ぐ必要があります。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CBaseKeyFrame`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxanimationcontroller.h  
  
##  <a name="addtostoryboard"></a>CBaseKeyFrame::AddToStoryboard  
 ストーリー ボードにキーフレームを追加します。  
  
```  
virtual BOOL AddToStoryboard(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDeepAdd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pStoryboard`  
 ストーリー ボードへのポインター。  
  
 `bDeepAdd`  
 このパラメーターが TRUE であり、追加されるキーフレームは、他のキーフレームまたは遷移によって異なります。 場合、このメソッドはこのキーフレームまたは最初にストーリー ボードへの移行を追加しようとします。  
  
### <a name="return-value"></a>戻り値  
 キーフレームが正常にストーリー ボードに追加された場合は TRUE。それ以外の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
 このメソッドはストーリー ボードにキーフレームを追加します。  
  
##  <a name="cbasekeyframe"></a>CBaseKeyFrame::CBaseKeyFrame  
 キーフレームのオブジェクトを構築します。  
  
```  
CBaseKeyFrame();
```  
  
##  <a name="getanimationkeyframe"></a>CBaseKeyFrame::GetAnimationKeyframe  
 基になるキーフレーム値を返します。  
  
```  
UI_ANIMATION_KEYFRAME GetAnimationKeyframe() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在のキーフレームです。 既定値は、UI_ANIMATION_KEYFRAME_STORYBOARD_START です。  
  
### <a name="remarks"></a>コメント  
 これは、基になるキーフレーム値のアクセサーです。  
  
##  <a name="isadded"></a>CBaseKeyFrame::IsAdded  
 キーフレームをストーリー ボードに追加されているかどうかを指示します。  
  
```  
BOOL IsAdded() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ストーリー ボード; にキーフレームを追加する場合は TRUE。そう FALSE。  
  
### <a name="remarks"></a>コメント  
 基本クラスでも常に TRUE を返しますが、派生クラスでオーバーライドされます。  
  
##  <a name="iskeyframeatoffset"></a>CBaseKeyFrame::IsKeyframeAtOffset  
 ストーリー ボードのオフセット、または移行後に、キーフレームを追加するかどうかを指定します。  
  
```  
BOOL IsKeyframeAtOffset() const;  
```  
  
### <a name="return-value"></a>戻り値  
 TRUE の場合、キーフレームは、いくつかの指定したオフセットでストーリー ボードに追加する必要があります。 FALSE の場合、ストーリー ボードの一部の切り替え後に、キーフレームを追加する必要があります。  
  
### <a name="remarks"></a>コメント  
 オフセットでストーリー ボードに、キーフレームを追加するかどうかを指定します。 派生クラスでは、オフセットまたは遷移を指定してください。  
  
##  <a name="m_badded"></a>CBaseKeyFrame::m_bAdded  
 このキーフレームをストーリー ボードに追加されているかどうかを指定します。  
  
```  
BOOL m_bAdded;  
```  
  
##  <a name="m_biskeyframeatoffset"></a>CBaseKeyFrame::m_bIsKeyframeAtOffset  
 ストーリー ボードの別の既存のキーフレームからのオフセットまたはいくつかの遷移の終了時にこのキーフレームを追加するかどうかを指定します。  
  
```  
BOOL m_bIsKeyframeAtOffset;  
```  
  
##  <a name="m_keyframe"></a>CBaseKeyFrame::m_keyframe  
 Windows Animation API キーフレームを表します。 キーフレームが初期化されていない場合は、UI_ANIMATION_KEYFRAME_STORYBOARD_START の定義済みの値に設定されます。  
  
```  
UI_ANIMATION_KEYFRAME m_keyframe;  
```  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

