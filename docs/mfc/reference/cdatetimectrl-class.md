---
title: "CDateTimeCtrl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDateTimeCtrl
- AFXDTCTL/CDateTimeCtrl
- AFXDTCTL/CDateTimeCtrl::CDateTimeCtrl
- AFXDTCTL/CDateTimeCtrl::CloseMonthCal
- AFXDTCTL/CDateTimeCtrl::Create
- AFXDTCTL/CDateTimeCtrl::GetDateTimePickerInfo
- AFXDTCTL/CDateTimeCtrl::GetIdealSize
- AFXDTCTL/CDateTimeCtrl::GetMonthCalColor
- AFXDTCTL/CDateTimeCtrl::GetMonthCalCtrl
- AFXDTCTL/CDateTimeCtrl::GetMonthCalFont
- AFXDTCTL/CDateTimeCtrl::GetMonthCalStyle
- AFXDTCTL/CDateTimeCtrl::GetRange
- AFXDTCTL/CDateTimeCtrl::GetTime
- AFXDTCTL/CDateTimeCtrl::SetFormat
- AFXDTCTL/CDateTimeCtrl::SetMonthCalColor
- AFXDTCTL/CDateTimeCtrl::SetMonthCalFont
- AFXDTCTL/CDateTimeCtrl::SetMonthCalStyle
- AFXDTCTL/CDateTimeCtrl::SetRange
- AFXDTCTL/CDateTimeCtrl::SetTime
dev_langs:
- C++
helpviewer_keywords:
- DateTimePicker control [MFC], CDateTimeCtrl class
- date-picking functionality
- CDateTimeCtrl class
- DateTimePicker control [MFC]
ms.assetid: 7113993b-5d37-4148-939f-500a190c5bdc
caps.latest.revision: 23
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: e5407934021abdb64dfb625e3dfb2c1841b7a5f0
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cdatetimectrl-class"></a>CDateTimeCtrl クラス
日時指定コントロールの機能がカプセル化されています。  
  
## <a name="syntax"></a>構文  
  
```  
class CDateTimeCtrl : public CWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDateTimeCtrl::CDateTimeCtrl](#cdatetimectrl)|`CDateTimeCtrl` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDateTimeCtrl::CloseMonthCal](#closemonthcal)|現在の日付と時刻のピッカー コントロールを閉じます。|  
|[CDateTimeCtrl::Create](#create)|日付と時刻の選択コントロールを作成し、それにアタッチ、`CDateTimeCtrl`オブジェクトです。|  
|[CDateTimeCtrl::GetDateTimePickerInfo](#getdatetimepickerinfo)|現在の日付と時刻のピッカー コントロールに関する情報を取得します。|  
|[CDateTimeCtrl::GetIdealSize](#getidealsize)|現在の日付または時刻を表示するために必要な日付と時刻のピッカー コントロールの適切なサイズを返します。|  
|[CDateTimeCtrl::GetMonthCalColor](#getmonthcalcolor)|月間予定表の日付と時刻の選択コントロール内の特定部分の色を取得します。|  
|[CDateTimeCtrl::GetMonthCalCtrl](#getmonthcalctrl)|取得、`CMonthCalCtrl`日付と時刻のピッカー コントロールに関連付けられているオブジェクト。|  
|[CDateTimeCtrl::GetMonthCalFont](#getmonthcalfont)|日時指定コントロールの子月間予定表コントロールで現在使用されているフォントを取得します。|  
|[CDateTimeCtrl::GetMonthCalStyle](#getmonthcalstyle)|現在の日付と時刻の選択コントロールのスタイルを取得します。|  
|[CDateTimeCtrl::GetRange](#getrange)|日付と時刻の選択コントロールのシステム時刻を許可される最小値と最大、現在を取得します。|  
|[CDateTimeCtrl::GetTime](#gettime)|日付と時刻の選択コントロールから現在選択されている時刻を取得し、指定した配置`SYSTEMTIME`構造体。|  
|[CDateTimeCtrl::SetFormat](#setformat)|指定された書式文字列に合わせて日付と時刻のピッカー コントロールの表示を設定します。|  
|[CDateTimeCtrl::SetMonthCalColor](#setmonthcalcolor)|月間予定表の日付と時刻の選択コントロール内の特定部分の色を設定します。|  
|[CDateTimeCtrl::SetMonthCalFont](#setmonthcalfont)|日時指定コントロールの子月間予定表コントロールで使用するフォントを設定します。|  
|[CDateTimeCtrl::SetMonthCalStyle](#setmonthcalstyle)|現在の日付と時刻の選択コントロールのスタイルを設定します。|  
|[CDateTimeCtrl::SetRange](#setrange)|日付と時刻の選択コントロールの最小値と最大の許可されたシステム時刻を設定します。|  
|[CDateTimeCtrl::SetTime](#settime)|日付と時刻の選択コントロール、時間を設定します。|  
  
## <a name="remarks"></a>コメント  
 日時指定コントロール (DTP コントロール) では、ユーザーと日付と時刻の情報を交換する単純なインターフェイスを提供します。 このインターフェイスには、コントロールに格納された日付と時刻の情報の一部を表示しているフィールドが含まれています。 ユーザーは、特定のフィールドに文字列の内容を変更することで、コントロールに格納されている情報を変更できます。 ユーザーは、フィールドをマウスまたはキーボードを使用して移動できます。  
  
 作成するときに、オブジェクトにさまざまなスタイルを適用することで、日付と時刻のピッカー コントロールをカスタマイズできます。 参照してください[日付と時刻の選択コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb761728)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]日時指定コントロールのスタイルの詳細についてです。 書式を設定する日時指定コントロールの表示形式を設定することができます。 これらの書式スタイルは、「"書式を設定する"で、[!INCLUDE[winsdkshort](../../atl-mfc-shared/reference/includes/winsdkshort_md.md)]トピック[日付と時刻の選択コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb761728)します。  
  
 日付と時刻の選択コントロールは、通知とに説明されているコールバックにも使用[を使用して CDateTimeCtrl](../../mfc/using-cdatetimectrl.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CDateTimeCtrl`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdtctl.h  
  
##  <a name="cdatetimectrl"></a>CDateTimeCtrl::CDateTimeCtrl  
 `CDateTimeCtrl` オブジェクトを構築します。  
  
```  
CDateTimeCtrl();
```  
  
##  <a name="closemonthcal"></a>CDateTimeCtrl::CloseMonthCal  
 現在の日付と時刻のピッカー コントロールを閉じます。  
  
```  
void CloseMonthCal() const;  
```  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [DTM_CLOSEMONTHCAL](http://msdn.microsoft.com/library/windows/desktop/bb761753)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 次のコード例は、変数を定義`m_dateTimeCtrl`つまり、日時指定コントロールをプログラムでアクセスするために使用します。 この変数は次の例で使用されています。  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>例  
 次のコード例では、現在の日付と時刻のピッカー コントロールのドロップダウンの予定表を閉じます。  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s&#1;5](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_2.cpp)]  
  
##  <a name="create"></a>CDateTimeCtrl::Create  
 日付と時刻の選択コントロールを作成し、それにアタッチ、`CDateTimeCtrl`オブジェクトです。  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwStyle`  
 日付コントロールのスタイルの組み合わせを指定します。 参照してください[日付と時刻の選択コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb761728)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]日付と時刻の選択スタイルの詳細についてです。  
  
 `rect`  
 参照、 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897)構造の日付と時刻の選択コントロールのサイズと位置です。  
  
 `pParentWnd`  
 ポインター、 [CWnd](../../mfc/reference/cwnd-class.md)日時指定コントロールの親ウィンドウであるオブジェクト。 ことはできません**NULL**します。  
  
 `nID`  
 日時指定コントロールのコントロール ID を指定します  
  
### <a name="return-value"></a>戻り値  
 作成が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
  
##### <a name="to-create-a-date-and-time-picker-control"></a>日付と時刻のピッカー コントロールを作成するには  
  
1.  呼び出す[CDateTimeCtrl](#cdatetimectrl)を構築する、`CDateTimeCtrl`オブジェクトです。  
  
2.  このメンバー関数は、Windows の日付と時刻のピッカー コントロールを作成してに接続するを呼び出す、`CDateTimeCtrl`オブジェクトです。  
  
 呼び出すと**作成**、一般的なコントロールが初期化されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CDateTimeCtrl&#1;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_3.cpp)]  
  
##  <a name="getdatetimepickerinfo"></a>CDateTimeCtrl::GetDateTimePickerInfo  
 現在の日付と時刻のピッカー コントロールに関する情報を取得します。  
  
```   
BOOL GetDateTimePickerInfo(LPDATETIMEPICKERINFO pDateTimePickerInfo) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[出力] `pDateTimePickerInfo`|ポインター、 [DATETIMEPICKERINFO](http://msdn.microsoft.com/library/windows/desktop/bb761729)を現在の日付と時刻のピッカー コントロールの説明を受け取る構造体。<br /><br /> 呼び出し元がこの構造体の割り当てを担当します。 ただし、このメソッドは初期化、`cbSize`構造体のメンバーです。|  
  
### <a name="return-value"></a>戻り値  
 `true`このメソッドが成功した場合それ以外の場合、`false`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [DTM_GETDATETIMEPICKERINFO](http://msdn.microsoft.com/library/windows/desktop/bb761755)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 次のコード例は、変数を定義`m_dateTimeCtrl`つまり、日時指定コントロールをプログラムでアクセスするために使用します。 この変数は次の例で使用されています。  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>例  
 次のコード例では、現在の日付と時刻の選択コントロールの概要情報が正常に取得するかどうかを示します。  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s1&4;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_4.cpp)]  
  
##  <a name="getmonthcalcolor"></a>CDateTimeCtrl::GetMonthCalColor  
 月間予定表の日付と時刻の選択コントロール内の特定部分の色を取得します。  
  
```  
COLORREF GetMonthCalColor(int iColor) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `iColor`  
 `int`色領域を取得する月のカレンダーを指定する値。 値の一覧を参照してください、`iColor`パラメーター [SetMonthCalColor](#setmonthcalcolor)します。  
  
### <a name="return-value"></a>戻り値  
 A **COLORREF**正常終了した場合は、月間予定表コントロールの指定した部分の色の設定を表す値。 それ以外の場合、この関数は-1 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[DTM_GETMCCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb761759)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CDateTimeCtrl&#2;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_5.cpp)]  
  
##  <a name="getmonthcalctrl"></a>CDateTimeCtrl::GetMonthCalCtrl  
 取得、`CMonthCalCtrl`日付と時刻のピッカー コントロールに関連付けられているオブジェクト。  
  
```  
CMonthCalCtrl* GetMonthCalCtrl() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md)オブジェクト、または**NULL**それ以外の場合、またはウィンドウが表示されない場合。  
  
### <a name="remarks"></a>コメント  
 日付と時刻のピッカー コントロールは、ユーザーは、ドロップダウン矢印をクリックすると、月間予定表の子コントロールを作成します。 ときに、`CMonthCalCtrl`オブジェクトが不要、破棄すると、アプリケーションに依存しないこと、日時指定コントロールの子の月間予定表イベントを表すオブジェクトを格納するようにします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CDateTimeCtrl&#3;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_6.cpp)]  
  
##  <a name="getmonthcalfont"></a>CDateTimeCtrl::GetMonthCalFont  
 日時指定コントロールの月間予定表コントロールで現在使用されているフォントを取得します。  
  
```  
CFont* GetMonthCalFont() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、 [CFont](../../mfc/reference/cfont-class.md)オブジェクト、または**NULL**失敗した場合。  
  
### <a name="remarks"></a>コメント  
 `CFont`戻り値によって指されるオブジェクトが一時オブジェクトし、次のアイドル状態の処理時に破棄します。  
  
##  <a name="getmonthcalstyle"></a>CDateTimeCtrl::GetMonthCalStyle  
 現在の日付と時刻のピッカー コントロールに関連付けられているドロップダウン月間予定表コントロールのスタイルを取得します。  
  
```  
DWORD GetMonthCalStyle() const;  
```  
  
### <a name="return-value"></a>戻り値  
 日付と時刻の選択コントロールのスタイルのビットごとの組み合わせであるドロップ ダウン月間予定表コントロールの (または) のスタイル。 詳細については、次を参照してください。[月間予定表コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760919)します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [DTM_GETMCSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb761763)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
##  <a name="getrange"></a>CDateTimeCtrl::GetRange  
 日付と時刻の選択コントロールのシステム時刻を許可される最小値と最大、現在を取得します。  
  
```  
DWORD GetRange(
    COleDateTime* pMinRange,  
    COleDateTime* pMaxRange) const;  
  
DWORD GetRange(
    CTime* pMinRange,  
    CTime* pMaxRange) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 `pMinRange`  
 ポインター、[時刻](../../atl-mfc-shared/reference/coledatetime-class.md)オブジェクトまたは[CTime](../../atl-mfc-shared/reference/ctime-class.md)オブジェクトで許可される最も早い時刻を含む、`CDateTimeCtrl`オブジェクトです。  
  
 `pMaxRange`  
 ポインター、`COleDateTime`オブジェクトまたは`CTime`オブジェクトで許可される最新の時刻を含む、`CDateTimeCtrl`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 A`DWORD`設定されている範囲を示すフラグを表す値。 If  
  
 `return value & GDTR_MAX` == 0  
  
 2 番目のパラメーターは有効です。 同様に場合、  
  
 `return value & GDTR_MIN` == 0  
  
 最初のパラメーターは有効です。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[DTM_GETRANGE](http://msdn.microsoft.com/library/windows/desktop/bb761767)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 MFC の実装では、いずれかを指定できます`COleDateTime`または`CTime`使用法です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CDateTimeCtrl&4;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_7.cpp)]  
  
##  <a name="gettime"></a>CDateTimeCtrl::GetTime  
 日付と時刻の選択コントロールから現在選択されている時刻を取得し、指定した配置`SYSTEMTIME`構造体。  
  
```  
BOOL GetTime(COleDateTime& timeDest) const;  
DWORD GetTime(CTime& timeDest) const;  
DWORD GetTime(LPSYSTEMTIME pTimeDest) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 *timeDest*  
 最初の形式への参照では、[時刻](../../atl-mfc-shared/reference/coledatetime-class.md)システム時刻の情報を受け取るオブジェクト。 2 番目のバージョンへの参照で、 [CTime](../../atl-mfc-shared/reference/ctime-class.md)システム時刻の情報を受け取るオブジェクト。  
  
 *pTimeDest*  
 ポインター、 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)システム時刻の情報を受け取る構造体。 ことはできません**NULL**します。  
  
### <a name="return-value"></a>戻り値  
 時間は書き込みが完了した場合は 0 以外の最初のバージョンで、`COleDateTime`オブジェクト。 それ以外の場合、0 です。 2 番目と&3; 番目のバージョンで、`DWORD`に等しい値が、 **dwFlag**セットのメンバー、[戻り](http://msdn.microsoft.com/library/windows/desktop/bb761730)構造体。 参照してください、**解説**詳細については後述します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[DTM_GETSYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/bb761769)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 MFC 実装で**GetTime**、使用する`COleDateTime`または`CTime`を使用するか、クラス、`SYSTEMTIME`時の情報を格納するための構造です。  
  
 戻り値`DWORD`2 番目と&3; 番目のバージョンを示します「日付なし」状態に日付と時刻のピッカー コントロールを設定するかどうかで指定されている、[戻り](http://msdn.microsoft.com/library/windows/desktop/bb761730)構造体のメンバー`dwFlags`します。 値する場合**GDT_NONE**、コントロールは、「日付なし」状態に設定されているしを使用して、 **DTS_SHOWNONE**スタイル。 値する場合**戻り**、システム時刻は、先に正常に保存します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CDateTimeCtrl&#5;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_8.cpp)]  
  
##  <a name="getidealsize"></a>CDateTimeCtrl::GetIdealSize  
 現在の日付または時刻を表示するために必要な日付と時刻のピッカー コントロールの適切なサイズを返します。  
  
```  
BOOL GetIdealSize(LPSIZE psize) const;  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[出力] `psize`|ポインター、[サイズ](http://msdn.microsoft.com/library/windows/desktop/dd145106)コントロールの適切なサイズを格納する構造体。|  
  
### <a name="return-value"></a>戻り値  
 戻り値は常に`true`します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [DTM_GETIDEALSIZE](http://msdn.microsoft.com/library/windows/desktop/bb761757)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 次のコード例は、変数を定義`m_dateTimeCtrl`つまり、日時指定コントロールをプログラムでアクセスするために使用します。 この変数は次の例で使用されています。  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>例  
 次のコード例では、日付と時刻のピッカー コントロールを表示する最適なサイズを取得します。  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s&#1;2](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_9.cpp)]  
  
##  <a name="setformat"></a>CDateTimeCtrl::SetFormat  
 指定された書式文字列に合わせて日付と時刻のピッカー コントロールの表示を設定します。  
  
```  
BOOL SetFormat(LPCTSTR pstrFormat);
```  
  
### <a name="parameters"></a>パラメーター  
 *pstrFormat*  
 希望の表示を定義する形式のゼロで終わる文字列へのポインター。 このパラメーターに設定**NULL**コントロールを現在のスタイルの既定の書式指定文字列にリセットされます。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
> [!NOTE]
>  ユーザー入力は、この呼び出しの成功または失敗を特定できません。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[DTM_SETFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb761771)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CDateTimeCtrl&6;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_10.cpp)]  
  
##  <a name="setmonthcalcolor"></a>CDateTimeCtrl::SetMonthCalColor  
 月間予定表の日付と時刻の選択コントロール内の特定部分の色を設定します。  
  
```  
COLORREF SetMonthCalColor(
    int iColor,  
    COLORREF ref);
```  
  
### <a name="parameters"></a>パラメーター  
 `iColor`  
 `int`月間予定表コントロールの設定の領域を指定する値。 この値は、次のいずれかを指定できます。  
  
|値|説明|  
|-----------|-------------|  
|MCSC_BACKGROUND|数か月間に表示される背景色を設定します。|  
|MCSC_MONTHBK|1 か月内に表示される背景色を設定します。|  
|MCSC_TEXT|1 か月のテキストの表示に使用する色を設定します。|  
|MCSC_TITLEBK|予定表のタイトルに表示される背景色を設定します。|  
|MCSC_TITLETEXT|予定表のタイトルのテキストに使用する色を設定します。|  
|MCSC_TRAILINGTEXT|ヘッダーと末尾の日付のテキスト表示に使用する色を設定します。 ヘッダーと後続の日はの現在の暦に表示される前と次の月から日です。|  
  
 `ref`  
 A **COLORREF**月間予定表の指定された領域を設定する色を表す値。  
  
### <a name="return-value"></a>戻り値  
 A **COLORREF**正常終了した場合は、月間予定表コントロールの指定した部分の前のカラー設定を表す値。 それ以外の場合、メッセージは、-1 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[DTM_SETMCCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb761773)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
  例を参照してください[CDateTimeCtrl::GetMonthCalColor](#getmonthcalcolor)します。  
  
##  <a name="setmonthcalfont"></a>CDateTimeCtrl::SetMonthCalFont  
 日時指定コントロールの子月間予定表コントロールで使用するフォントを設定します。  
  
```  
void SetMonthCalFont(
    HFONT hFont,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `hFont`  
 設定されるフォントへのハンドルします。  
  
 `bRedraw`  
 かどうか、コントロール再描画するかすぐにフォントの設定を指定します。 このパラメーターに設定**TRUE**コントロールを自動的に再描画します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[DTM_SETMCFONT](http://msdn.microsoft.com/library/windows/desktop/bb761775)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CDateTimeCtrl&#7;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_11.cpp)]  
  
> [!NOTE]
>  このコードを使用する場合のメンバにする、 `CDialog`-という名前のクラスを派生`m_MonthFont`型の**CFont**します。  
  
##  <a name="setmonthcalstyle"></a>CDateTimeCtrl::SetMonthCalStyle  
 現在の日付と時刻のピッカー コントロールに関連付けられているドロップダウン月間予定表コントロールのスタイルを設定します。  
  
```  
DWORD SetMonthCalStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `dwStyle`|新しい&1; か月カレンダーの月間予定表コントロールのスタイルのビットごとの組み合わせ (OR) は、コントロールのスタイル。 詳細については、次を参照してください。[月間予定表コントロールのスタイル](http://msdn.microsoft.com/library/windows/desktop/bb760919)します。|  
  
### <a name="return-value"></a>戻り値  
 ドロップダウンの月間予定表コントロールの以前のスタイル。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、送信、 [DTM_SETMCSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb761778)で説明されているメッセージ、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="example"></a>例  
 次のコード例は、変数を定義`m_dateTimeCtrl`つまり、日時指定コントロールをプログラムでアクセスするために使用します。 この変数は次の例で使用されています。  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s&#1;1](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_1.h)]  
  
### <a name="example"></a>例  
 次のコード例では、週番号、日、曜日、および現在のインジケーターはありませんの省略名を表示する日付と時刻のピッカー コントロールを設定します。  
  
 [!code-cpp[NVC_MFC_CDateTimeCtrl_s&#1;3](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_12.cpp)]  
  
##  <a name="setrange"></a>CDateTimeCtrl::SetRange  
 日付と時刻の選択コントロールの最小値と最大の許可されたシステム時刻を設定します。  
  
```  
BOOL SetRange(
    const COleDateTime* pMinRange,  
    const COleDateTime* pMaxRange);

 
BOOL SetRange(
    const CTime* pMinRange,  
    const CTime* pMaxRange);
```  
  
### <a name="parameters"></a>パラメーター  
 `pMinRange`  
 ポインター、[時刻](../../atl-mfc-shared/reference/coledatetime-class.md)オブジェクトまたは[CTime](../../atl-mfc-shared/reference/ctime-class.md)オブジェクトで許可される最も早い時刻を含む、`CDateTimeCtrl`オブジェクトです。  
  
 `pMaxRange`  
 ポインター、`COleDateTime`オブジェクトまたは`CTime`オブジェクトで許可される最新の時刻を含む、`CDateTimeCtrl`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[DTM_SETRANGE](http://msdn.microsoft.com/library/windows/desktop/bb761780)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 MFC の実装では、いずれかを指定できます`COleDateTime`または`CTime`使用法です。 場合、`COleDateTime`オブジェクトには、 **NULL**状態、範囲が削除されます。 場合、`CTime`ポインター、または`COleDateTime`ポインターが**NULL**範囲が削除されます。  
  
### <a name="example"></a>例  
  例を参照してください[CDateTimeCtrl::GetRange](#getrange)します。  
  
##  <a name="settime"></a>CDateTimeCtrl::SetTime  
 日付と時刻の選択コントロール、時間を設定します。  
  
```  
BOOL SetTime(const COleDateTime& timeNew);  
BOOL SetTime(const CTime* pTimeNew);  
BOOL SetTime(LPSYSTEMTIME pTimeNew = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *timeNew*  
 参照、[時刻](../../atl-mfc-shared/reference/coledatetime-class.md)オブジェクトを含む、コントロールを設定します。  
  
 *pTimeNew*  
 2 番目のバージョンへのポインターの上で、 [CTime](../../atl-mfc-shared/reference/ctime-class.md)コントロールを設定する時刻を表すオブジェクト。 3 番目のバージョンへのポインターの上で、 [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950)コントロールを設定する時刻を含む構造体。  
  
### <a name="return-value"></a>戻り値  
 正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このメンバー関数は、Win32 メッセージの動作を実装して[DTM_SETSYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/bb761782)」を参照して、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。 MFC 実装で**SetTime**、使用することができます、`COleDateTime`または`CTime`を使用するか、クラス、`SYSTEMTIME`構造、時間の情報を設定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_CDateTimeCtrl&#8;](../../mfc/reference/codesnippet/cpp/cdatetimectrl-class_13.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル CMNCTRL1](../../visual-cpp-samples.md)   
 [CWnd クラス](../../mfc/reference/cwnd-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CMonthCalCtrl クラス](../../mfc/reference/cmonthcalctrl-class.md)

