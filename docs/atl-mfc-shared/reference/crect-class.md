---
title: "CRect クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CRect"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LPCRECT データ型"
  - "CRect クラス"
  - "LPRECT 演算子"
  - "RECT 構造体"
ms.assetid: dee4e752-15d6-4db4-b68f-1ad65b2ed6ca
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CRect クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows のような [RECT](RECT%20Structure1.md) 構造体。  
  
## <a name="syntax"></a>構文  
  
```  
class CRect : public tagRECT  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CRect::CRect](#crect__crect)|`CRect` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CRect::BottomRight](#crect__bottomright)|右下隅の点を返す `CRect`します。|  
|[CRect::CenterPoint](#crect__centerpoint)|中心点を返す `CRect`します。|  
|[CRect::CopyRect](#crect__copyrect)|コピーを元の四角形の寸法 `CRect`します。|  
|[CRect::DeflateRect](#crect__deflaterect)|幅と高さの減少 `CRect`します。|  
|[CRect::EqualRect](#crect__equalrect)|指定するかどうか `CRect` が指定された四角形と等しい。|  
|[CRect::Height](#crect__height)|高さを計算 `CRect`します。|  
|[CRect::InflateRect](#crect__inflaterect)|幅と高さの増加 `CRect`します。|  
|[CRect::IntersectRect](#crect__intersectrect)|セット `CRect` の 2 つの四角形の交差部分に等しい。|  
|[CRect::IsRectEmpty](#crect__isrectempty)|指定するかどうか `CRect` が空です。 `CRect` 空の場合、幅や高さは 0 です。|  
|[CRect::IsRectNull](#crect__isrectnull)|決定するかどうか、 **上部**, 、**下部にある**, 、**左**, 、および **右** メンバー変数が 0 に等しいすべてです。|  
|[CRect::MoveToX](#crect__movetox)|移動 `CRect` 指定した x 座標。|  
|[CRect::MoveToXY](#crect__movetoxy)|移動 `CRect` を指定した x 座標と y 座標。|  
|[CRect::MoveToY](#crect__movetoy)|移動 `CRect` に指定された座標の y 座標。|  
|[CRect::NormalizeRect](#crect__normalizerect)|幅と高さを標準化 `CRect`します。|  
|[CRect::OffsetRect](#crect__offsetrect)|移動 `CRect` 指定されたオフセットします。|  
|[CRect::PtInRect](#crect__ptinrect)|内で指定したポイントにあるかどうかを調べます `CRect`します。|  
|[CRect::SetRect](#crect__setrect)|寸法を設定 `CRect`します。|  
|[CRect::SetRectEmpty](#crect__setrectempty)|セット `CRect` (すべての座標は 0 に等しい) 空の四角形にします。|  
|[CRect::Size](#crect__size)|サイズを計算 `CRect`します。|  
|[CRect::SubtractRect](#crect__subtractrect)|別の 1 つの四角形を減算します。|  
|[CRect::TopLeft](#crect__topleft)|左上の点を返す `CRect`します。|  
|[CRect::UnionRect](#crect__unionrect)|セット `CRect` の 2 つの四角形の部分に相当します。|  
|[CRect::Width](#crect__width)|幅を計算 `CRect`します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CRect::operator-](#crect__operator_-)|指定したオフセットを減算 `CRect` を縮小または `CRect` し、その結果を返します `CRect`します。|  
|[CRect::operator LPCRECT](#crect__operator_lpcrect)|変換、 `CRect` に、 **LPCRECT**します。|  
|[CRect::operator LPRECT](#crect__operator_lprect)|変換、 `CRect` に、 `LPRECT`です。|  
|[CRect::operator! =](#crect__operator__neq)|指定するかどうか `CRect` が四角形と等しくないです。|  
|[CRect::operator &amp;](#crect__operator__amp_)|積集合を作成 `CRect` と四角形をその結果を返します `CRect`します。|  
|[CRect::operator &amp;=](#crect__operator__amp__eq)|セット `CRect` の交差部分に等しい `CRect` と四角形。|  
|[CRect::operator |](#crect__operator__or)|和集合を作成 `CRect` と四角形、その結果を返すと `CRect`です。|  
|[CRect::operator |=](#crect__operator__or_eq)|セット `CRect` の共用体に等しい `CRect` と四角形。|  
|[CRect::operator +](#crect__operator__add)|指定したオフセットへの追加 `CRect` 拡張または `CRect` し、その結果を返します `CRect`します。|  
|[CRect::operator + = 演算子](#crect__operator__add_eq)|指定したオフセット位置に追加 `CRect` 拡張または `CRect`です。|  
|[CRect::operator =](#crect__operator__eq)|コピーする四角形の寸法 `CRect`します。|  
|[CRect::operator =](#crect__operator_-_eq)|指定されたオフセットを減算 `CRect` を縮小または `CRect`です。|  
|[CRect::operator = =](#crect__operator__eq_eq)|決定するかどうか `CRect` は四角形にします。|  
  
## <a name="remarks"></a>コメント  
 `CRect` 操作するためのメンバー関数を含む `CRect` オブジェクトと Windows `RECT` 構造体。  
  
 A `CRect` オブジェクトは、関数のパラメーターとして渡すことがであれば常に、 `RECT` 構造体、 **LPCRECT**, 、または `LPRECT` 渡すことができます。  
  
> [!NOTE]
>  このクラスから派生、 **tagRECT** 構造体。 (名前 **tagRECT** なしに一般的に使用される名前で、 `RECT` 構造です)。つまり、このデータ メンバー ( **左**, 、**上部**, 、**右**, 、および **下部**) の `RECT` 構造のアクセス可能なデータ メンバーである `CRect`です。  
  
 A `CRect` 四角形の左と右下隅の点を定義するメンバー変数が含まれています。  
  
 指定する場合、 `CRect`, は、正規化になるように構築する必要があります: つまり、左座標の値が右最上部より小さい結果が下より小さくします。 などの (10, 10) の左、上と (20, 20) の右下定義正規化された四角形が (20, 20) の左し、(10, 10) の右下が正規化されていない四角形を定義します。 多く、四角形が正規化されていない場合 `CRect` メンバー関数が正しくない結果を返す可能性があります。 (参照 [CRect::NormalizeRect](#crect__normalizerect) これらの関数の一覧についてです)。正規化された四角形を必要とする関数を呼び出す前に呼び出すことによって正規化されていない四角形を正規化して、 `NormalizeRect` 関数です。  
  
 操作するときに警告を使用して、 `CRect` [CDC::DPtoLP] と (../Topic/CDC%20Class.md#cdc__dptolp と [CDC::LPtoDP] (../Topic/CDC%20Class.md#cdc__lptodp メンバー関数。 ディスプレイ コンテキストのマッピング モードでが y 範囲が負の場合と同様になるよう `MM_LOENGLISH`, 、し、 `CDC::DPtoLP` を変換する、 `CRect` の最上位は、下部にあるより大きいようにします。 などの関数 **高さ** と **サイズ** 、変換後の高さに負の値が返される `CRect`, 、正規化されていない、四角形になります。  
  
 オーバー ロードを使用するときに `CRect` 演算子、1 番目のオペランドである必要があります、 `CRect`; 2 つ目には、いずれかを指定できます、 [RECT](RECT%20Structure1.md) 構造体、または `CRect` オブジェクトです。  
  
> [!NOTE]
>  詳細については、ユーティリティ クラスを共有 (のように `CRect`) を参照してください [共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `tagRECT`  
  
 `CRect`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atltypes.h  
  
##  <a name="a-namecrectbottomrighta-crectbottomright"></a><a name="crect__bottomright"></a>  CRect::BottomRight  
 座標がへの参照として返される、 [CPoint](../Topic/CPoint%20Class.md) オブジェクトに含まれている `CRect`します。  
  
```  
 
CPoint& BottomRight() throw();

const CPoint& BottomRight() const throw();

 
```  
  
### <a name="return-value"></a>戻り値  
 四角形の右下隅の座標。  
  
### <a name="remarks"></a>コメント  
 この関数は、取得、または四角形の右下隅の設定を使用することができます。 代入演算子の左側にあるこの関数を使用して、角を設定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#35](../../atl-mfc-shared/codesnippet/CPP/crect-class_1.cpp)]  
  
##  <a name="a-namecrectcenterpointa-crectcenterpoint"></a><a name="crect__centerpoint"></a>  CRect::CenterPoint  
 中心点を計算 `CRect` 左と右の値を追加して、2 つで除算し、上端と下端の値を追加する 2 で除算しています。  
  
```  
CPoint CenterPoint() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 A `CPoint` の中心点であるオブジェクトを `CRect`します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#36](../../atl-mfc-shared/codesnippet/CPP/crect-class_2.cpp)]  
  
##  <a name="a-namecrectcopyrecta-crectcopyrect"></a><a name="crect__copyrect"></a>  CRect::CopyRect  
 コピー、 `lpSrcRect` に四角形 `CRect`します。  
  
```  
 
void CopyRect(
LPCRECT   
lpSrcRect) throw();

 
```  
  
### <a name="parameters"></a>パラメーター  
 `lpSrcRect`  
 指す、 [RECT](RECT%20Structure1.md) 構造または `CRect` オブジェクトのコピーです。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#37](../../atl-mfc-shared/codesnippet/CPP/crect-class_3.cpp)]  
  
##  <a name="a-namecrectcrecta-crectcrect"></a><a name="crect__crect"></a>  CRect::CRect  
 `CRect` オブジェクトを構築します。  
  
```  
 
    CRect() throw();
CRect(
 int    
    l ,  
    int 
    t ,  
    int 
    r ,  
    int 
    b) throw();
CRect(
 const RECT& 
    srcRect) throw();
CRect(
 LPCRECT    
    lpSrcRect) throw();
CRect(
 POINT    
    point ,  
    SIZE 
    size) throw();
CRect(
 POINT    
    topLeft ,  
    POINT 
    bottomRight) throw();

 
```  
  
### <a name="parameters"></a>パラメーター  
 *l*  
 左の位置を示す `CRect`します。  
  
 *t*  
 先頭を示す `CRect`します。  
  
 *r*  
 右の位置を示す `CRect`します。  
  
 *b*  
 指定の下部にある `CRect`です。  
  
 *srcRect*  
 指す、 [RECT](RECT%20Structure1.md) の座標を含む構造体 `CRect`します。  
  
 `lpSrcRect`  
 指す、 `RECT` の座標を含む構造体 `CRect`します。  
  
 `point`  
 構築される四角形の最初の場所を指定します。 左上隅に対応します。  
  
 `size`  
 左上隅から構築される四角形の右下隅までの距離を指定します。  
  
 *左上端*  
 左上の位置を示す `CRect`します。  
  
 *bottomRight*  
 右下の位置を示す `CRect`します。  
  
### <a name="remarks"></a>コメント  
 引数を指定しない場合 **左**, 、**上部**, 、**右**, 、および **下部** メンバーは初期化されません。  
  
  `CRect`( **Const RECT &**) と `CRect`( **LPCRECT**) コンス トラクターで実行、 [CopyRect](#crect__copyrect)します。 他のコンス トラクターでは、直接オブジェクトのメンバー変数を初期化します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#38](../../atl-mfc-shared/codesnippet/CPP/crect-class_4.cpp)]  
  
##  <a name="a-namecrectdeflaterecta-crectdeflaterect"></a><a name="crect__deflaterect"></a>  CRect::DeflateRect  
 `DeflateRect` 縮小 `CRect` 、両側の中心に移行することができます。  
  
```  
 
    void DeflateRect(
    int 
    x ,  
    int 
    y) throw();
void DeflateRect(
    SIZE 
    size) throw();
void DeflateRect(
    LPCRECT 
    lpRect) throw();
void DeflateRect(
    int 
    l ,  
    int 
    t ,  
    int 
    r ,  
    int 
    b) throw();

 
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 指定の左側を圧縮する単位の数および右側 `CRect`します。  
  
 *y*  
 上下を圧縮する単位の数を指定 `CRect`します。  
  
 `size`  
 A [サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106) または [CSize](../../atl-mfc-shared/reference/csize-class.md) deflate する単位の数を指定する `CRect`です。  `cx` 値左辺と右辺を圧縮する単位の数を指定し、 `cy` 値上部と下部を圧縮する単位の数を指定します。  
  
 `lpRect`  
 指す、 [RECT](RECT%20Structure1.md) 構造または `CRect` 各辺を縮小する単位の数を指定します。  
  
 *l*  
 左側にあるを圧縮する単位の数を指定 `CRect`します。  
  
 *t*  
 先頭を圧縮する単位の数を指定 `CRect`します。  
  
 *r*  
 右側にあるを圧縮する単位の数を指定 `CRect`します。  
  
 *b*  
 下部にあるを圧縮する単位の数を指定 `CRect`します。  
  
### <a name="remarks"></a>コメント  
 これを行う `DeflateRect` left および top にユニットを追加し、右や下から単位を減算します。 パラメーター `DeflateRect` は署名値は正の値が deflate `CRect` 負の値は拡大とします。  
  
 最初の 2 つのオーバー ロードは、両方の反対側の組み合わせを縮小 `CRect` 2 倍、全体の幅が減少するよう *x* (または `cx`) し、2 回、全体の高さが減らさ *y* (または `cy`)。 その他の 2 つのオーバー ロードの各辺を縮小する `CRect` 、他のユーザーとは無関係にします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#39](../../atl-mfc-shared/codesnippet/CPP/crect-class_5.cpp)]  
  
##  <a name="a-namecrectequalrecta-crectequalrect"></a><a name="crect__equalrect"></a>  CRect::EqualRect  
 指定するかどうか `CRect` が指定された四角形と等しい。  
  
```  
 
BOOL EqualRect(
LPCRECT   
lpRect) const throw();

 
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect`  
 指す、 [RECT](RECT%20Structure1.md) 構造または `CRect` 四角形の左上隅および右下隅の座標を格納しているオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 2 つの四角形は、同じ上、左、下、および右の値がある場合は 0 以外それ以外の場合 0 を返します。  
  
> [!NOTE]
>  四角形の両方を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます [NormalizeRect](#crect__normalizerect) をこの関数を呼び出す前に、四角形を正規化します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#40](../../atl-mfc-shared/codesnippet/CPP/crect-class_6.cpp)]  
  
##  <a name="a-namecrectheighta-crectheight"></a><a name="crect__height"></a>  CRect::Height  
 高さを計算 `CRect` 下部にある値から最上位の値を減算します。  
  
```  
int Height() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 高さ `CRect`します。  
  
### <a name="remarks"></a>コメント  
 結果として得られる値は、負の値で指定できます。  
  
> [!NOTE]
>  四角形を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます [NormalizeRect](#crect__normalizerect) をこの関数を呼び出す前に、四角形を正規化します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#41](../../atl-mfc-shared/codesnippet/CPP/crect-class_7.cpp)]  
  
##  <a name="a-namecrectinflaterecta-crectinflaterect"></a><a name="crect__inflaterect"></a>  CRect::InflateRect  
 `InflateRect` 拡張 `CRect` 中心から離れて、両側を移動しています。  
  
```  
 
    void InflateRect(
    int 
    x ,  
    int 
    y) throw();
void InflateRect(
    SIZE 
    size) throw();
void InflateRect(
    LPCRECT 
    lpRect) throw();
void InflateRect(
    int 
    l ,  
    int 
    t ,  
    int 
    r ,  
    int 
    b) throw();

 
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 左右を左に拡大するためのユニットの数を指定 `CRect`します。  
  
 *y*  
 上下に拡大するためのユニットの数を指定 `CRect`します。  
  
 `size`  
 A [サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106) または [CSize](../../atl-mfc-shared/reference/csize-class.md) を拡大するためのユニットの数を指定する `CRect`です。  `cx` 値を左辺と右辺を拡大するためのユニットの数を指定し、 `cy` 値を上下に拡大するためのユニットの数を指定します。  
  
 `lpRect`  
 指す、 [RECT](RECT%20Structure1.md) 構造または `CRect` 各辺を拡大する単位の数を指定します。  
  
 *l*  
 左側にあるを拡大するためのユニットの数を指定 `CRect`します。  
  
 *t*  
 先頭を拡大するためのユニットの数を指定 `CRect`します。  
  
 *r*  
 右側にあるを拡大するためのユニットの数を指定 `CRect`します。  
  
 *b*  
 下部にあるを拡大するためのユニットの数を指定 `CRect`します。  
  
### <a name="remarks"></a>コメント  
 これを行う `InflateRect` left および top から単位を減算し、その単位を右や下に追加します。 パラメーター `InflateRect` は署名値は正の値は拡大 `CRect` し、負の値は縮小します。  
  
 最初の 2 つのオーバー ロードは、両方の反対側の組み合わせを拡大 `CRect` 、全体の幅が 2 倍に増加できるように *x* (または `cx`)、全体の高さを 2 倍に増やす *y* (または `cy`)。 その他の 2 つのオーバー ロードの各辺を拡大する `CRect` 、他のユーザーとは無関係にします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#42](../../atl-mfc-shared/codesnippet/CPP/crect-class_8.cpp)]  
  
##  <a name="a-namecrectintersectrecta-crectintersectrect"></a><a name="crect__intersectrect"></a>  CRect::IntersectRect  
 により、 `CRect` 既存の 2 つの四角形の交差部分に等しい。  
  
```  
 
    BOOL IntersectRect(
    LPCRECT 
    lpRect1 ,  
    LPCRECT 
    lpRect2) throw();

 
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect1`  
 指す、 [RECT](RECT%20Structure1.md) 構造または `CRect` を元の四角形を含むオブジェクト。  
  
 `lpRect2`  
 指す、 `RECT` 構造または `CRect` を元の四角形を含むオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 積集合が空でない場合は 0 以外。積集合が空の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 積集合は、両方の既存の四角形に含まれる最大の四角形です。  
  
> [!NOTE]
>  四角形の両方を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます [NormalizeRect](#crect__normalizerect) をこの関数を呼び出す前に、四角形を正規化します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#43](../../atl-mfc-shared/codesnippet/CPP/crect-class_9.cpp)]  
  
##  <a name="a-namecrectisrectemptya-crectisrectempty"></a><a name="crect__isrectempty"></a>  CRect::IsRectEmpty  
 指定するかどうか `CRect` が空です。  
  
```  
BOOL IsRectEmpty() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の値 `CRect` が空の場合 0 場合 `CRect` 空ではありません。  
  
### <a name="remarks"></a>コメント  
 四角形は、空の場合、幅や高さは 0 または負の値です。 異なる `IsRectNull`, 、四角形のすべての座標は、0 であるかどうかを決定します。  
  
> [!NOTE]
>  四角形を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます [NormalizeRect](#crect__normalizerect) をこの関数を呼び出す前に、四角形を正規化します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#44](../../atl-mfc-shared/codesnippet/CPP/crect-class_10.cpp)]  
  
##  <a name="a-namecrectisrectnulla-crectisrectnull"></a><a name="crect__isrectnull"></a>  CRect::IsRectNull  
 左上が下かどうかを決定し、右の値 `CRect` が 0 に等しいすべてです。  
  
```  
BOOL IsRectNull() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の値 `CRect`左、上の下し、右の値は 0。 それ以外の場合 0 です。  
  
### <a name="remarks"></a>コメント  
 異なる `IsRectEmpty`, 、四角形が空かどうかを決定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#45](../../atl-mfc-shared/codesnippet/CPP/crect-class_11.cpp)]  
  
##  <a name="a-namecrectmovetoxa-crectmovetox"></a><a name="crect__movetox"></a>  CRect::MoveToX  
 指定された絶対 x 座標に四角形を移動するには、この関数を呼び出す *x*です。  
  
```  
 
void MoveToX(
int   
x) throw();

 
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 四角形の左上隅の絶対 x 座標。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#46](../../atl-mfc-shared/codesnippet/CPP/crect-class_12.cpp)]  
  
##  <a name="a-namecrectmovetoxya-crectmovetoxy"></a><a name="crect__movetoxy"></a>  CRect::MoveToXY  
 絶対 x 座標と y 座標を指定の四角形を移動するには、この関数を呼び出します。  
  
```  
 
    void MoveToXY(
    int 
    x ,  
    int 
    y) throw();
void MoveToXY(
    POINT 
    point) throw();

 
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 四角形の左上隅の絶対 x 座標。  
  
 *y*  
 四角形の左上隅の絶対 y 座標。  
  
 `point`  
 A **ポイント** 四角形の絶対の左上隅を指定する構造体。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#47](../../atl-mfc-shared/codesnippet/CPP/crect-class_13.cpp)]  
  
##  <a name="a-namecrectmovetoya-crectmovetoy"></a><a name="crect__movetoy"></a>  CRect::MoveToY  
 絶対座標の y 座標で指定された四角形を移動するには、この関数を呼び出す *y*します。  
  
```  
 
void MoveToY(
int   
y) throw();

 
```  
  
### <a name="parameters"></a>パラメーター  
 *y*  
 四角形の左上隅の絶対 y 座標。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#48](../../atl-mfc-shared/codesnippet/CPP/crect-class_14.cpp)]  
  
##  <a name="a-namecrectnormalizerecta-crectnormalizerect"></a><a name="crect__normalizerect"></a>  CRect::NormalizeRect  
 正規化 `CRect` 幅と高さが正の値になるようです。  
  
```  
void NormalizeRect() throw();
```  
  
### <a name="remarks"></a>コメント  
 四角形を正規化 4 分の作業領域を配置するため Windows が通常の座標を使用します。 `NormalizeRect` 上端と下端の値を比較し、最上位は、下部にあるより大きい場合は、それらをスワップします。 同様に、左が右より大きい場合、左と右の値を交換します。 この関数は、別のマッピング モードを処理する場合に便利ですが、反転された四角形。  
  
> [!NOTE]
>  次 `CRect` メンバー関数が正常に動作するために正規化された四角形を必要と: [高さ](#crect__height), 、[幅](#crect__width), 、[サイズ](#crect__size), 、[IsRectEmpty](#crect__isrectempty), 、[PtInRect](#crect__ptinrect), 、[EqualRect](#crect__equalrect), 、[UnionRect](#crect__unionrect), 、[示します](#crect__intersectrect), 、[SubtractRect](#crect__subtractrect), 、[演算子 = =](#crect__operator__eq_eq), 、[演算子! =](#crect__operator__neq), 、[演算子 &#124;](#crect__operator__or), 、[演算子 & #124 文字です。 =](#crect__operator__or_eq), 、[演算子 &](#crect__operator__amp_), 、と [演算子 (& a) =](#crect__operator__amp__eq)です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#49](../../atl-mfc-shared/codesnippet/CPP/crect-class_15.cpp)]  
  
##  <a name="a-namecrectoffsetrecta-crectoffsetrect"></a><a name="crect__offsetrect"></a>  CRect::OffsetRect  
 移動 `CRect` 指定されたオフセットします。  
  
```  
 
    void OffsetRect(
    int 
    x ,  
    int 
    y) throw();
void OffsetRect(
    POINT 
    point) throw();
void OffsetRect(
    SIZE 
    size) throw();

 
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 左に移動する量を指定します。 負の値を左に移動する場合があります。  
  
 *y*  
 上下に移動する量を指定します。 上に移動する負の値がある場合があります。  
  
 `point`  
 含む、 [ポイント](../../mfc/reference/point-structure1.md) 構造または [CPoint](../Topic/CPoint%20Class.md) 移動に使用する寸法の両方を指定するオブジェクト。  
  
 `size`  
 含む、 [サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106) 構造または [CSize](../../atl-mfc-shared/reference/csize-class.md) 移動に使用する寸法の両方を指定するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 移動 `CRect`*x* 、x 軸に沿った単位と *y* y 軸に沿った単位です。  *X* と *y* パラメーターは、符号付きの値をそのため、 `CRect` をし、左に移動できるまたは右上または下です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#50](../../atl-mfc-shared/codesnippet/CPP/crect-class_16.cpp)]  
  
##  <a name="a-namecrectoperatorlpcrecta-crectoperator-lpcrect"></a><a name="crect__operator_lpcrect"></a>  CRect::operator LPCRECT  
 変換、 `CRect` に、 [LPCRECT](../Topic/Data%20Types%20\(MFC\).md)します。  
  
'' 演算子 LPCRECT() const throw() です。
```  
  
### Remarks  
 When you use this function, you don't need the address-of ( **&**) operator. This operator will be automatically used when you pass a `CRect` object to a function that expects an **LPCRECT**.  
  
### Example  
 [!code-cpp[NVC_ATLMFC_Utilities#58](../../atl-mfc-shared/codesnippet/CPP/crect-class_17.cpp)]  
  
##  <a name="crect__operator_lprect"></a>  CRect::operator LPRECT  
 Converts a `CRect` to an [LPRECT](../Topic/Data%20Types%20\(MFC\).md).  
  
```  operator LPRECT() throw();
```  
  
### <a name="remarks"></a>コメント  
 この関数を使用するときのアドレスがなくても ( **&**) 演算子。 この演算子は渡すときに自動的に使用、 `CRect` オブジェクトを受け取る関数を `LPRECT`です。  
  
### <a name="example"></a>例  
 例を参照してください [CRect::operator LPCRECT](#crect__operator_lpcrect)します。  
  
##  <a name="a-namecrectoperatoreqa-crectoperator-"></a><a name="crect__operator__eq"></a>  CRect::operator =  
 割り当てる *srcRect* に `CRect`します。  
  
```  
 
void operator=(
const RECT& 
srcRect) throw();

 
```  
  
### <a name="parameters"></a>パラメーター  
 *srcRect*  
 元の四角形を指します。  [RECT](RECT%20Structure1.md) または `CRect`です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#59](../../atl-mfc-shared/codesnippet/CPP/crect-class_18.cpp)]  
  
##  <a name="a-namecrectoperatoreqeqa-crectoperator-"></a><a name="crect__operator__eq_eq"></a>  CRect::operator = =  
 決定するかどうか `rect` に等しい `CRect` 左上隅および右下隅の座標を比較することによってです。  
  
```  
 
BOOL operator==(
const RECT& 
rect) const throw();

 
```  
  
### <a name="parameters"></a>パラメーター  
 `rect`  
 元の四角形を指します。  [RECT](RECT%20Structure1.md) または `CRect`です。  
  
### <a name="return-value"></a>戻り値  
 等しい場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  四角形の両方を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます [NormalizeRect](#crect__normalizerect) をこの関数を呼び出す前に、四角形を正規化します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#60](../../atl-mfc-shared/codesnippet/CPP/crect-class_19.cpp)]  
  
##  <a name="a-namecrectoperatorneqa-crectoperator-"></a><a name="crect__operator__neq"></a>  CRect::operator! =  
 決定するかどうか `rect` と等しくない `CRect` 左上隅および右下隅の座標を比較することによってです。  
  
```  
 
BOOL operator!=(
const RECT& 
rect) const throw();

 
```  
  
### <a name="parameters"></a>パラメーター  
 `rect`  
 元の四角形を指します。  [RECT](RECT%20Structure1.md) または `CRect`です。  
  
### <a name="return-value"></a>戻り値  
 等しくない場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  四角形の両方を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます [NormalizeRect](#crect__normalizerect) をこの関数を呼び出す前に、四角形を正規化します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#61](../../atl-mfc-shared/codesnippet/CPP/crect-class_20.cpp)]  
  
##  <a name="a-namecrectoperatoraddeqa-crectoperator-"></a><a name="crect__operator__add_eq"></a>  CRect::operator + = 演算子  
 最初の 2 つのオーバー ロードは、移動 `CRect` 指定されたオフセットします。  
  
```  
 
void operator+=(
POINT   
point) throw();

void operator+=(
SIZE   
size) throw();

void operator+=(
LPCRECT   
lpRect) throw();

 
```  
  
### <a name="parameters"></a>パラメーター  
 `point`  
 A [ポイント](../../mfc/reference/point-structure1.md) 構造または [CPoint](../Topic/CPoint%20Class.md) 四角形を移動する単位の数を指定するオブジェクト。  
  
 `size`  
 A [サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106) 構造または [CSize](../../atl-mfc-shared/reference/csize-class.md) 四角形を移動する単位の数を指定するオブジェクト。  
  
 `lpRect`  
 指す、 [RECT](RECT%20Structure1.md) 構造または `CRect` の各辺拡大する単位の数を格納しているオブジェクト `CRect`します。  
  
### <a name="remarks"></a>コメント  
 パラメーターの *x* と *y* (または `cx` と `cy`) 値に追加する `CRect`です。  
  
 3 番目のオーバー ロードだけ `CRect` 、パラメーターの各メンバーで指定された単位の数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#62](../../atl-mfc-shared/codesnippet/CPP/crect-class_21.cpp)]  
  
##  <a name="a-namecrectoperator-eqa-crectoperator--"></a><a name="crect__operator_-_eq"></a>  CRect::operator =  
 最初の 2 つのオーバー ロードは、移動 `CRect` 指定されたオフセットします。  
  
```  
 
void operator-=(
POINT   
point) throw();

void operator-=(
SIZE   
size) throw();

void operator-=(
LPCRECT   
lpRect) throw();

 
```  
  
### <a name="parameters"></a>パラメーター  
 `point`  
 A [ポイント](../../mfc/reference/point-structure1.md) 構造または [CPoint](../Topic/CPoint%20Class.md) 四角形を移動する単位の数を指定するオブジェクト。  
  
 `size`  
 A [サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106) 構造または [CSize](../../atl-mfc-shared/reference/csize-class.md) 四角形を移動する単位の数を指定するオブジェクト。  
  
 `lpRect`  
 指す、 [RECT](RECT%20Structure1.md) 構造または `CRect` の各辺を圧縮する単位の数を格納しているオブジェクト `CRect`します。  
  
### <a name="remarks"></a>コメント  
 パラメーターの *x* と *y* (または `cx` と `cy`) から値を減算する `CRect`です。  
  
 3 番目のオーバー ロードを縮小 `CRect` 、パラメーターの各メンバーで指定された単位の数。 このオーバー ロードの機能を [DeflateRect](#crect__deflaterect)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#63](../../atl-mfc-shared/codesnippet/CPP/crect-class_22.cpp)]  
  
##  <a name="a-namecrectoperatorampeqa-crectoperator-amp"></a><a name="crect__operator__amp__eq"></a>  CRect::operator &amp;=  
 セット `CRect` の交差部分に等しい `CRect` と `rect`です。  
  
```  
 
void operator&=(
const RECT& 
rect) throw();

 
```  
  
### <a name="parameters"></a>パラメーター  
 `rect`  
 含む、 [RECT](RECT%20Structure1.md) または `CRect`です。  
  
### <a name="remarks"></a>コメント  
 積集合は、両方の四角形に含まれる最大の四角形です。  
  
> [!NOTE]
>  四角形の両方を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます [NormalizeRect](#crect__normalizerect) をこの関数を呼び出す前に、四角形を正規化します。  
  
### <a name="example"></a>例  
 例を参照してください [CRect::IntersectRect](#crect__intersectrect)します。  
  
##  <a name="a-namecrectoperatororeqa-crectoperator-124"></a><a name="crect__operator__or_eq"></a>  CRect::operator &#124; =  
 セット `CRect` の共用体に等しい `CRect` と `rect`です。  
  
```  
 
void operator|=(
const RECT& 
rect) throw();

 
```  
  
### <a name="parameters"></a>パラメーター  
 `rect`  
 含む、 `CRect` または [RECT](RECT%20Structure1.md)します。  
  
### <a name="remarks"></a>コメント  
 共用体は、両方の四角形を含む最小の四角形です。  
  
> [!NOTE]
>  四角形の両方を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます [NormalizeRect](#crect__normalizerect) をこの関数を呼び出す前に、四角形を正規化します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#64](../../atl-mfc-shared/codesnippet/CPP/crect-class_23.cpp)]  
  
##  <a name="a-namecrectoperatoradda-crectoperator-"></a><a name="crect__operator__add"></a>  CRect::operator +  
 最初の 2 つのオーバー ロードが返す、 `CRect` オブジェクトと等しい `CRect` 指定したオフセット位置がずれている場合します。  
  
```  
 
CRect operator+(
POINT   
point) const throw();

CRect operator+(
LPCRECT   
lpRect) const throw();

CRect operator+(
SIZE   
size) const throw();

 
```  
  
### <a name="parameters"></a>パラメーター  
 `point`  
 A [ポイント](../../mfc/reference/point-structure1.md) 構造または [CPoint](../Topic/CPoint%20Class.md) 戻り値を移動する単位の数を指定するオブジェクト。  
  
 `size`  
 A [サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106) 構造または [CSize](../../atl-mfc-shared/reference/csize-class.md) 戻り値を移動する単位の数を指定するオブジェクト。  
  
 `lpRect`  
 指す、 [RECT](RECT%20Structure1.md) 構造または `CRect` 戻り値の各辺を拡大する単位の数を格納しているオブジェクト。  
  
### <a name="return-value"></a>戻り値  
  `CRect` 移動または増やして `CRect` パラメーターで指定されたユニットの数でします。  
  
### <a name="remarks"></a>コメント  
 パラメーターの *x* と *y* (または `cx` と `cy`) にパラメーターが追加される `CRect`の位置します。  
  
 3 番目のメソッドの戻り値の新しい `CRect` の値が `CRect` 膨らませると各メンバーのパラメーターで指定された単位の数。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#65](../../atl-mfc-shared/codesnippet/CPP/crect-class_24.cpp)]  
  
##  <a name="a-namecrectoperator-a-crectoperator--"></a><a name="crect__operator_-"></a>  CRect::operator-  
 最初の 2 つのオーバー ロードが返す、 `CRect` オブジェクトと等しい `CRect` 指定したオフセット位置がずれている場合します。  
  
```  
 
CRect operator-(
POINT   
point) const throw();

CRect operator-(
SIZE   
size) const throw();

CRect operator-(
LPCRECT   
lpRect) const throw();

 
```  
  
### <a name="parameters"></a>パラメーター  
 `point`  
 A [ポイント](../../mfc/reference/point-structure1.md) 構造または `CPoint` 戻り値を移動する単位の数を指定するオブジェクト。  
  
 `size`  
 A [サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106) 構造または `CSize` 戻り値を移動する単位の数を指定するオブジェクト。  
  
 `lpRect`  
 指す、 [RECT](RECT%20Structure1.md) 構造または `CRect` 戻り値の各辺を圧縮する単位の数を格納しているオブジェクト。  
  
### <a name="return-value"></a>戻り値  
  `CRect` 移動または縮小された `CRect` パラメーターで指定されたユニット数。  
  
### <a name="remarks"></a>コメント  
 パラメーターの *x* と *y* (または `cx` と `cy`) からのパラメーターが減算されて `CRect`の位置します。  
  
 3 番目のオーバー ロードを返します新しい `CRect` の値が `CRect` 、パラメーターの各メンバーで指定された単位の数で縮小されました。 このオーバー ロードの機能を [DeflateRect](#crect__deflaterect), ではなく、 [SubtractRect](#crect__subtractrect)します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#66](../../atl-mfc-shared/codesnippet/CPP/crect-class_25.cpp)]  
  
##  <a name="a-namecrectoperatorampa-crectoperator-amp"></a><a name="crect__operator__amp_"></a>  CRect::operator &amp;  
 返します。、 `CRect` の積集合は `CRect` と *rect2*します。  
  
```  
 
CRect operator&(
const RECT& 
rect2) const throw();

 
```  
  
### <a name="parameters"></a>パラメーター  
 *rect2*  
 含む、 [RECT](RECT%20Structure1.md) または `CRect`です。  
  
### <a name="return-value"></a>戻り値  
 A `CRect` の積集合は `CRect` と *rect2*します。  
  
### <a name="remarks"></a>コメント  
 積集合は、両方の四角形に含まれる最大の四角形です。  
  
> [!NOTE]
>  四角形の両方を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます [NormalizeRect](#crect__normalizerect) をこの関数を呼び出す前に、四角形を正規化します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#67](../../atl-mfc-shared/codesnippet/CPP/crect-class_26.cpp)]  
  
##  <a name="a-namecrectoperatorora-crectoperator-124"></a><a name="crect__operator__or"></a>  CRect::operator & #124 文字です。  
 返します。、 `CRect` の共用体つまり `CRect` と *rect2*します。  
  
```  
 
CRect operator|(
const RECT& 
rect2) const throw();

 
```  
  
### <a name="parameters"></a>パラメーター  
 *rect2*  
 含む、 [RECT](RECT%20Structure1.md) または `CRect`です。  
  
### <a name="return-value"></a>戻り値  
 A `CRect` の共用体つまり `CRect` と *rect2*します。  
  
### <a name="remarks"></a>コメント  
 共用体は、両方の四角形を含む最小の四角形です。  
  
> [!NOTE]
>  四角形の両方を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます [NormalizeRect](#crect__normalizerect) をこの関数を呼び出す前に、四角形を正規化します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#68](../../atl-mfc-shared/codesnippet/CPP/crect-class_27.cpp)]  
  
##  <a name="a-namecrectptinrecta-crectptinrect"></a><a name="crect__ptinrect"></a>  CRect::PtInRect  
 内で指定したポイントにあるかどうかを調べます `CRect`します。  
  
```  
 
BOOL PtInRect(
POINT   
point) const throw();

 
```  
  
### <a name="parameters"></a>パラメーター  
 `point`  
 含む、 [ポイント](../../mfc/reference/point-structure1.md) 構造または [CPoint](../Topic/CPoint%20Class.md) オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 ポイントが内にある場合は 0 以外 `CRect`。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>コメント  
 点が `CRect` 左端または上端側である、4 辺すべて内にあるかどうか。 右端または下端にある点が範囲外です `CRect`します。  
  
> [!NOTE]
>  四角形を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます [NormalizeRect](#crect__normalizerect) をこの関数を呼び出す前に、四角形を正規化します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#51](../../atl-mfc-shared/codesnippet/CPP/crect-class_28.cpp)]  
  
##  <a name="a-namecrectsetrecta-crectsetrect"></a><a name="crect__setrect"></a>  CRect::SetRect  
 寸法を設定 `CRect` 指定した座標にします。  
  
```  
 
    void SetRect(
    int 
    x1 ,  
    int 
    y1 ,  
    int 
    x2 ,  
    int 
    y2) throw();

 
```  
  
### <a name="parameters"></a>パラメーター  
 `x1`  
 左上隅の x 座標を指定します。  
  
 `y1`  
 左上隅の y 座標を指定します。  
  
 `x2`  
 右下隅の x 座標を指定します。  
  
 `y2`  
 右下隅の y 座標を指定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#52](../../atl-mfc-shared/codesnippet/CPP/crect-class_29.cpp)]  
  
##  <a name="a-namecrectsetrectemptya-crectsetrectempty"></a><a name="crect__setrectempty"></a>  CRect::SetRectEmpty  
  `CRect` 空の四角形ですべての座標を 0 に設定します。  
  
```  
void SetRectEmpty() throw();
```  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#53](../../atl-mfc-shared/codesnippet/CPP/crect-class_30.cpp)]  
  
##  <a name="a-namecrectsizea-crectsize"></a><a name="crect__size"></a>  CRect::Size  
  `cx` と `cy` の幅と高さに戻り値のメンバーが含まれて `CRect`します。  
  
```  
CSize Size() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md) オブジェクトのサイズを含む `CRect`します。  
  
### <a name="remarks"></a>コメント  
 高さと幅のいずれかを負数にすることができます。  
  
> [!NOTE]
>  四角形を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます [NormalizeRect](#crect__normalizerect) をこの関数を呼び出す前に、四角形を正規化します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#54](../../atl-mfc-shared/codesnippet/CPP/crect-class_31.cpp)]  
  
##  <a name="a-namecrectsubtractrecta-crectsubtractrect"></a><a name="crect__subtractrect"></a>  CRect::SubtractRect  
 寸法を作成、 **CRect** の減算に等しい `lpRectSrc2` から `lpRectSrc1`します。  
  
```  
 
    BOOL SubtractRect(
    LPCRECT 
    lpRectSrc1 ,  
    LPCRECT 
    lpRectSrc2) throw();

 
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRectSrc1`  
 指す、 [RECT](RECT%20Structure1.md) 構造または `CRect` 四角形を減算する元のオブジェクト。  
  
 `lpRectSrc2`  
 指す、 `RECT` 構造または `CRect` によって指される四角形から減算するオブジェクト、 `lpRectSrc1` パラメーター。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 減算は、すべてのポイントを含む最小の四角形 `lpRectScr1` の積集合にされない `lpRectScr1` と *lpRectScr2*します。  
  
 指定された四角 `lpRectSrc1` を変更しないことで、四角形が指定された場合 `lpRectSrc2` によって指定された四角形を完全に重なっていない *lpRectSrc1* 少なくとも 1 つの x 方向または y 方向です。  
  
 たとえば場合、 `lpRectSrc1` された (10,10、100,100) と `lpRectSrc2` された (50,50、150,150)、四角形を指す `lpRectSrc1` は変更されず、関数が返されるときにします。 場合 `lpRectSrc1` されました (10,10、100,100) と `lpRectSrc2` された (50,10、150,150)、ただし、四角形を指す `lpRectSrc1` (10, 10, 50,100) 座標が含まれます関数が返されます。  
  
 `SubtractRect` 同じではありません [- 演算子](#crect__operator_-) も [演算子-=](#crect__operator_-_eq)です。 これらの演算子のどちらもこれまで呼び出し `SubtractRect`します。  
  
> [!NOTE]
>  四角形の両方を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます [NormalizeRect](#crect__normalizerect) をこの関数を呼び出す前に、四角形を正規化します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#55](../../atl-mfc-shared/codesnippet/CPP/crect-class_32.cpp)]  
  
##  <a name="a-namecrecttoplefta-crecttopleft"></a><a name="crect__topleft"></a>  CRect::TopLeft  
 座標がへの参照として返される、 [CPoint](../Topic/CPoint%20Class.md) オブジェクトに含まれている `CRect`します。  
  
```  
 
CPoint& TopLeft() throw();

const CPoint& TopLeft() const throw();

 
```  
  
### <a name="return-value"></a>戻り値  
 四角形の左上隅の座標。  
  
### <a name="remarks"></a>コメント  
 この関数は、取得、または四角形の左上隅を設定を使用することができます。 代入演算子の左側にあるこの関数を使用して、角を設定します。  
  
### <a name="example"></a>例  
 例を参照してください [CRect::CenterPoint](#crect__centerpoint)します。  
  
##  <a name="a-namecrectunionrecta-crectunionrect"></a><a name="crect__unionrect"></a>  CRect::UnionRect  
 ディメンションは、 `CRect` の 2 つのソース四角形の部分に相当します。  
  
```  
 
    BOOL UnionRect(
    LPCRECT 
    lpRect1 ,  
    LPCRECT 
    lpRect2) throw();

 
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect1`  
 指す、 [RECT](RECT%20Structure1.md) または `CRect` 元の四角形を格納しています。  
  
 `lpRect2`  
 指す、 `RECT` または `CRect` 元の四角形を格納しています。  
  
### <a name="return-value"></a>戻り値  
 和集合が空でない場合は 0 以外。和集合が空の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 共用体は、両方の四角形を含む最小の四角形です。  
  
 Windows は空の四角形の寸法は無視されます。四角形の高さがないか、幅がありません。  
  
> [!NOTE]
>  四角形の両方を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます [NormalizeRect](#crect__normalizerect) をこの関数を呼び出す前に、四角形を正規化します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#56](../../atl-mfc-shared/codesnippet/CPP/crect-class_33.cpp)]  
  
##  <a name="a-namecrectwidtha-crectwidth"></a><a name="crect__width"></a>  CRect::Width  
 幅を計算 `CRect` 適切な値から左の値を減算します。  
  
```  
int Width() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 幅 `CRect`します。  
  
### <a name="remarks"></a>コメント  
 幅を負数にすることができます。  
  
> [!NOTE]
>  四角形を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます [NormalizeRect](#crect__normalizerect) をこの関数を呼び出す前に、四角形を正規化します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATLMFC_Utilities#57](../../atl-mfc-shared/codesnippet/CPP/crect-class_34.cpp)]  
  
## <a name="see-also"></a>「  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CPoint クラス](../Topic/CPoint%20Class.md)   
 [CSize クラス](../../atl-mfc-shared/reference/csize-class.md)   
 [RECT](RECT%20Structure1.md)

