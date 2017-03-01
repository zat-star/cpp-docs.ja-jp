---
title: "CAnimateCtrl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimateCtrl
dev_langs:
- C++
helpviewer_keywords:
- animation controls [C++], CAnimateCtrl class
- Windows common controls [C++], CAnimateCtrl class
- CAnimateCtrl class
ms.assetid: 5e8eb1bd-96b7-47b8-8de2-6bcbb3cc299b
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
ms.openlocfilehash: cef1d6274d5334804ee028fa296c77faf124a496
ms.lasthandoff: 02/24/2017

---
# <a name="canimatectrl-class"></a>CAnimateCtrl クラス
Windows コモン アニメーション コントロールの機能が用意されています。  
  
## <a name="syntax"></a>構文  
  
```  
class CAnimateCtrl : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimateCtrl::CAnimateCtrl](#canimatectrl)|`CAnimateCtrl` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimateCtrl::Close](#close)|AVI クリップを閉じます。|  
|[CAnimateCtrl::Create](#create)|アニメーション コントロールを作成し、それをアタッチ、`CAnimateCtrl`オブジェクトです。|  
|[CAnimateCtrl::CreateEx](#createex)|指定した Windows 拡張スタイルを使用してアニメーション コントロールを作成し、それにアタッチ、`CAnimateCtrl`オブジェクトです。|  
|[CAnimateCtrl::IsPlaying](#isplaying)|Audio-video Interleaved (AVI) クリップを再生するかどうかを示します。|  
|[CAnimateCtrl::Open](#open)|ファイルまたはリソースから AVI クリップを開き、最初のフレームを表示します。|  
|[CAnimateCtrl::Play](#play)|サウンドなし AVI クリップを再生します。|  
|[CAnimateCtrl::Seek](#seek)|AVI クリップの選択した&1; つのフレームを表示します。|  
|[CAnimateCtrl::Stop](#stop)|AVI クリップの再生を停止します。|  
  
## <a name="remarks"></a>コメント  
 このコントロール (つまり、`CAnimateCtrl`クラス) は以降、Windows 95、Windows 98、および Windows NT version 3.51 で実行するプログラムにのみ使用できます。  
  
 アニメーション コントロールは、AVI (Audio Video Interleaved) 形式でクリップを表示する四角形のウィンドウなど、標準の Windows ビデオ/オーディオ形式です。 AVI クリップは、一連の映画と同様、ビットマップ フレームです。  
  
 アニメーション コントロールは、単純な AVI クリップのみを再生できます。 具体的には、アニメーション コントロールで再生するクリップは、次の要件を満たす必要があります。  
  
-   厳密に&1; つのビデオ ストリームが存在する必要があります、少なくとも&1; つのフレームがあります。  
  
-   最大で&2; つのストリームにできますファイル (通常、その他のストリーム存在する場合は、オーディオ ストリーム アニメーション コントロールのオーディオ情報は無視されますが)。  
  
-   クリップは現在必要がありますか、圧縮されていない、または RLE8 圧縮で圧縮されます。  
  
-   ビデオ ストリームでは、パレットの変更は許可されません。  
  
 AVI クリップを追加するには、AVI リソースとしてアプリケーションに、または別の AVI ファイルとしてアプリケーションを伴うことができます。  
  
 スレッドは、AVI クリップが表示されている間の実行を続行、あるためアニメーション コントロールの&1; つの一般的な用途では、時間のかかる操作中にシステムの利用状況を示します。 などのファイル エクスプ ローラーの検索 ダイアログ ボックスでは、ファイルをシステム検索している間、虫眼鏡が表示されます。  
  
 作成する場合、`CAnimateCtrl`ボックスまたはダイアログ エディターを使用して、ダイアログ リソースから自動的に破棄されます ダイアログ ボックスを閉じたときに、ダイアログ ボックスでオブジェクトです。  
  
 作成する場合、`CAnimateCtrl`ウィンドウ内でオブジェクトを破棄する必要があります。 作成する場合、`CAnimateCtrl`スタック上のオブジェクトは自動的に破棄します。 作成する場合、`CAnimateCtrl`を使用して、ヒープ上のオブジェクト、**新しい**関数を呼び出す必要があります**削除**を破棄するオブジェクト。 新しいクラスを派生する場合`CAnimateCtrl`とそのクラスのメモリの割り当て、オーバーライド、`CAnimateCtrl`デストラクターが、割り当てを破棄します。  
  
 使用する方法について`CAnimateCtrl`を参照してください[コントロール](../../mfc/controls-mfc.md)と[を使用して CAnimateCtrl](../../mfc/using-canimatectrl.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CAnimateCtrl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxcmn.h  
  
##  <a name="a-namecanimatectrla--canimatectrlcanimatectrl"></a><a name="canimatectrl"></a>CAnimateCtrl::CAnimateCtrl  
 `CAnimateCtrl` オブジェクトを構築します。  
  
```  
CAnimateCtrl();
```  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります、[作成](#create)メンバー関数を作成するオブジェクトの他の処理を実行する前にします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCControlLadenDialog #&56;](../../mfc/codesnippet/cpp/canimatectrl-class_1.cpp)]  
  
##  <a name="a-nameclosea--canimatectrlclose"></a><a name="close"></a>CAnimateCtrl::Close  
 アニメーション コントロール (存在する場合) で既に開かれている AVI クリップを終了し、メモリから削除します。  
  
```  
BOOL Close();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
### <a name="example"></a>例  
  例を参照してください[CAnimateCtrl::CAnimateCtrl](#canimatectrl)します。  
  
##  <a name="a-namecreatea--canimatectrlcreate"></a><a name="create"></a>CAnimateCtrl::Create  
 アニメーション コントロールを作成し、それをアタッチ、`CAnimateCtrl`オブジェクトです。  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwStyle`  
 アニメーション コントロールのスタイルを指定します。 任意の組み合わせのスタイルの下の「解説」セクションおよびアニメーション コントロールのスタイルでの説明が記載されている windows の[アニメーション コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb761886)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
 `rect`  
 アニメーション コントロールの位置とサイズを指定します。 いずれかになります、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](../../mfc/reference/rect-structure1.md)構造体。  
  
 `pParentWnd`  
 アニメーション コントロールの親ウィンドウを通常指定する`CDialog`です。 ことはできません**NULL です。**  
  
 `nID`  
 アニメーション コントロールの ID を指定します  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
### <a name="remarks"></a>コメント  
 構築する、`CAnimateCtrl`で&2; つの手順を実行します。 最初に、コンス トラクターを呼び出すし、し、呼び出す**作成**、アニメーション コントロールを作成およびそれにアタッチする、`CAnimateCtrl`オブジェクトです。  
  
 次の適用[ウィンドウ スタイル](../../mfc/reference/window-styles.md)アニメーション コントロールにします。  
  
- **WS_CHILD**常に  
  
- **WS_VISIBLE**通常  
  
- **WS_DISABLED**ことはほとんどありません  
  
 アニメーション コントロールで拡張ウィンドウ スタイルを使用する場合は、呼び出す[CreateEx](#createex)の代わりに**作成**します。  
  
 上に示した、ウィンドウ スタイルを&1; つまたは複数のアニメーション コントロールのスタイルをアニメーション コントロールに適用します。 参照してください、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の詳細については[アニメーション コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb761886)します。  
  
### <a name="example"></a>例  
  例を参照してください[CAnimateCtrl::CAnimateCtrl](#canimatectrl)します。  
  
##  <a name="a-namecreateexa--canimatectrlcreateex"></a><a name="createex"></a>CAnimateCtrl::CreateEx  
 コントロール (子ウィンドウ) を作成し、関連付けます、`CAnimateCtrl`オブジェクトです。  
  
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
 アニメーション コントロールのスタイルを指定します。 ウィンドウの任意の組み合わせを適用し、アニメーション コントロールのスタイル」に記載[アニメーション コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb761886)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
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
  
##  <a name="a-nameisplayinga--canimatectrlisplaying"></a><a name="isplaying"></a>CAnimateCtrl::IsPlaying  
 Audio-video Interleaved (AVI) クリップを再生するかどうかを示します。  
  
```  
BOOL IsPlaying() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `true`AVI クリップを再生して; 場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [ACM_ISPLAYING](http://msdn.microsoft.com/library/windows/desktop/bb761895)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="a-nameopena--canimatectrlopen"></a><a name="open"></a>CAnimateCtrl::Open  
 AVI クリップを開き、最初のフレームを表示するには、この関数を呼び出します。  
  
```  
BOOL Open(LPCTSTR lpszFileName);  
BOOL Open(UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `lpszFileName`  
 A`CString`オブジェクトまたは AVI ファイルの名前または AVI リソースの名前を表す null で終わる文字列へのポインター。 このパラメーターは場合**NULL**システムが存在する場合、アニメーションのコントロールは、既に開かれている AVI クリップを閉じます。  
  
 `nID`  
 AVI リソースの識別子です。 このパラメーターは場合**NULL**システムが存在する場合、アニメーションのコントロールは、既に開かれている AVI クリップを閉じます。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
### <a name="remarks"></a>コメント  
 AVI リソースは、アニメーションのコントロールを作成したモジュールから読み込まれます。  
  
 **開く**AVI クリップ; のサウンドをサポートしていませんサイレント AVI クリップのみを開くことができます。  
  
 アニメーション コントロールが、`ACS_AUTOPLAY`スタイル、アニメーション コントロールが自動的に開始して開いた後にすぐにクリップを再生します。 スレッドの実行を続行中は、バック グラウンドでクリップを再生し続けます。 クリップが完了すると、再生中には自動的に繰り返されます。  
  
 アニメーション コントロールが、`ACS_CENTER`スタイル、AVI クリップは、コントロールの中央、およびコントロールのサイズは変わりません。 アニメーション コントロールがない場合、`ACS_CENTER`スタイル、AVI クリップが AVI クリップ内のイメージのサイズに開かれたときに、コントロールがサイズ変更されます。 コントロールの左上隅の位置は変わりません、コントロールのサイズのみです。  
  
 アニメーション コントロールが、 `ACS_TRANSPARENT` 、透明な背景を使用して最初のフレームを描画するのではなくスタイルで指定した背景色、アニメーション クリップします。  
  
### <a name="example"></a>例  
  例を参照してください[CAnimateCtrl::CAnimateCtrl](#canimatectrl)します。  
  
##  <a name="a-nameplaya--canimatectrlplay"></a><a name="play"></a>CAnimateCtrl::Play  
 アニメーション コントロールで AVI クリップを再生するには、この関数を呼び出します。  
  
```  
BOOL Play(
    UINT nFrom,  
    UINT nTo,  
    UINT nRep);
```  
  
### <a name="parameters"></a>パラメーター  
 `nFrom`  
 再生を開始するフレームの&0; から始まるインデックス。 値は、65,536 未満である必要があります。 値 0 AVI クリップの最初のフレームを始めることを意味します。  
  
 `nTo`  
 0 から始まるインデックス、フレームの再生を終了します。 値は、65,536 未満である必要があります。 値 – 1 は、最後のフレームと AVI クリップの終了を意味します。  
  
 *nRep*  
 AVI クリップを再生する回数です。 値 – 1 は、ファイルの再生を無期限にするかを意味します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
### <a name="remarks"></a>コメント  
 アニメーション コントロールが、スレッドは継続の実行中には、バック グラウンドでクリップを再生します。 アニメーション コントロールが`ACS_TRANSPARENT`スタイル、AVI クリップで再生されるアニメーション クリップに指定した背景色ではなく、透明な背景を使用します。  
  
### <a name="example"></a>例  
  例を参照してください[CAnimateCtrl::CAnimateCtrl](#canimatectrl)します。  
  
##  <a name="a-nameseeka--canimatectrlseek"></a><a name="seek"></a>CAnimateCtrl::Seek  
 静的に AVI クリップの&1; つのフレームを表示するには、この関数を呼び出します。  
  
```  
BOOL Seek(UINT nTo);
```  
  
### <a name="parameters"></a>パラメーター  
 `nTo`  
 表示するフレームの&0; から始まるインデックス。 値は、65,536 未満である必要があります。 値が 0 の手段では、AVI クリップの最初のフレームを表示します。 値が-1 の手段では、AVI クリップの最後のフレームを表示します。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
### <a name="remarks"></a>コメント  
 アニメーション コントロールが`ACS_TRANSPARENT`、AVI クリップは透明な背景を使用して描画するのではなくスタイルで指定した背景色、アニメーション クリップします。  
  
### <a name="example"></a>例  
  例を参照してください[CAnimateCtrl::CAnimateCtrl](#canimatectrl)します。  
  
##  <a name="a-namestopa--canimatectrlstop"></a><a name="stop"></a>CAnimateCtrl::Stop  
 アニメーション コントロールでの AVI クリップの再生を停止するには、この関数を呼び出します。  
  
```  
BOOL Stop();
```  
  
### <a name="return-value"></a>戻り値  
 成功した場合は&0; 以外を返します。それ以外の場合は&0; を返します。  
  
### <a name="example"></a>例  
  例を参照してください[CAnimateCtrl::CAnimateCtrl](#canimatectrl)します。  
  
## <a name="see-also"></a>関連項目  
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CAnimateCtrl::Create](#create)   
 [ON_CONTROL](http://msdn.microsoft.com/library/2cb7ebdf-296b-4606-b191-3449835003db)


