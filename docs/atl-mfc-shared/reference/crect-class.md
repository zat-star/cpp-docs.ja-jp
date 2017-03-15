---
title: "クラスを含む CRect |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRect
dev_langs:
- C++
helpviewer_keywords:
- LPCRECT data type
- CRect class
- LPRECT operator
- RECT structure
ms.assetid: dee4e752-15d6-4db4-b68f-1ad65b2ed6ca
caps.latest.revision: 24
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: fa528d300c546bfdeaab55ff88735efcaf8533a5
ms.lasthandoff: 02/24/2017

---
# <a name="crect-class"></a>CRect クラス
Windows のような[RECT](../../mfc/reference/rect-structure1.md)構造体。  
  
## <a name="syntax"></a>構文  
  
```  
class CRect : public tagRECT  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CRect::CRect](#crect)|`CRect` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CRect::BottomRight](#bottomright)|右下隅の点を返す`CRect`します。|  
|[CRect::CenterPoint](#centerpoint)|中心点を返す`CRect`します。|  
|[CRect::CopyRect](#copyrect)|コピーを元の四角形の寸法`CRect`します。|  
|[CRect::DeflateRect](#deflaterect)|幅と高さの減少`CRect`します。|  
|[CRect::EqualRect](#equalrect)|指定するかどうか`CRect`が指定された四角形と等しい。|  
|[CRect::Height](#height)|高さを計算`CRect`します。|  
|[CRect::InflateRect](#inflaterect)|幅と高さの増加`CRect`します。|  
|[CRect::IntersectRect](#intersectrect)|セット`CRect`の&2; つの四角形の交差部分に等しい。|  
|[CRect::IsRectEmpty](#isrectempty)|指定するかどうか`CRect`が空です。 `CRect`空の場合、幅や高さは 0 です。|  
|[CRect::IsRectNull](#isrectnull)|決定するかどうか、**上部**、**下部にある**、**左**、および**右**メンバー変数が 0 に等しいすべてです。|  
|[CRect::MoveToX](#movetox)|移動`CRect`指定した x 座標。|  
|[CRect::MoveToXY](#movetoxy)|移動`CRect`を指定した x 座標と y 座標。|  
|[CRect::MoveToY](#movetoy)|移動`CRect`に指定された座標の y 座標。|  
|[CRect::NormalizeRect](#normalizerect)|幅と高さを標準化`CRect`します。|  
|[CRect::OffsetRect](#offsetrect)|移動`CRect`指定されたオフセットします。|  
|[CRect::PtInRect](#ptinrect)|内で指定したポイントにあるかどうかを調べます`CRect`します。|  
|[CRect::SetRect](#setrect)|寸法を設定`CRect`します。|  
|[CRect::SetRectEmpty](#setrectempty)|セット`CRect`(すべての座標は 0 に等しい) 空の四角形にします。|  
|[CRect::Size](#size)|サイズを計算`CRect`します。|  
|[CRect::SubtractRect](#subtractrect)|別の&1; つの四角形を減算します。|  
|[CRect::TopLeft](#topleft)|左上の点を返す`CRect`します。|  
|[CRect::UnionRect](#unionrect)|セット`CRect`の&2; つの四角形の部分に相当します。|  
|[CRect::Width](#width)|幅を計算`CRect`します。|  
  
### <a name="public-operators"></a>パブリック演算子    
|名前|説明|  
|----------|-----------------|  
|[CRect::operator-](#operator_-)|指定したオフセットを減算`CRect`を縮小または`CRect`し、その結果を返します`CRect`します。|  
|[CRect::operator LPCRECT](#operator_lpcrect)|変換、`CRect`に、 **LPCRECT**します。|  
|[CRect::operator LPRECT](#operator_lprect)|変換、`CRect`に、`LPRECT`です。|  
|[CRect::operator! =](#operator_neq)|指定するかどうか`CRect`が四角形と等しくないです。|  
|[CRect::operator&amp;](#operator_amp)|積集合を作成`CRect`と四角形をその結果を返します`CRect`します。|  
|[CRect::operator&amp;=](#operator_amp_eq)|セット`CRect`の交差部分に等しい`CRect`と四角形。|  
|[CRect::operator |](#operator_or)|和集合を作成`CRect`と四角形、その結果を返すと`CRect`です。|  
|[CRect::operator |=](#operator_or_eq)|セット`CRect`の共用体に等しい`CRect`と四角形。|  
|[CRect::operator +](#operator_add)|指定したオフセットへの追加`CRect`拡張または`CRect`し、その結果を返します`CRect`します。|  
|[CRect::operator + = 演算子](#operator_add_eq)|指定したオフセット位置に追加`CRect`拡張または`CRect`です。|  
|[CRect::operator =](#operator_eq)|コピーする四角形の寸法`CRect`します。|  
|[CRect::operator =](#operator_-_eq)|指定されたオフセットを減算`CRect`を縮小または`CRect`です。|  
|[CRect::operator = =](#operator_eq_eq)|決定するかどうか`CRect`は四角形にします。|  
  
## <a name="remarks"></a>コメント  
 `CRect`操作するためのメンバー関数を含む`CRect`オブジェクトと Windows`RECT`構造体。  
  
 A`CRect`オブジェクトは、関数のパラメーターとして渡すことがであれば常に、`RECT`構造体、 **LPCRECT**、または`LPRECT`渡すことができます。  
  
> [!NOTE]
>  このクラスから派生、 **tagRECT**構造体。 (名前**tagRECT**なしに一般的に使用される名前で、`RECT`構造です)。つまり、このデータ メンバー (**左**、**上部**、**右**、および**下部**) の`RECT`構造のアクセス可能なデータ メンバーである`CRect`です。  
  
 A`CRect`四角形の左と右下隅の点を定義するメンバー変数が含まれています。  
  
 指定する場合、`CRect`は、正規化になるように構築する必要があります: つまり、左座標の値が右最上部より小さい結果が下より小さくします。 などの (10,&10;) の左、上と (20,&20;) の右下定義正規化された四角形が (20,&20;) の左し、(10,&10;) の右下が正規化されていない四角形を定義します。 多く、四角形が正規化されていない場合`CRect`メンバー関数が正しくない結果を返す可能性があります。 (参照[CRect::NormalizeRect](#normalizerect)これらの関数の一覧についてです)。正規化された四角形を必要とする関数を呼び出す前に呼び出すことによって正規化されていない四角形を正規化して、`NormalizeRect`関数です。  
  
 操作するときに警告を使用して、`CRect`で、 [CDC::DPtoLP](../../mfc/reference/cdc-class.md#dptolp)と[CDC::LPtoDP](../../mfc/reference/cdc-class.md#lptodp)メンバー関数。 ディスプレイ コンテキストのマッピング モードでが y 範囲が負の場合と同様になるよう`MM_LOENGLISH`、し、`CDC::DPtoLP`を変換する、`CRect`の最上位は、下部にあるより大きいようにします。 などの関数**高さ**と**サイズ**、変換後の高さに負の値が返される`CRect`、正規化されていない、四角形になります。  

  
 オーバー ロードを使用するときに`CRect`演算子、1 番目のオペランドである必要があります、 `CRect`;&2; つ目には、いずれかを指定できます、 [RECT](../../mfc/reference/rect-structure1.md)構造体、または`CRect`オブジェクトです。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `tagRECT`  
  
 `CRect`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atltypes.h  
  
##  <a name="a-namebottomrighta--crectbottomright"></a><a name="bottomright"></a>CRect::BottomRight  
 座標がへの参照として返される、 [CPoint](cpoint-class.md)オブジェクトに含まれている`CRect`します。  
  
```  
CPoint& BottomRight() throw();
const CPoint& BottomRight() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 四角形の右下隅の座標。  
  
### <a name="remarks"></a>コメント  
 この関数は、取得、または四角形の右下隅の設定を使用することができます。 代入演算子の左側にあるこの関数を使用して、角を設定します。  
  
### <a name="example"></a>例  
```cpp  
 // use BottomRight() to retrieve the bottom
 // right POINT 
 CRect rect(210, 150, 350, 900);
 CPoint ptDown;

 ptDown = rect.BottomRight();

 // ptDown is now set to (350, 900)
 ASSERT(ptDown == CPoint(350, 900));

 // or, use BottomRight() to set the bottom
 // right POINT 
 CRect rect2(10, 10, 350, 350);
 CPoint ptLow(180, 180);

   CRect rect2(10, 10, 350, 350);
   CPoint ptLow(180, 180);
rect2.BottomRight() = ptLow;

   // rect2 is now (10, 10, 180, 180)
   ASSERT(rect2 == CRect(10, 10, 180, 180));   
```
  
##  <a name="a-namecenterpointa--crectcenterpoint"></a><a name="centerpoint"></a>CRect::CenterPoint 
 中心点を計算`CRect`左と右の値を追加して、2 つで除算し、上端と下端の値を追加する&2; で除算しています。  
  
```  
CPoint CenterPoint() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 A`CPoint`の中心点であるオブジェクトを`CRect`します。  
  
### <a name="example"></a>例  
```cpp  
// Code from this OnPaint() implementation can be pasted into your own application
// to draw lines that would look like a letter "Y" within your dialog. 
void CMyDlg::OnPaint()
{
    CPaintDC dc(this);


    // device context for painting

    // get the size and position of the client area of 
    // your window

    CRect rect;
    GetClientRect(&rect);

    // Move the current pen to the top left of the window. We call the
    // TopLeft() member of CRect here and it returns a CPoint object we
    // pass to the override of CDC::MoveTo() that accepts a CPoint.

    dc.MoveTo(rect.TopLeft());

    // Draw a line from the top left to the center of the window.
    // CenterPoint() gives us the middle point of the window as a
    // CPoint, and since CDC::LineTo() has an override that accepts a
    // CPoint, we can just pass it along.

    dc.LineTo(rect.CenterPoint());

    // Now, draw a line to the top right of the window. There's no
    // CRect member which returns a CPoint for the top right of the
    // window, so we'll reference the CPoint members directly and call
    // the CDC::LineTo() override which takes two integers.

    dc.LineTo(rect.right, rect.top);

    // The top part of the "Y" is drawn. Now, we'll draw the stem. We
    // start from the center point.

    dc.MoveTo(rect.CenterPoint());

    // and then draw to the middle of the bottom edge of the window.
    // We'll get the x-coordinate from the x member of the CPOINT 
  // returned by CenterPoint(), and the y value comes directly from
    // the rect.

    dc.LineTo(rect.CenterPoint().x, rect.bottom);
}
```
  
##  <a name="a-namecopyrecta--crectcopyrect"></a><a name="copyrect"></a>CRect::CopyRect  
 コピー、`lpSrcRect`に四角形`CRect`します。  
  
```  
void CopyRect(LPCRECT lpSrcRect) throw(); 
```  
  
### <a name="parameters"></a>パラメーター  
 `lpSrcRect`  
 指す、 [RECT](../../mfc/reference/rect-structure1.md)構造または`CRect`オブジェクトのコピーです。  
  
### <a name="example"></a>例  
```cpp  
 CRect rectSource(35, 10, 125, 10);
 CRect rectDest;

 rectDest.CopyRect(&rectSource);

 // rectDest is now set to (35, 10, 125, 10)

 RECT rectSource2;
 rectSource2.left = 0;
 rectSource2.top = 0;
 rectSource2.bottom = 480;
 rectSource2.right = 640;

 rectDest.CopyRect(&rectSource2);

 // works against RECT structures, too!
 // rectDest is now set to (0, 0, 640, 480)   
```

  
##  <a name="a-namecrecta--crectcrect"></a><a name="crect"></a>CRect::CRect  
 `CRect` オブジェクトを構築します。  
  
```  
CRect() throw();
CRect(int l, int t, int r, int b) throw();
CRect(const RECT& srcRect) throw();
CRect(LPCRECT lpSrcRect) throw();
CRect(POINT point, SIZE size) throw();
CRect(POINT topLeft, POINT bottomRight) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 *l*  
 左の位置を示す`CRect`します。  
  
 *t*  
 先頭を示す`CRect`します。  
  
 *r*  
 右の位置を示す`CRect`します。  
  
 *b*  
 指定の下部にある`CRect`です。  
  
 *srcRect*  
 指す、 [RECT](../../mfc/reference/rect-structure1.md)の座標を含む構造体`CRect`します。  
  
 `lpSrcRect`  
 指す、`RECT`の座標を含む構造体`CRect`します。  
  
 `point`  
 構築される四角形の最初の場所を指定します。 左上隅に対応します。  
  
 `size`  
 左上隅から構築される四角形の右下隅までの距離を指定します。  
  
 *左上端*  
 左上の位置を示す`CRect`します。  
  
 *bottomRight*  
 右下の位置を示す`CRect`します。  
  
### <a name="remarks"></a>コメント  
 引数を指定しない場合**左**、**上部**、**右**、および**下部**メンバーは初期化されません。  
  
 `CRect`(**Const RECT >/documents/report1.rdl」の**) と`CRect`(**LPCRECT**) コンス トラクターで実行、 [CopyRect](#copyrect)します。 他のコンス トラクターでは、直接オブジェクトのメンバー変数を初期化します。  
  
### <a name="example"></a>例  
```cpp  
 // default constructor doesn't initialize!
 CRect rectUnknown;

 // four-integers are left, top, right, and bottom
 CRect rect(0, 0, 100, 50);
 ASSERT(rect.Width() == 100);
 ASSERT(rect.Height() == 50);

 // Initialize from RECT stucture
 RECT sdkRect;
 sdkRect.left = 0;
 sdkRect.top = 0;
 sdkRect.right = 100;
 sdkRect.bottom = 50;

 CRect rect2(sdkRect);
 // by reference
 CRect rect3(&sdkRect);


 // by address
 ASSERT(rect2 == rect);
 ASSERT(rect3 == rect);

 // from a point and a size
 CPoint pt(0, 0);
 CSize sz(100, 50);
 CRect rect4(pt, sz);
 ASSERT(rect4 == rect2);

 // from two points
 CPoint ptBottomRight(100, 50);
 CRect rect5(pt, ptBottomRight);
 ASSERT(rect5 == rect4);  
```
  
##  <a name="a-namedeflaterecta--crectdeflaterect"></a><a name="deflaterect"></a>CRect::DeflateRect  
 `DeflateRect`縮小`CRect`両側の中心に移行することができます。  
  
```  
void DeflateRect(int x, int y) throw();
void DeflateRect(SIZE size) throw();
void DeflateRect(LPCRECT lpRect) throw();
void DeflateRect(int l, int t, int r, int b) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 指定の左側を圧縮する単位の数および右側`CRect`します。  
  
 *y*  
 上下を圧縮する単位の数を指定`CRect`します。  
  
 `size`  
 A[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)または[CSize](csize-class.md) deflate する単位の数を指定する`CRect`です。 `cx`値左辺と右辺を圧縮する単位の数を指定し、`cy`値上部と下部を圧縮する単位の数を指定します。  
  
 `lpRect`  
 指す、 [RECT](../../mfc/reference/rect-structure1.md)構造または`CRect`各辺を縮小する単位の数を指定します。  
  
 *l*  
 左側にあるを圧縮する単位の数を指定`CRect`します。  
  
 *t*  
 先頭を圧縮する単位の数を指定`CRect`します。  
  
 *r*  
 右側にあるを圧縮する単位の数を指定`CRect`します。  
  
 *b*  
 下部にあるを圧縮する単位の数を指定`CRect`します。  
  
### <a name="remarks"></a>コメント  
 これを行う`DeflateRect`left および top にユニットを追加し、右や下から単位を減算します。 パラメーター`DeflateRect`は署名値は正の値が deflate`CRect`負の値は拡大とします。  
  
 最初の&2; つのオーバー ロードは、両方の反対側の組み合わせを縮小`CRect`2 倍、全体の幅が減少するよう*x* (または`cx`) し、2 回、全体の高さが減らさ*y* (または`cy`)。 その他の&2; つのオーバー ロードの各辺を縮小する`CRect`他のユーザーとは無関係にします。  
  
### <a name="example"></a>例  
```cpp  
   CRect rect(10, 10, 50, 50);
   rect.DeflateRect(1, 2);
   ASSERT(rect.left == 11 && rect.right == 49);
   ASSERT(rect.top == 12 && rect.bottom == 48);
   
   CRect rect2(10, 10, 50, 50);
   CRect rectDeflate(1, 2, 3, 4);
   rect2.DeflateRect(&rectDeflate);
   ASSERT(rect2.left == 11 && rect2.right == 47);
   ASSERT(rect2.top == 12 && rect2.bottom == 46);   
```
  
##  <a name="a-nameequalrecta--crectequalrect"></a><a name="equalrect"></a>CRect::EqualRect  
 指定するかどうか`CRect`が指定された四角形と等しい。  
  
```  
BOOL EqualRect(LPCRECT lpRect) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect`  
 指す、 [RECT](../../mfc/reference/rect-structure1.md)構造または`CRect`四角形の左上隅および右下隅の座標を格納しているオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 2 つの四角形は、同じ上、左、下、および右の値がある場合は 0 以外それ以外の場合 0 を返します。  
  
> [!NOTE]
>  四角形の両方を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。  
  
### <a name="example"></a>例  
```cpp  
   CRect rect1(35, 150, 10, 25);
   CRect rect2(35, 150, 10, 25);
   CRect rect3(98, 999, 6, 3);
ASSERT(rect1.EqualRect(rect2));
   ASSERT(!rect1.EqualRect(rect3));
 // works just fine against RECTs, as well

 RECT test;
 test.left = 35;
 test.top = 150;
 test.right = 10;
 test.bottom = 25;

 ASSERT(rect1.EqualRect(&test));  
```

##  <a name="a-nameheighta--crectheight"></a><a name="height"></a>CRect::Height  
 高さを計算`CRect`下部にある値から最上位の値を減算します。  
  
```  
int Height() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 高さ`CRect`します。  
  
### <a name="remarks"></a>コメント  
 結果として得られる値は、負の値で指定できます。  
  
> [!NOTE]
>  四角形を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。  
  
### <a name="example"></a>例  
```cpp  
 CRect rect(20, 30, 80, 70);
 int nHt = rect.Height();

```cpp  
   CRect rect(20, 30, 80, 70);
int nHt = rect.Height();

   // nHt is now 40
   ASSERT(nHt == 40);   
```

  
##  <a name="a-nameinflaterecta--crectinflaterect"></a><a name="inflaterect"></a>CRect::InflateRect  
 `InflateRect`拡張`CRect`中心から離れて、両側を移動しています。  
  
```  
void InflateRect(int x, int y) throw();
void InflateRect(SIZE size) throw();
void InflateRect(LPCRECT lpRect) throw();
void InflateRect(int l, int t, int r,  int b) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 左右を左に拡大するためのユニットの数を指定`CRect`します。  
  
 *y*  
 上下に拡大するためのユニットの数を指定`CRect`します。  
  
 `size`  
 A[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)または[CSize](csize-class.md)を拡大するためのユニットの数を指定する`CRect`です。 `cx`値を左辺と右辺を拡大するためのユニットの数を指定し、`cy`値を上下に拡大するためのユニットの数を指定します。  
  
 `lpRect`  
 指す、 [RECT](../../mfc/reference/rect-structure1.md)構造または`CRect`各辺を拡大する単位の数を指定します。  
  
 *l*  
 左側にあるを拡大するためのユニットの数を指定`CRect`します。  
  
 *t*  
 先頭を拡大するためのユニットの数を指定`CRect`します。  
  
 *r*  
 右側にあるを拡大するためのユニットの数を指定`CRect`します。  
  
 *b*  
 下部にあるを拡大するためのユニットの数を指定`CRect`します。  
  
### <a name="remarks"></a>コメント  
 これを行う`InflateRect`left および top から単位を減算し、その単位を右や下に追加します。 パラメーター`InflateRect`は署名値は正の値は拡大`CRect`し、負の値は縮小します。  
  
 最初の&2; つのオーバー ロードは、両方の反対側の組み合わせを拡大`CRect`、全体の幅が&2; 倍に増加できるように*x* (または`cx`)、全体の高さを&2; 倍に増やす*y* (または`cy`)。 その他の&2; つのオーバー ロードの各辺を拡大する`CRect`他のユーザーとは無関係にします。  
  
### <a name="example"></a>例  
```cpp  
 CRect rect(0, 0, 300, 300);
 rect.InflateRect(50, 200);

 // rect is now (-50, -200, 350, 500)
 ASSERT(rect == CRect(-50, -200, 350, 500));  
```
  
##  <a name="a-nameintersectrecta--crectintersectrect"></a><a name="intersectrect"></a>CRect::IntersectRect  
 により、`CRect`既存の&2; つの四角形の交差部分に等しい。  
  
```  
BOOL IntersectRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect1`  
 指す、 [RECT](../../mfc/reference/rect-structure1.md)構造または`CRect`を元の四角形を含むオブジェクト。  
  
 `lpRect2`  
 指す、`RECT`構造または`CRect`を元の四角形を含むオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 積集合が空でない場合は 0 以外。積集合が空の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 積集合は、両方の既存の四角形に含まれる最大の四角形です。  
  
> [!NOTE]
>  四角形の両方を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。  
  
### <a name="example"></a>例  
```cpp  
 CRect rectOne(125, 0, 150, 200);
 CRect rectTwo(0, 75, 350,  95);
 CRect rectInter;

```cpp  
   CRect rectOne(125,  0, 150, 200);
   CRect rectTwo(0, 75, 350, 95);
   CRect rectInter;

   rectInter.IntersectRect(rectOne, rectTwo);
 ASSERT(rectInter == CRect(125, 75, 150, 95));
 // operator &= can do the same task:

 CRect rectInter2 = rectOne;
 rectInter2 &= rectTwo;
 ASSERT(rectInter2 == CRect(125, 75, 150, 95));  
```
  
##  <a name="a-nameisrectemptya--crectisrectempty"></a><a name="isrectempty"></a>CRect::IsRectEmpty  
 指定するかどうか`CRect`が空です。  
  
```  
BOOL IsRectEmpty() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の値`CRect`が空の場合 0 場合`CRect`空ではありません。  
  
### <a name="remarks"></a>コメント  
 四角形は、空の場合、幅や高さは 0 または負の値です。 異なる`IsRectNull`、四角形のすべての座標は、0 であるかどうかを決定します。  
  
> [!NOTE]
>  四角形を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。  
  
### <a name="example"></a>例  
```cpp  
 CRect rectNone(0, 0, 0, 0);
 CRect rectSome(35, 50, 135, 150);

```cpp  
   CRect rectNone(0, 0, 0, 0);
   CRect rectSome(35, 50, 135, 150);
ASSERT(rectNone.IsRectEmpty());
   ASSERT(!rectSome.IsRectEmpty());
CRect rectEmpty(35, 35, 35, 35);
   ASSERT(rectEmpty.IsRectEmpty());   
```

  
##  <a name="a-nameisrectnulla--crectisrectnull"></a><a name="isrectnull"></a>CRect::IsRectNull  
 左上が下かどうかを決定し、右の値`CRect`が 0 に等しいすべてです。  
  
```  
BOOL IsRectNull() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の値`CRect`左、上の下し、右の値は 0。 それ以外の場合 0 です。  
  
### <a name="remarks"></a>コメント  
 異なる`IsRectEmpty`、四角形が空かどうかを決定します。  
  
### <a name="example"></a>例  
```cpp  
 CRect rectNone(0, 0, 0, 0);
 CRect rectSome(35, 50, 135, 150);

```cpp  
   CRect rectNone(0, 0, 0, 0);
   CRect rectSome(35, 50, 135, 150);
ASSERT(rectNone.IsRectNull());
   ASSERT(!rectSome.IsRectNull());
 // note that null means _all_ zeros

 CRect rectNotNull(0, 0, 35, 50);
 ASSERT(!rectNotNull.IsRectNull());  
```
  
##  <a name="a-namemovetoxa--crectmovetox"></a><a name="movetox"></a>CRect::MoveToX  
 指定された絶対 x 座標に四角形を移動するには、この関数を呼び出す*x*です。  
  
```  
void MoveToX(int x) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 四角形の左上隅の絶対 x 座標。  
  
### <a name="example"></a>例  
```cpp  
 CRect rect(0, 0, 100, 100);
 rect.MoveToX(10);

```cpp  
   CRect rect(0, 0, 100, 100);
rect.MoveToX(10);

   // rect is now (10, 0, 110, 100);
   ASSERT(rect == CRect(10, 0, 110, 100));   
```
  
##  <a name="a-namemovetoxya--crectmovetoxy"></a><a name="movetoxy"></a>CRect::MoveToXY  
 絶対 x 座標と y 座標を指定の四角形を移動するには、この関数を呼び出します。  
  
```  
void MoveToXY(int x, int y) throw();
void MoveToXY(POINT point) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 四角形の左上隅の絶対 x 座標。  
  
 *y*  
 四角形の左上隅の絶対 y 座標。  
  
 `point`  
 A**ポイント**四角形の絶対の左上隅を指定する構造体。  
  
### <a name="example"></a>例  
```cpp  
 CRect rect(0, 0, 100, 100);
 rect.MoveToXY(10, 10);

```cpp  
   CRect rect(0, 0, 100, 100);
   rect.MoveToXY(10, 10);
// rect is now (10, 10, 110, 110);
   ASSERT(rect == CRect(10, 10, 110, 110));   
```

  
##  <a name="a-namemovetoya--crectmovetoy"></a><a name="movetoy"></a>CRect::MoveToY  
 絶対座標の y 座標で指定された四角形を移動するには、この関数を呼び出す*y*します。  
  
```  
void MoveToY(int y) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 *y*  
 四角形の左上隅の絶対 y 座標。  
  
### <a name="example"></a>例  
```cpp  
 CRect rect(0, 0, 100, 100);
 rect.MoveToY(10);

```cpp  
   CRect rect(0, 0, 100, 100);
   rect.MoveToY(10);
// rect is now (0, 10, 100, 110);
   ASSERT(rect == CRect(0, 10, 100, 110));   
```

  
##  <a name="a-namenormalizerecta--crectnormalizerect"></a><a name="normalizerect"></a>CRect::NormalizeRect  
 正規化`CRect`幅と高さが正の値になるようです。  
  
```  
void NormalizeRect() throw();
```  
  
### <a name="remarks"></a>コメント  
 四角形を正規化&4; 分の作業領域を配置するため Windows が通常の座標を使用します。 `NormalizeRect`上端と下端の値を比較し、最上位は、下部にあるより大きい場合は、それらをスワップします。 同様に、左が右より大きい場合、左と右の値を交換します。 この関数は、別のマッピング モードを処理する場合に便利ですが、反転された四角形。  
  
> [!NOTE]
>  次`CRect`メンバー関数が正常に動作するために正規化された四角形を必要と:[高さ](#height)、[幅](#width)、[サイズ](#size)、 [IsRectEmpty](#isrectempty)、 [PtInRect](#ptinrect)、 [EqualRect](#equalrect)、 [UnionRect](#unionrect)、[示します](#intersectrect)、 [SubtractRect](#subtractrect)、[演算子 = =](#operator_eq_eq)、[演算子! =](#operator_neq)、[演算子 |](#operator_or)、[演算子 | =](#operator_or_eq)、[演算子 >/documents/report1.rdl」の](#operator_amp)、および[演算子 = <](#operator_amp_eq)します。  
  
### <a name="example"></a>例  
```cpp  
 CRect rect1(110, 100, 250, 310);
 CRect rect2(250, 310, 110, 100);

```cpp  
   CRect rect1(110, 100, 250, 310);
   CRect rect2(250, 310, 110, 100);
rect1.NormalizeRect();
   rect2.NormalizeRect();
 ASSERT(rect1 == rect2);  
```
  
##  <a name="a-nameoffsetrecta--crectoffsetrect"></a><a name="offsetrect"></a>CRect::OffsetRect  
 移動`CRect`指定されたオフセットします。  
  
```  
void OffsetRect(int x, int y) throw();
void OffsetRect(POINT point) throw();
void OffsetRect(SIZE size) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 *x*  
 左に移動する量を指定します。 負の値を左に移動する場合があります。  
  
 *y*  
 上下に移動する量を指定します。 上に移動する負の値がある場合があります。  
  
 `point`  
 含む、[ポイント](../../mfc/reference/point-structure1.md)構造または[CPoint](cpoint-class.md)移動に使用する寸法の両方を指定するオブジェクト。  
  
 `size`  
 含む、[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)構造または[CSize](csize-class.md)移動に使用する寸法の両方を指定するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 移動`CRect` *x* 、x 軸に沿った単位と*y* y 軸に沿った単位です。 *X*と*y*パラメーターは、符号付きの値をそのため、`CRect`をし、左に移動できるまたは右上または下です。  
  
### <a name="example"></a>例  
```cpp  
 CRect rect(0, 0, 35, 35);
 rect.OffsetRect(230, 230);

```cpp  
   CRect rect(0, 0, 35, 35);
   rect.OffsetRect(230, 230);

   // rect is now (230, 230, 265, 265)
   ASSERT(rect == CRect(230, 230, 265, 265));   
```

  
##  <a name="a-nameoperatorlpcrecta--crectoperator-lpcrect-converts-a-crect-to-an-lpcrectmfcreferencedata-types-mfcmd"></a><a name="operator_lpcrect"></a>CRect::operator LPCRECT 変換、`CRect`に、 [LPCRECT](../../mfc/reference/data-types-mfc.md)します。  

  
```  
operator LPCRECT() const throw();
```  
  
### <a name="remarks"></a>コメント  
 この関数を使用するときのアドレスがなくても (**&**) 演算子。 この演算子は渡すときに自動的に使用、`CRect`オブジェクトを受け取る関数を**LPCRECT**します。  
  

##  <a name="a-nameoperatorlprecta--crectoperator-lprect"></a><a name="operator_lprect"></a>CRect::operator LPRECT  
 変換、`CRect`に、 [LPRECT](../../mfc/reference/data-types-mfc.md)します。  

  
```
operator LPRECT() throw();
```  
  
### <a name="remarks"></a>コメント  
 この関数を使用するときのアドレスがなくても (**&**) 演算子。 この演算子は渡すときに自動的に使用、`CRect`オブジェクトを受け取る関数を`LPRECT`です。  
  
### <a name="example"></a>例  
 例を参照してください[CRect::operator LPCRECT](#operator_lpcrect)します。  
  
##  <a name="a-nameoperatoreqa--crectoperator-"></a><a name="operator_eq"></a>CRect::operator =  
 割り当てる*srcRect*に`CRect`します。  
  
```  
void operator=(const RECT& srcRect) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *srcRect*  
 元の四角形を指します。 Can be a [RECT](../../mfc/reference/rect-structure1.md) or `CRect`.  
  
### <a name="example"></a>例  
```cpp  
 CRect rect(0, 0, 127, 168);
 CRect rect2;

```cpp  
   CRect rect(0, 0, 127, 168);
   CRect rect2;

   rect2 = rect;
   ASSERT(rect2 == CRect(0, 0, 127, 168));   
```

  
##  <a name="a-nameoperatoreqeqa--crectoperator-"></a><a name="operator_eq_eq"></a>CRect::operator = =  
 決定するかどうか`rect`に等しい`CRect`左上隅および右下隅の座標を比較することによってです。  
  
```  
BOOL operator==(const RECT& rect) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `rect`  
 元の四角形を指します。 Can be a [RECT](../../mfc/reference/rect-structure1.md) or `CRect`.  
  
### <a name="return-value"></a>戻り値  
 等しい場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  四角形の両方を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。  
  
### <a name="example"></a>例  
```cpp  
 CRect rect1(35, 150, 10, 25);
 CRect rect2(35, 150, 10, 25);
 CRect rect3(98, 999,  6,  3);

```cpp  
   CRect rect1(35, 150, 10, 25);
   CRect rect2(35, 150, 10, 25);
   CRect rect3(98, 999, 6, 3);
ASSERT(rect1 == rect2);
 // works just fine against RECTs, as well

 RECT test;
 test.left = 35;
 test.top = 150;
 test.right = 10;
 test.bottom = 25;

 ASSERT(rect1 == test);  
```

  
##  <a name="a-nameoperatorneqa--crectoperator-"></a><a name="operator_neq"></a>CRect::operator! =  
 決定するかどうか`rect`と等しくない`CRect`左上隅および右下隅の座標を比較することによってです。  
  
```  
BOOL operator!=(const RECT& rect) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `rect`  
 元の四角形を指します。 Can be a [RECT](../../mfc/reference/rect-structure1.md) or `CRect`.  
  
### <a name="return-value"></a>戻り値  
 等しくない場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
  
> [!NOTE]
>  四角形の両方を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。  
  
### <a name="example"></a>例  
```cpp  
 CRect rect1(35, 150, 10, 25);
 CRect rect2(35, 150, 10, 25);
 CRect rect3(98, 999,  6,  3);

```cpp  
   CRect rect1(35, 150, 10, 25);
   CRect rect2(35, 150, 10, 25);
   CRect rect3(98, 999, 6, 3);
ASSERT(rect1 != rect3);
 // works just fine against RECTs, as well

 RECT test;
 test.left = 35;
 test.top = 150;
 test.right = 10;
 test.bottom = 25;

 ASSERT(rect3 != test);  
```
  
##  <a name="a-nameoperatoraddeqa--crectoperator-"></a><a name="operator_add_eq"></a>CRect::operator + = 演算子  
 最初の&2; つのオーバー ロードは、移動`CRect`指定されたオフセットします。  
  
```  
void operator+=(POINT point) throw();
void operator+=(SIZE size) throw();
void operator+=(LPCRECT lpRect) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `point`  
 A[ポイント](../../mfc/reference/point-structure1.md)構造または[CPoint](cpoint-class.md)四角形を移動する単位の数を指定するオブジェクト。  
  
 `size`  
 A[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)構造または[CSize](csize-class.md)四角形を移動する単位の数を指定するオブジェクト。  
  
 `lpRect`  
 指す、 [RECT](../../mfc/reference/rect-structure1.md)構造または`CRect`の各辺拡大する単位の数を格納しているオブジェクト`CRect`します。  
  
### <a name="remarks"></a>コメント  
 パラメーターの*x*と*y* (または`cx`と`cy`) 値に追加する`CRect`です。  
  
 3 番目のオーバー ロードだけ`CRect`パラメーターの各メンバーで指定された単位の数。  
  
### <a name="example"></a>例  
```cpp  
 CRect rect1(100, 235, 200, 335);
 CPoint pt(35, 65);
 CRect rect2(135, 300, 235, 400);

```cpp  
   CRect   rect1(100, 235, 200, 335);
   CPoint pt(35, 65);
   CRect   rect2(135, 300, 235, 400);

   rect1 += pt;
   ASSERT(rect1 == rect2);   
```
  
##  <a name="a-nameoperator-eqa--crectoperator--"></a><a name="operator_-_eq"></a>CRect::operator =  
 最初の&2; つのオーバー ロードは、移動`CRect`指定されたオフセットします。  
  
```  
void operator-=(POINT point) throw();
void operator-=(SIZE size) throw();
void operator-=(LPCRECT lpRect) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `point`  
 A[ポイント](../../mfc/reference/point-structure1.md)構造または[CPoint](cpoint-class.md)四角形を移動する単位の数を指定するオブジェクト。  
  
 `size`  
 A[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)構造または[CSize](csize-class.md)四角形を移動する単位の数を指定するオブジェクト。  
  
 `lpRect`  
 指す、 [RECT](../../mfc/reference/rect-structure1.md)構造または`CRect`の各辺を圧縮する単位の数を格納しているオブジェクト`CRect`します。  
  
### <a name="remarks"></a>コメント  
 パラメーターの*x*と*y* (または`cx`と`cy`) から値を減算する`CRect`です。  
  
 3 番目のオーバー ロードを縮小`CRect`パラメーターの各メンバーで指定された単位の数。 このオーバー ロードの機能を[DeflateRect](#deflaterect)します。  
  
### <a name="example"></a>例  
```cpp  
 CRect rect1(100, 235, 200, 335);
 CPoint pt(35, 65);
 rect1 -= pt;

```cpp  
   CRect   rect1(100, 235, 200, 335);
   CPoint pt(35, 65);

   rect1 -= pt;
   CRect   rectResult(65, 170, 165, 270);
   ASSERT(rect1 == rectResult);   
```
  
##  <a name="a-nameoperatorampeqa--crectoperator-amp"></a><a name="operator_amp_eq"></a>CRect::operator&amp;=  
 セット`CRect`の交差部分に等しい`CRect`と`rect`です。  
  
```  
void operator&=(const RECT& rect) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `rect`  
 含む、 [RECT](../../mfc/reference/rect-structure1.md)または`CRect`です。  
  
### <a name="remarks"></a>コメント  
 積集合は、両方の四角形に含まれる最大の四角形です。  
  
> [!NOTE]
>  四角形の両方を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。  
  
### <a name="example"></a>例  
 例を参照してください[CRect::IntersectRect](#intersectrect)します。  
  
##  <a name="a-nameoperatororeqa--crectoperator-124"></a><a name="operator_or_eq"></a>CRect::operator | =  
 セット`CRect`の共用体に等しい`CRect`と`rect`です。  
  
```  
void operator|=(const RECT& rect) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `rect`  
 含む、`CRect`または[RECT](../../mfc/reference/rect-structure1.md)します。  
  
### <a name="remarks"></a>コメント  
 共用体は、両方の四角形を含む最小の四角形です。  
  
> [!NOTE]
>  四角形の両方を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。  
  
### <a name="example"></a>例  
```cpp  
 CRect rect1(100,   0, 200, 300);
 CRect rect2( 0, 100, 300, 200);
 rect1 |= rect2;

```cpp  
   CRect   rect1(100,  0, 200, 300);
   CRect   rect2(0, 100, 300, 200);

   rect1 |= rect2;
   CRect   rectResult(0, 0, 300, 300);
   ASSERT(rectResult == rect1);   
```

  
##  <a name="a-nameoperatoradda--crectoperator-"></a><a name="operator_add"></a>CRect::operator +  
 最初の&2; つのオーバー ロードが返す、`CRect`オブジェクトと等しい`CRect`指定したオフセット位置がずれている場合します。  
  
```  
CRect operator+(POINT point) const throw();
CRect operator+(LPCRECT lpRect) const throw();
CRect operator+(SIZE size) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `point`  
 A[ポイント](../../mfc/reference/point-structure1.md)構造または[CPoint](cpoint-class.md)戻り値を移動する単位の数を指定するオブジェクト。  
  
 `size`  
 A[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)構造または[CSize](csize-class.md)戻り値を移動する単位の数を指定するオブジェクト。  
  
 `lpRect`  
 指す、 [RECT](../../mfc/reference/rect-structure1.md)構造または`CRect`戻り値の各辺を拡大する単位の数を格納しているオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 `CRect`移動または増やして`CRect`パラメーターで指定されたユニットの数でします。  
  
### <a name="remarks"></a>コメント  
 パラメーターの*x*と*y* (または`cx`と`cy`) にパラメーターが追加される`CRect`の位置します。  
  
 3 番目のメソッドの戻り値の新しい`CRect`の値が`CRect`膨らませると各メンバーのパラメーターで指定された単位の数。  
  
### <a name="example"></a>例  
```cpp  
   CRect   rect1(100, 235, 200, 335);
   CPoint pt(35, 65);
   CRect   rect2;

   rect2 = rect1 + pt;
   CRect   rectResult(135, 300, 235, 400);
   ASSERT(rectResult == rect2);   
```

  
##  <a name="a-nameoperator-a--crectoperator--"></a><a name="operator_-"></a>CRect::operator-  
 最初の&2; つのオーバー ロードが返す、`CRect`オブジェクトと等しい`CRect`指定したオフセット位置がずれている場合します。  
  
```  
CRect operator-(POINT point) const throw();
CRect operator-(SIZE size) const throw();
CRect operator-(LPCRECT lpRect) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `point`  
 A[ポイント](../../mfc/reference/point-structure1.md)構造または`CPoint`戻り値を移動する単位の数を指定するオブジェクト。  
  
 `size`  
 A[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)構造または`CSize`戻り値を移動する単位の数を指定するオブジェクト。  
  
 `lpRect`  
 指す、 [RECT](../../mfc/reference/rect-structure1.md)構造または`CRect`戻り値の各辺を圧縮する単位の数を格納しているオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 `CRect`移動または縮小された`CRect`パラメーターで指定されたユニット数。  
  
### <a name="remarks"></a>コメント  
 パラメーターの*x*と*y* (または`cx`と`cy`) からのパラメーターが減算されて`CRect`の位置します。  
  
 新しい&3; つ目のオーバー ロードを返します`CRect`の値が`CRect`パラメーターの各メンバーで指定された単位の数で縮小します。 このオーバー ロードの機能を[DeflateRect](#deflaterect)ではなく、 [SubtractRect](#subtractrect)します。  
  
### <a name="example"></a>例  
```cpp  
   CRect   rect1(100, 235, 200, 335);
   CPoint pt(35, 65);
   CRect   rect2;

   rect2 = rect1 - pt;
   CRect   rectResult(65, 170, 165, 270);
   ASSERT(rect2 == rectResult);   
```

  
##  <a name="a-nameoperatorampa--crectoperator-amp"></a><a name="operator_amp"></a>CRect::operator&amp;  
 返します。、`CRect`の積集合は`CRect`と*rect2*します。  
  
```  
CRect operator&(const RECT& rect2) const throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *rect2*  
 含む、 [RECT](../../mfc/reference/rect-structure1.md)または`CRect`です。  
  
### <a name="return-value"></a>戻り値  
 A`CRect`の積集合は`CRect`と*rect2*します。  
  
### <a name="remarks"></a>コメント  
 積集合は、両方の四角形に含まれる最大の四角形です。  
  
> [!NOTE]
>  四角形の両方を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。  
  
### <a name="example"></a>例  
```cpp  
   CRect   rect1(100,  0, 200, 300);
   CRect   rect2(0, 100, 300, 200);
   CRect   rect3;

   rect3 = rect1 & rect2;
   CRect   rectResult(100, 100, 200, 200);
   ASSERT(rectResult == rect3);   
```

  
##  <a name="a-nameoperatorora--crectoperator-124"></a><a name="operator_or"></a>CRect::operator |  
 返します。、`CRect`の共用体つまり`CRect`と*rect2*します。  
  
```   
CRect operator|(const RECT& 
rect2) const throw(); 
```  
  
### <a name="parameters"></a>パラメーター  
 *rect2*  
 含む、 [RECT](../../mfc/reference/rect-structure1.md)または`CRect`です。  
  
### <a name="return-value"></a>戻り値  
 A`CRect`の共用体つまり`CRect`と*rect2*します。  
  
### <a name="remarks"></a>コメント  
 共用体は、両方の四角形を含む最小の四角形です。  
  
> [!NOTE]
>  四角形の両方を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。  
  
### <a name="example"></a>例  
```cpp  
 CRect rect1(100,   0, 200, 300);
 CRect rect2( 0, 100, 300, 200);
 CRect rect3;

```cpp  
   CRect   rect1(100,  0, 200, 300);
   CRect   rect2(0, 100, 300, 200);
   CRect   rect3;

   rect3 = rect1 | rect2;
   CRect   rectResult(0, 0, 300, 300);
   ASSERT(rectResult == rect3);   
```

  
##  <a name="a-nameptinrecta--crectptinrect"></a><a name="ptinrect"></a>CRect::PtInRect  
 内で指定したポイントにあるかどうかを調べます`CRect`します。  
  
```   
BOOL PtInRect(POINT point) const throw(); 
```  
  
### <a name="parameters"></a>パラメーター  
 `point`  
 含む、[ポイント](../../mfc/reference/point-structure1.md)構造または[CPoint](cpoint-class.md)オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 ポイントが内にある場合は 0 以外`CRect`。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>コメント  
 点が`CRect`左端または上端側である、4 辺すべて内にあるかどうか。 右端または下端にある点が範囲外です`CRect`します。  
  
> [!NOTE]
>  四角形を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。  
  
### <a name="example"></a>例  
```cpp  
 CRect rect(5, 5, 100, 100);
 CPoint pt1(35, 50);
 CPoint pt2(125, 298);

 // this is true, because pt1 is inside the rectangle
 ASSERT(rect.PtInRect(pt1));

 // this is NOT true, because pt2 is outside the rectangle
 ASSERT(!rect.PtInRect(pt2));

 // note that the right and the bottom aren't inside
 ASSERT(!rect.PtInRect(CPoint(35, 100)));
 ASSERT(!rect.PtInRect(CPoint(100, 98)));

 // but the top and the left are inside
 ASSERT(rect.PtInRect(CPoint(5, 65)));
 ASSERT(rect.PtInRect(CPoint(88, 5)));

 // and that PtInRect() works against a POINT, too
 POINT pt;
 pt.x = 35;
 pt.y = 50;
 ASSERT(rect.PtInRect(pt));  
```
  
##  <a name="a-namesetrecta--crectsetrect"></a><a name="setrect"></a>CRect::SetRect  
 寸法を設定`CRect`指定した座標にします。  
  
```   
void SetRect(int x1, int y1, int x2, int y2) throw(); 
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
```cpp  
 CRect rect;
 rect.SetRect(256, 256, 512, 512);

```cpp  
   CRect rect;
   rect.SetRect(256, 256, 512, 512);
   ASSERT(rect == CRect(256, 256, 512, 512));   
```

  
##  <a name="a-namesetrectemptya--crectsetrectempty"></a><a name="setrectempty"></a>CRect::SetRectEmpty  
 `CRect`空の四角形ですべての座標を&0; に設定します。  
  
```  
void SetRectEmpty() throw();
```  
  
### <a name="example"></a>例  
```cpp  
CRect rect;
rect.SetRectEmpty();

// rect is now (0, 0, 0, 0)
ASSERT(rect.IsRectEmpty());  
```
  
##  <a name="a-namesizea--crectsize"></a><a name="size"></a>CRect::SIZE 
 `cx`と`cy`の幅と高さに戻り値のメンバーが含まれて`CRect`します。  
  
```  
CSize Size() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 A [CSize](csize-class.md)オブジェクトのサイズを含む`CRect`します。  
  
### <a name="remarks"></a>コメント  
 高さと幅のいずれかを負数にすることができます。  
  
> [!NOTE]
>  四角形を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。  
  
### <a name="example"></a>例  
```cpp  
 CRect rect(10, 10, 50, 50);
 CSize sz = rect.Size();
 ASSERT(sz.cx == 40 && sz.cy == 40);  
```

##  <a name="a-namesubtractrecta--crectsubtractrect"></a><a name="subtractrect"></a>CRect::SubtractRect  
 寸法を作成、 **CRect**の減算に等しい`lpRectSrc2`から`lpRectSrc1`します。  
  
```  
BOOL SubtractRect(LPCRECT lpRectSrc1, LPCRECT lpRectSrc2) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRectSrc1`  
 指す、 [RECT](../../mfc/reference/rect-structure1.md)構造または`CRect`四角形を減算する元のオブジェクト。  
  
 `lpRectSrc2`  
 指す、`RECT`構造または`CRect`によって指される四角形から減算するオブジェクト、`lpRectSrc1`パラメーター。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 減算は、すべてのポイントを含む最小の四角形`lpRectScr1`の積集合にされない`lpRectScr1`と*lpRectScr2*します。  
  
 指定された四角`lpRectSrc1`を変更しないことで、四角形が指定された場合`lpRectSrc2`によって指定された四角形を完全に重なっていない*lpRectSrc1*少なくとも&1; つの x 方向または y 方向です。  
  
 たとえば場合、`lpRectSrc1`された (10,10、100,100) と`lpRectSrc2`された (50,50、150,150)、四角形を指す`lpRectSrc1`は変更されず、関数が返されるときにします。 場合`lpRectSrc1`されました (10,10、100,100) と`lpRectSrc2`された (50,10、150,150)、ただし、四角形を指す`lpRectSrc1`(10, 10, 50,100) 座標が含まれます関数が返されます。  
  
 `SubtractRect`同じではありません[- 演算子](#operator_-)も[演算子-=](#operator_-_eq)です。 これらの演算子のどちらもこれまで呼び出し`SubtractRect`します。  
  
> [!NOTE]
>  四角形の両方を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。  
  
### <a name="example"></a>例  
```cpp  
   RECT   rectOne;
   RECT   rectTwo;

   rectOne.left = 10;
   rectOne.top = 10;
   rectOne.bottom = 100;
   rectOne.right = 100;

   rectTwo.left = 50;
   rectTwo.top = 10;
   rectTwo.bottom = 150;
   rectTwo.right = 150;

   CRect   rectDiff;

   rectDiff.SubtractRect(&rectOne, &rectTwo);
CRect   rectResult(10, 10, 50, 100);

   ASSERT(rectDiff == rectResult);

   // works for CRect, too, since there is
   // implicit CRect -> LPCRECT conversion

   CRect rect1(10, 10, 100, 100);
   CRect rect2(50, 10, 150, 150);
   CRect rectOut;

   rectOut.SubtractRect(rect1, rect2);
   ASSERT(rectResult == rectOut);   
```
  
##  <a name="a-nametoplefta--crecttopleft"></a><a name="topleft"></a>CRect::TopLeft  
 座標がへの参照として返される、 [CPoint](cpoint-class.md)オブジェクトに含まれている`CRect`します。  
  
```  
CPoint& TopLeft() throw();
const CPoint& TopLeft() const throw(); 
```  
  
### <a name="return-value"></a>戻り値  
 四角形の左上隅の座標。  
  
### <a name="remarks"></a>コメント  
 この関数は、取得、または四角形の左上隅を設定を使用することができます。 代入演算子の左側にあるこの関数を使用して、角を設定します。  
  
### <a name="example"></a>例  
 例を参照してください[CRect::CenterPoint](#centerpoint)します。  
  
##  <a name="a-nameunionrecta--crectunionrect"></a><a name="unionrect"></a>CRect::UnionRect  
 ディメンションは、`CRect`の&2; つのソース四角形の部分に相当します。  
  
```  
BOOL UnionRect(LPCRECT lpRect1, LPCRECT lpRect2) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `lpRect1`  
 指す、 [RECT](../../mfc/reference/rect-structure1.md)または`CRect`元の四角形を格納しています。  
  
 `lpRect2`  
 指す、`RECT`または`CRect`元の四角形を格納しています。  
  
### <a name="return-value"></a>戻り値  
 和集合が空でない場合は 0 以外。和集合が空の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 共用体は、両方の四角形を含む最小の四角形です。  
  
 Windows は空の四角形の寸法は無視されます。四角形の高さがないか、幅がありません。  
  
> [!NOTE]
>  四角形の両方を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。  
  
### <a name="example"></a>例  
```cpp  
   CRect   rect1(100,  0, 200, 300);
   CRect   rect2(0, 100, 300, 200);
   CRect   rect3;

   rect3.UnionRect(&rect1, &rect2);
   CRect   rectResult(0, 0, 300, 300);
   ASSERT(rectResult == rect3);   
```
 
##  <a name="a-namewidtha--crectwidth"></a><a name="width"></a>CRect::Width  
 幅を計算`CRect`適切な値から左の値を減算します。  
  
```  
int Width() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 幅`CRect`します。  
  
### <a name="remarks"></a>コメント  
 幅を負数にすることができます。  
  
> [!NOTE]
>  四角形を正規化する必要がありますか、この関数が失敗する可能性があります。 呼び出すことができます[NormalizeRect](#normalizerect)をこの関数を呼び出す前に、四角形を正規化します。  
  
### <a name="example"></a>例  

```cpp  
   CRect rect(20, 30, 80, 70);
int nWid = rect.Width();
   // nWid is now 60
   ASSERT(nWid == 60);   
```
## <a name="see-also"></a>関連項目  
 [CPoint クラス](cpoint-class.md)   
 [CSize クラス](csize-class.md)   
 [RECT](../../mfc/reference/rect-structure1.md)



