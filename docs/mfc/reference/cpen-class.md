---
title: "CPen クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPen
- AFXWIN/CPen
- AFXWIN/CPen::CPen
- AFXWIN/CPen::CreatePen
- AFXWIN/CPen::CreatePenIndirect
- AFXWIN/CPen::FromHandle
- AFXWIN/CPen::GetExtLogPen
- AFXWIN/CPen::GetLogPen
dev_langs:
- C++
helpviewer_keywords:
- HPEN
- CPen class
- pens, MFC
ms.assetid: 93175a3a-d46c-4768-be8d-863254f97a5f
caps.latest.revision: 20
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
ms.openlocfilehash: edea12c84a8f39161acbf367360fd86a1ff19998
ms.lasthandoff: 02/24/2017

---
# <a name="cpen-class"></a>CPen クラス
Windows のグラフィック デバイス インターフェイス (GDI) のペンをカプセル化したものです。  
  
## <a name="syntax"></a>構文  
  
```  
class CPen : public CGdiObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CPen::CPen](#cpen)|`CPen` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CPen::CreatePen](#createpen)|指定したスタイル、幅、およびブラシ属性と論理表面的または幾何学的ペンを作成し、それにアタッチ、`CPen`オブジェクトです。|  
|[CPen::CreatePenIndirect](#createpenindirect)|スタイル、幅、および色でペンを作成、 [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041)構造、およびそれにアタッチ、`CPen`オブジェクトです。|  
|[CPen::FromHandle](#fromhandle)|ポインターを返す、 `CPen` Windows が指定されると`HPEN`です。|  
|[CPen::GetExtLogPen](#getextlogpen)|取得、[保持](http://msdn.microsoft.com/library/windows/desktop/dd162711)構造体の基になります。|  
|[CPen::GetLogPen](#getlogpen)|取得、 [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041)構造体の基になります。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CPen::operator HPEN](#operator_hpen)|接続されている Windows ハンドルを返す、`CPen`オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 使用する方法について`CPen`を参照してください[グラフィック オブジェクト](../../mfc/graphic-objects.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CGdiObject](../../mfc/reference/cgdiobject-class.md)  
  
 `CPen`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
##  <a name="cpen"></a>CPen::CPen  
 `CPen` オブジェクトを構築します。  
  
```  
CPen();

 
CPen(
    int nPenStyle,  
    int nWidth,  
    COLORREF crColor);

 
CPen(
    int nPenStyle,  
    int nWidth,  
    const LOGBRUSH* pLogBrush,  
    int nStyleCount = 0,  
    const DWORD* lpStyle = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `nPenStyle`  
 ペンのスタイルを指定します。 コンス トラクターの最初のバージョンでは、このパラメーターは、次の値のいずれかになります。  
  
- **きは**ソリッド ペンを作成します。  
  
- **PS_DASH**破線のペンを作成します。 ペンの幅が 1 またはそれ以下のデバイスでの単位である場合にのみ有効です。  
  
- **PS_DOT**ピリオドで区切られたペンを作成します。 ペンの幅が 1 またはそれ以下のデバイスでの単位である場合にのみ有効です。  
  
- **PS_DASHDOT**の代替ダッシュとドットでペンを作成します。 ペンの幅が 1 またはそれ以下のデバイスでの単位である場合にのみ有効です。  
  
- **PS_DASHDOTDOT**の代替ダッシュと&2; つのドットでペンを作成します。 ペンの幅が 1 またはそれ以下のデバイスでの単位である場合にのみ有効です。  
  
- **必ず**null ペンを作成します。  
  
- **ペン**外接する四角形を指定する Windows GDI の出力関数によって生成される、閉じた図形のフレーム内の行を描画するペンを作成 (たとえば、**楕円**、**四角形**、 `RoundRect`、 `Pie`、および`Chord`メンバー関数)。 外接する四角形が指定されていない Windows GDI 関数と共にこのスタイルを使用した場合 (たとえば、`LineTo`メンバー関数)、ペンの描画領域は、フレームによって制限されません。  
  
 第&2; のバージョン、`CPen`コンス トラクターは、種類、スタイル、端点キャップ、および結合の属性の組み合わせを指定します。 各カテゴリの値は、ビットごとの OR 演算子 (|) を使用して組み合わせる必要があります。 ペンの種類には、次の値のいずれかを指定できます。  
  
- **PS_GEOMETRIC**幾何学模様のペンを作成します。  
  
- **PS_COSMETIC**表面的でペンを作成します。  
  
     第&2; のバージョン、`CPen`コンス トラクターの次のペンのスタイルを追加する`nPenStyle`:  
  
- **PS_ALTERNATE**他のすべてのピクセルを設定するペンを作成します。 (このスタイルは、表面的でペンにのみ適用)。  
  
- **PS_USERSTYLE**ユーザーが指定したスタイルの配列を使用するペンを作成します。  
  
     端点キャップには、次の値のいずれかを指定できます。  
  
- **PS_ENDCAP_ROUND**端点キャップ、round します。  
  
- **PS_ENDCAP_SQUARE**端点キャップが四角形。  
  
- **PS_ENDCAP_FLAT**端点キャップがフラットです。  
  
     結合は、次の値のいずれかになります。  
  
- **PS_JOIN_BEVEL**斜め結合します。  
  
- **PS_JOIN_MITER**結合はマイターによって設定された現在の制限内にいるときに、 [SetMiterLimit](http://msdn.microsoft.com/library/windows/desktop/dd145076)関数です。 結合は、この上限を超えている場合は斜めです。  
  
- **PS_JOIN_ROUND**の結合がラウンドです。  
  
 `nWidth`  
 ペンの幅を指定します。  
  
-   コンス トラクターの最初のバージョンのこの値が 0 の場合、幅デバイス単位では常にマッピング モードに関係なく、1 ピクセルです。  
  
-   コンス トラクターの&2; 番目のバージョンの場合`nPenStyle`は**PS_GEOMETRIC**幅を論理単位で指定します。 場合`nPenStyle`は**PS_COSMETIC**幅が 1 に設定する必要があります。  
  
 `crColor`  
 ペンの RGB の色が含まれています。  
  
 `pLogBrush`  
 指す、`LOGBRUSH`構造体。 場合`nPenStyle`は**PS_COSMETIC**、`lbColor`のメンバー、`LOGBRUSH`構造体は、ペンの色を指定し、`lbStyle`のメンバー、`LOGBRUSH`に構造体を設定する必要があります**BS_SOLID**します。 場合`nPenStyle`は**PS_GEOMETRIC**、すべてのメンバーは、ペンのブラシ属性を指定するために使用する必要があります。  
  
 `nStyleCount`  
 長さをダブルワード単位を指定、`lpStyle`配列。 この値は場合は&0; である必要があります`nPenStyle`は**PS_USERSTYLE**します。  
  
 `lpStyle`  
 ダブルワードの値の配列を指します。 最初の値では、最初のダッシュの長さを指定したユーザー定義のスタイル、2 番目の値は、最初の空白の長さを指定します。 このポインターである必要があります**NULL**場合`nPenStyle`は**PS_USERSTYLE**します。  
  
### <a name="remarks"></a>コメント  
 引数なしのコンス トラクターを使用する場合、その結果を初期化する必要があります`CPen`オブジェクトを`CreatePen`、 `CreatePenIndirect`、または`CreateStockObject`メンバー関数。  
  
 引数を受け取るコンス トラクターを使用する場合は、さらに初期化もする必要はありません。 引数を持つコンス トラクターは、引数なしのコンス トラクターは常に成功しますが、エラーが発生した場合、例外をスローできます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView&#99;](../../mfc/codesnippet/cpp/cpen-class_1.cpp)]  
  
##  <a name="createpen"></a>CPen::CreatePen  
 指定したスタイル、幅、およびブラシ属性と論理表面的または幾何学的ペンを作成し、それにアタッチ、`CPen`オブジェクトです。  
  
```  
BOOL CreatePen(
    int nPenStyle,  
    int nWidth,  
    COLORREF crColor);

 
BOOL CreatePen(
    int nPenStyle,  
    int nWidth,  
    const LOGBRUSH* pLogBrush,  
    int nStyleCount = 0,  
    const DWORD* lpStyle = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `nPenStyle`  
 ペンのスタイルを指定します。 使用可能な値の一覧は、次を参照してください。、`nPenStyle`内のパラメーター、 [CPen](#cpen)コンス トラクターです。  
  
 `nWidth`  
 ペンの幅を指定します。  
  
-   最初のバージョンの`CreatePen`幅をデバイス単位がマッピング モードに関係なく、1 ピクセルでは常にこの値が 0 の場合。  
  
-   2 番目のバージョンの`CreatePen`場合は、`nPenStyle`は**PS_GEOMETRIC**幅を論理単位で指定します。 場合`nPenStyle`は**PS_COSMETIC**幅が 1 に設定する必要があります。  
  
 `crColor`  
 ペンの RGB の色が含まれています。  
  
 `pLogBrush`  
 指す、 [LOGBRUSH](http://msdn.microsoft.com/library/windows/desktop/dd145035)構造体。 場合`nPenStyle`は**PS_COSMETIC**、 **lbColor**のメンバー、`LOGBRUSH`構造体は、ペンの色を指定し、`lbStyle`のメンバー、`LOGBRUSH`に構造体を設定する必要があります**BS_SOLID**します。 場合**nPenStyle**は**PS_GEOMETRIC**、すべてのメンバーは、ペンのブラシ属性を指定するために使用する必要があります。  
  
 `nStyleCount`  
 長さをダブルワード単位を指定、`lpStyle`配列。 この値は場合は&0; である必要があります`nPenStyle`は**PS_USERSTYLE**します。  
  
 `lpStyle`  
 ダブルワードの値の配列を指します。 最初の値では、最初のダッシュの長さを指定したユーザー定義のスタイル、2 番目の値は、最初の空白の長さを指定します。 このポインターである必要があります**NULL**場合`nPenStyle`は**PS_USERSTYLE**します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、0 以外の値またはメソッドが失敗した場合は&0; です。  
  
### <a name="remarks"></a>コメント  
 最初のバージョン`CreatePen`指定したスタイル、幅、および色のペンを初期化します。 任意のデバイス コンテキストには、現在のペンとペンを後で選択できます。  
  
 ペンの幅の 1 ピクセルがあるいずれかのより大きい、**必ず**、**きは**、または**ペン**スタイル。  
  
 ペンがある場合、**ペン**スタイルおよび色の論理テーブルで使用する色に一致しない色ディザー カラーでペンを描画します。 **きは**にディザー カラー ペンを作成するのには、ペンのスタイルを使用できません。 スタイル**ペン**と同じ**きは**ペンの幅が 1 以下である場合。  
  
 2 番目のバージョンの`CreatePen`を指定したスタイル、幅、およびブラシ属性を持つ論理表面的または幾何学的ペンを初期化します。 表面的でペンの幅は、常に 1 です。幾何学模様のペンの幅は常に、ワールド単位で指定します。 アプリケーションには、論理ペンが作成されたら、デバイス コンテキストのペン、選択を呼び出して、 [:selectobject](../../mfc/reference/cdc-class.md#selectobject)関数です。 デバイス コンテキストにペンを選択すると後、は、直線と曲線の描画に使用できます。  
  
-   場合`nPenStyle`は**PS_COSMETIC**と**PS_USERSTYLE**、内のエントリ、`lpStyle`スタイル単位で配列がダッシュと空白の長さを指定します。 スタイルの単位は、直線を描画するペンが使用されるデバイスによって定義されます。  
  
-   場合`nPenStyle`は**PS_GEOMETRIC**と**PS_USERSTYLE**、内のエントリ、`lpStyle`配列が論理ユニットにダッシュと空白の長さを指定します。  
  
-   場合`nPenStyle`は**PS_ALTERNATE**スタイル、単位は無視され、その他のすべてのピクセルを設定します。  
  
 呼び出して、アプリケーションが不要になった特定のペンに必要な場合、 [CGdiObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject)メンバー関数または破棄、`CPen`オブジェクトのリソースが使用できないようにします。 デバイス コンテキストで、ペンを選択すると、アプリケーションは、ペンを削除しないでください。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView&#100;](../../mfc/codesnippet/cpp/cpen-class_2.cpp)]  
  
##  <a name="createpenindirect"></a>CPen::CreatePenIndirect  
 スタイル、幅、および色が指す構造体では、ペンを初期化します`lpLogPen`します。  
  
```  
BOOL CreatePenIndirect(LPLOGPEN lpLogPen);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpLogPen`  
 Windows が指す[LOGPEN](../../mfc/reference/logpen-structure.md)ペンについての情報を格納する構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 ペンの幅の 1 ピクセルがあるいずれかのより大きい、**必ず**、**きは**、または**ペン**スタイル。  
  
 ペンがある場合、**ペン**スタイルおよび色の論理テーブルで使用する色に一致しない色ディザー カラーでペンを描画します。 **ペン**スタイルは**きは**ペンの幅が 1 以下である場合。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&101;](../../mfc/codesnippet/cpp/cpen-class_3.cpp)]  
  
##  <a name="fromhandle"></a>CPen::FromHandle  
 ポインターを返す、 `CPen` Windows GDI pen オブジェクトへのハンドルを指定したオブジェクト。  
  
```  
static CPen* PASCAL FromHandle(HPEN hPen);
```  
  
### <a name="parameters"></a>パラメーター  
 *hPen*  
 `HPEN`Windows GDI ペンへのハンドルします。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CPen`成功以外の場合は、オブジェクト**NULL**します。  
  
### <a name="remarks"></a>コメント  
 `CPen` オブジェクトがハンドルに関連付けられていない場合は、一時的な `CPen` オブジェクトが生成され、関連付けられます。 この一時`CPen`だけですべて一時的なグラフィックを時間があるオブジェクトは削除されるまで、次回、アプリケーションのアイドル時間のイベント ループで、オブジェクトが有効です。 つまり、一時オブジェクトは&1; つのウィンドウ メッセージを処理中に有効なだけなりました。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&105;](../../mfc/codesnippet/cpp/cpen-class_4.cpp)]  
  
##  <a name="getextlogpen"></a>CPen::GetExtLogPen  
 取得、**保持**構造体の基になります。  
  
```  
int GetExtLogPen(EXTLOGPEN* pLogPen);
```  
  
### <a name="parameters"></a>パラメーター  
 `pLogPen`  
 指す、[保持](http://msdn.microsoft.com/library/windows/desktop/dd162711)ペンについての情報を格納する構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 **保持**構造体は、スタイル、幅、およびペンのブラシ属性を定義します。 たとえば、呼び出す`GetExtLogPen`ペンの特定のスタイルに一致します。  
  
 次のトピックを参照してください、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]ペン属性については。  
  
- [Getobject メソッド](http://msdn.microsoft.com/library/windows/desktop/dd144904)  
  
- [保持](http://msdn.microsoft.com/library/windows/desktop/dd162711)  
  
- [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041)  
  
- [構造体](http://msdn.microsoft.com/library/windows/desktop/dd162705)  
  
### <a name="example"></a>例  
 呼び出しを次のコード例に示します`GetExtLogPen`ペンの属性を取得し、同じ色を持つ新しい表面的でペンを作成します。  
  
 [!code-cpp[NVC_MFCDocView #&102;](../../mfc/codesnippet/cpp/cpen-class_5.cpp)]  
  
##  <a name="getlogpen"></a>CPen::GetLogPen  
 取得、`LOGPEN`構造体の基になります。  
  
```  
int GetLogPen(LOGPEN* pLogPen);
```  
  
### <a name="parameters"></a>パラメーター  
 `pLogPen`  
 指す、 [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041)ペンについての情報を格納する構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 `LOGPEN`構造体は、スタイル、色、およびペンのパターンを定義します。  
  
 たとえば、呼び出す`GetLogPen`ペンの特定のスタイルに一致します。  
  
 次のトピックを参照してください、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]ペン属性については。  
  
- [Getobject メソッド](http://msdn.microsoft.com/library/windows/desktop/dd144904)  
  
- [LOGPEN](http://msdn.microsoft.com/library/windows/desktop/dd145041)  
  
### <a name="example"></a>例  
 呼び出しを次のコード例に示します`GetLogPen`ペンの文字を取得し、同じ色を持つ新しいソリッド ペンを作成します。  
  
 [!code-cpp[NVC_MFCDocView #&103;](../../mfc/codesnippet/cpp/cpen-class_6.cpp)]  
  
##  <a name="operator_hpen"></a>CPen::operator HPEN  
 接続されている Windows GDI ハンドルを取得、`CPen`オブジェクトです。  
  
```  
operator HPEN() const;  
```  
  
### <a name="return-value"></a>戻り値  
 かどうかは成功すると、Windows GDI オブジェクトへのハンドルによって表される、`CPen`オブジェクト。 それ以外の場合**NULL**します。  
  
### <a name="remarks"></a>コメント  
 この演算子はキャスト演算子の`HPEN`オブジェクトです。  
  
 グラフィック オブジェクトの使い方の詳細については、記事を参照してください。[グラフィック オブジェクト](http://msdn.microsoft.com/library/windows/desktop/dd144962)で[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCDocView #&104;](../../mfc/codesnippet/cpp/cpen-class_7.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [CGdiObject クラス](../../mfc/reference/cgdiobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CBrush クラス](../../mfc/reference/cbrush-class.md)

