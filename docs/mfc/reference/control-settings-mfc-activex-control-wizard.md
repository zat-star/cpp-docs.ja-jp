---
title: "[コントロールの設定] (MFC ActiveX コントロール ウィザード) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfc.ctl.settings"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC ActiveX コントロール ウィザード、コントロールの設定"
ms.assetid: 2ccaa4fc-0d52-413e-afa3-ecd474c3f6f0
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# [コントロールの設定] (MFC ActiveX コントロール ウィザード)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ウィザードのこのページを使用して、コントロールの動作を指定します。  たとえば、標準の Windows コントロールのタイプに基づいてコントロールを作成したり、コントロールの動作や外観を最適化したりできます。また、コントロールが他のコントロールのコンテナーとして機能するように指定することもできます。  
  
 コントロールの効果を最大限にするためのこのページのオプション選択の詳細については、「[MFC ActiveX コントロール : 最適化](../../mfc/mfc-activex-controls-optimization.md)」を参照してください。  
  
## UIElement の一覧  
 **\[次に基づいてコントロールを作成\]**  
 この一覧から、コントロールが継承するコントロールの種類を選択できます。  この一覧は、`CreateWindowEx` で使用可能なコントロール クラスのサブセットと、commctrl.h で指定された追加のコモン コントロールです。  選択肢は *ProjName*Ctrl.cpp ファイルの `PreCreateWindow` 関数のコントロールのスタイルを指定します。  詳細については、「[MFC ActiveX コントロール : Windows コントロールのサブクラス化](../../mfc/mfc-activex-controls-subclassing-a-windows-control.md)」を参照してください。  
  
|Control|説明|  
|-------------|--------|  
|**BUTTON**|Windows のボタン コントロール。|  
|**COMBOBOX**|Windows のコンボ ボックス コントロール。|  
|**EDIT**|Windows のエディット ボックス コントロール。|  
|**LISTBOX**|Windows のリスト ボックス コントロール。|  
|**SCROLLBAR**|Windows のスクロール バー コントロール。|  
|**STATIC**|Windows のスタティック コントロール。|  
|**msctls\_hotkey32**|ホット キー コモン コントロール。|  
|**msctls\_progress32**|プログレス バー コモン コントロール。|  
|**msctls\_statusbar32**|ステータス バー コモン コントロール。|  
|**msctls\_trackbar32**|トラック バー コモン コントロール。|  
|**msctls\_updown32**|スピン ボタン \(または アップダウン\) コモン コントロール|  
|**SysAnimate32**|アニメーション コモン コントロール。|  
|**SysHeader32**|ヘッダー コモン コントロール。|  
|**SysListView32**|リスト ビュー コモン コントロール。|  
|**SysTabControl32**|タブ コモン コントロール。|  
|**SysTreeView32**|ツリー ビュー コモン コントロール。|  
  
 **\[表示時にアクティブ\]**  
 コントロールにアクセスされたときに、そのコントロールのウィンドウを作成するように指定します。  既定では、**\[表示時にアクティブ\]** はオンになっています。  コンテナーでコントロールが \(マウス クリックなどによって\) 必要になるまでコントロールをアクティブにしない場合は、このオプションをオフにします。  この機能をオフにすると、必要になるまでウィンドウを作成しないため、コントロールによる負荷が削減されます。  詳細については、「[\[表示時にアクティブ\] オプションのオフ](../Topic/Turning%20off%20the%20Activate%20When%20Visible%20Option.md)」を参照してください。  
  
 **\[ランタイムで非表示\]**  
 実行時にコントロールのユーザー インターフェイスを表示しないことを指定します。  表示が不要なコントロールとしては、たとえばタイマー コントロールなどがあります。  
  
 **\[\[バージョン情報\] ボックス ダイアログあり\]**  
 コントロールで標準の Windows の **\[バージョン情報\]** ダイアログ ボックスを使用して、バージョン番号と著作権情報を表示するように指定します。  
  
> [!NOTE]
>  ユーザーがコントロールのヘルプにアクセスする方法は、ヘルプの実装方法、およびコンテナーのヘルプがコントロールのヘルプに統合されているかどうかによって異なります。  ヘルプを表示するには、Web サイトに統合する方法に関する詳細について [MSDN ライブラリ](http://go.microsoft.com/fwlink/?linkID=150542) 「MFC ActiveX コントロールに状況依存のヘルプの追加」を参照してください。  
  
 このオプションを選択すると、プロジェクトのコントロール クラス \(C*ProjName*Ctrl.cpp\) で `AboutBox` コントロール メソッドが追加され、プロジェクトのディスパッチ マップにバージョン情報を追加します。  既定では、このチェック ボックスはオンになっています。  
  
 **\[最適化された描画コード\]**  
 同じデバイス コンテキストに描画されるコンテナーのコントロールの描画がすべて完了した後で、コンテナーの GDI オブジェクトを自動的に元の状態に復元するように指定します。  この機能の詳細については、「[コントロールの描画の最適化](../../mfc/optimizing-control-drawing.md)」を参照してください。  
  
 **\[ウィンドウなしでアクティブ\]**  
 コントロールがアクティブになったときにコントロールのウィンドウを作成しないように指定します。  この機能をオンにすると、四角形以外のコントロールや透過的なコントロールを使用できます。また、ウィンドウなしのコントロールには、ウィンドウ付きのコントロールに比べて必要なシステム オーバーヘッドが削減されます。  ウィンドウなしのコントロールでは、クリッピングを行わないデバイス コンテキストやちらつきなしのアクティベーションは使用できません。  1996 年以前に作成されたコンテナーでは、ウィンドウなしのアクティベーションをサポートしません。  このオプションの使用方法の詳細については、「[ウィンドウなしのアクティベーション](../../mfc/providing-windowless-activation.md)」を参照してください。  
  
 **\[クリッピングを行わないデバイス コンテキスト\]**  
 `IntersectClipRect` の呼び出しを `COleControl`で無効にするコントロールのヘッダー \(*projname*ctrl.h\) オーバーライドは [COleControl::GetControlFlags](../Topic/COleControl::GetControlFlags.md) しました。  このオプションをオンにすると、処理速度が多少向上します。  **\[ウィンドウなしでアクティブ\]** をオンにした場合は、この機能を使用できません。  詳細については、「[クリッピングを行わないデバイス コンテキストの使用](../../mfc/using-an-unclipped-device-context.md)」を参照してください。  
  
 **\[ちらつきなしでアクティブ化\]**  
 コントロールの状態がアクティブと非アクティブの間で移行するときに発生する描画処理とそれに伴うちらつきをなくします。  **\[ウィンドウなしでアクティブ\]** をオンにした場合は、この機能を使用できません。  このオプションをオンにすると、[COleControl::GetControlFlags](../Topic/COleControl::GetControlFlags.md) によって返されるフラグに `noFlickerActivate` フラグが含まれます。  詳細については、「[ちらつきなしのアクティベーションの提供](../../mfc/providing-flicker-free-activation.md)」を参照してください。  
  
 **\[\[オブジェクトの挿入\] で使用\]**  
 有効なコンテナーに対してコントロールを **\[オブジェクトの挿入\]** ダイアログ ボックスで使用できることを指定します。  このオプションをオンにすると、`AfxOleRegisterControlClass` によって返されるフラグに `afxRegInsertable` フラグが含まれます。  **\[オブジェクトの挿入\]** ダイアログ ボックスを使用すると、ユーザーは新規または既存のオブジェクトを複合ドキュメントに追加できます。  
  
 **\[非アクティブ時のマウス ポインター通知\]**  
 コントロールがアクティブかどうかにかかわらず、コントロールでマウス ポインターの通知を処理できるように指定します。  このオプションをオンにすると、[COleControl::GetControlFlags](../Topic/COleControl::GetControlFlags.md) によって返されるフラグに `pointerInactive` フラグが含まれます。  このオプションの使用方法の詳細については、「[コントロールがアクティブでないときのマウスとの対話](../Topic/Providing%20Mouse%20Interaction%20While%20Inactive.md)」を参照してください。  
  
 **\[シンプル フレーム コントロールとして動作\]**  
 コントロールの `OLEMISC_SIMPLEFRAME` ビットを設定することにより、そのコントロールが他のコントロールのコンテナーであることを指定します。  詳細について、[MSDN ライブラリ](http://go.microsoft.com/fwlink/?linkID=150542) サイトの「単純なフレーム サイト コンテインメント」を検索してください。  
  
 **\[非同期でプロパティを読み込む\]**  
 以前の非同期データのリセットを有効にし、コントロールの非同期プロパティの新規読み込みを実行します。  
  
## 参照  
 [MFC ActiveX コントロール ウィザード](../../mfc/reference/mfc-activex-control-wizard.md)   
 [\[アプリケーションの設定\] \(MFC ActiveX コントロール ウィザード\)](../Topic/Application%20Settings,%20MFC%20ActiveX%20Control%20Wizard.md)   
 [\[コントロール名\] \(MFC ActiveX コントロール ウィザード\)](../Topic/Control%20Names,%20MFC%20ActiveX%20Control%20Wizard.md)