---
title: "MFC ActiveX コントロール ウィザード、設定を制御 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.mfc.ctl.settings
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX Control Wizard, control settings
ms.assetid: 2ccaa4fc-0d52-413e-afa3-ecd474c3f6f0
caps.latest.revision: 16
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 35ec579e6f777a3dffd87adc5a86af2ea38b30f4
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="control-settings-mfc-activex-control-wizard"></a>[コントロールの設定] (MFC ActiveX コントロール ウィザード)
ウィザードのこのページを使用して、コントロールの動作をする方法を指定します。 たとえば、標準的な Windows のコントロールの種類の制御の基盤の動作や外観を最適化、またはコントロールも、他のコントロールのコンテナーとして機能するかを示すできます。  
  
 コントロールの効率を最大限にこのページのオプションを選択する方法の詳細については、次を参照してください。 [MFC ActiveX コントロール: 最適化](../../mfc/mfc-activex-controls-optimization.md)します。  
  
## <a name="uielement-list"></a>UIElement の一覧  
 **基づくコントロールを作成します。**  
 この一覧には、コントロールが継承するコントロールの種類を選択できます。 一覧で利用可能なコントロール クラスのサブセットである`CreateWindowEx`と commctrl.h で指定されているコモン コントロールを追加します。 選択した項目のコントロールのスタイルを決定する、`PreCreateWindow`で機能、 *ProjName*Ctrl.cpp ファイルです。 詳細については、次を参照してください。 [MFC ActiveX コントロール: Windows コントロールをサブクラス化](../../mfc/mfc-activex-controls-subclassing-a-windows-control.md)します。  
  
|コントロール|説明|  
|-------------|-----------------|  
|**ボタン**|Windows のボタン コントロール|  
|**コンボ ボックス**|Windows コンボ ボックス コントロール|  
|**編集します。**|Windows のエディット ボックス コントロール|  
|**リスト ボックス**|Windows のリスト ボックス コントロール|  
|**スクロール バー**|Windows のスクロール バー コントロール|  
|**静的**|Windows のスタティック コントロール|  
|**msctls_hotkey32**|ホット キーの共通コントロール|  
|**msctls_progress32**|プログレス バー コモン コントロール|  
|**msctls_statusbar32**|ステータス バー コモン コントロール|  
|**msctls_trackbar32**|トラック バー コモン コントロール|  
|**msctls_updown32**|スピン ボタン (または上下) コモン コントロール|  
|**SysAnimate32**|アニメーションのコモン コントロール|  
|**SysHeader32**|ヘッダーのコモン コントロール|  
|**SysListView32**|リスト ビュー コモン コントロール|  
|**SysTabControl32**|タブのコモン コントロール|  
|**SysTreeView32**|ツリー ビューのコモン コントロール|  
  
 **表示時にアクティブします。**  
 アクセスする場合、コントロールのウィンドウを作成することを指定します。 既定では、**表示時にアクティブ**オプションを選択します。 コンテナーが (たとえば、ユーザーがマウスをクリックする) 必要になるまでは、コントロールのアクティブ化を遅延させる場合は、このオプションをオフにします。 この機能がオフの場合は、コントロールが必要になるまでウィンドウの作成の費用を発生してしません。 詳細については、次を参照してください。 [、アクティブ化するときに [表示] オプションをオフにする](../../mfc/turning-off-the-activate-when-visible-option.md)です。  
  
 **実行時に非表示**  
 コントロールは、実行時にユーザー インターフェイスがないことを指定します。 タイマーは、非表示にすることがありますコントロールの種類です。  
  
 **About ボックス ダイアログします。**  
 コントロールに標準の Windows があることを示す**に関する** ダイアログ ボックスは、バージョン番号と著作権情報が表示されます。  
  
> [!NOTE]
>  ユーザーがコントロールのヘルプにアクセスする方法は、ヘルプを実装する方法と、コントロールのヘルプをコンテナーのヘルプが統合されているかどうかによって異なります。 ヘルプを統合する方法について、 [MSDN ライブラリ](http://go.microsoft.com/fwlink/linkid=150542)web サイト、「を追加する状況依存のヘルプを MFC ActiveX コントロール」を検索します。  
  
 挿入は、このオプションを選択すると、`AboutBox`プロジェクト コントロール クラスのメソッドを制御 (C*ProjName*Ctrl.cpp) し、プロジェクトのディスパッチ マップにオンを追加します。 既定では、このチェック ボックスはオンになっています。  
  
 **最適化されたコードの描画**  
 あるコンテナー GDI の元のオブジェクトを自動的に復元結局のところが描画された同じデバイス コンテキストへの描画は、コンテナー コントロールを指定します。 この機能の詳細については、次を参照してください。[コントロールの描画を最適化する](../../mfc/optimizing-control-drawing.md)です。  
  
 **ウィンドウなしのアクティベーション**  
 アクティブな場合のコントロールはウィンドウを作成しないことを指定します。 ウィンドウなしのアクティベーションで、四角形以外または透明なコントロールし、ウィンドウなしのコントロールでは、ウィンドウを持つコントロールよりも少ないシステムのオーバーヘッドが必要ですが必要です。 ウィンドウなしのコントロールは、クリッピングを行わないデバイス コンテキストまたはちらつきなしのアクティベーションはできません。 1996 年以前に作成されたコンテナーは、ウィンドウなしのアクティベーションをサポートしていません。 このオプションを使用する方法の詳細については、次を参照してください。[ウィンドウなしのアクティベーション](../../mfc/providing-windowless-activation.md)します。  
  
 **クリッピングを行わないデバイス コンテキスト**  
 オーバーライド[オン](../../mfc/reference/colecontrol-class.md#getcontrolflags)コントロールのヘッダー (*projname*ctrl.h) への呼び出しを無効にする`IntersectClipRect`による`COleControl`します。 このオプションを選択すると、小さなスピードに関する利点を提供します。 選択した場合**ウィンドウなしのアクティベーション**、この機能は使用できません。 詳細については、次を参照してください。[クリッピングを行わないデバイス コンテキストの使用](../../mfc/using-an-unclipped-device-context.md)します。  
  
 **ちらつきなしのアクティベーション**  
 描画の処理とコントロールのアクティブおよび非アクティブ状態の間に発生するちらつきがなくなります。 選択した場合**ウィンドウなしのアクティベーション**、この機能は使用できません。 このオプションを設定すると、`noFlickerActivate`フラグは、いずれかのフラグによって返される[オン](../../mfc/reference/colecontrol-class.md#getcontrolflags)します。 詳細については、次を参照してください。[ちらつきなしのアクティベーション](../../mfc/providing-flicker-free-activation.md)します。  
  
 **[オブジェクトの挿入] ダイアログ ボックス**  
 コントロールがで使用できることを示す、**オブジェクトの挿入**有効なコンテナーのダイアログ ボックス。 このオプションを選択すると、`afxRegInsertable`フラグは、いずれかのフラグによって返される`AfxOleRegisterControlClass`です。 使用して、**オブジェクトの挿入**ダイアログ ボックスで、ユーザーは、新しく作成されたが挿入または既存の複合ドキュメントにオブジェクトです。  
  
 **アクティブでないときのマウス ポインターの通知を行う**  
 コントロールがアクティブかどうかは、マウス ポインターの通知を処理する、コントロールを有効にします。 このオプションを選択すると、`pointerInactive`フラグは、いずれかのフラグによって返される[オン](../../mfc/reference/colecontrol-class.md#getcontrolflags)します。 このオプションを使用する方法の詳細については、次を参照してください。[を提供するマウス操作中にアクティブでない](../../mfc/providing-mouse-interaction-while-inactive.md)します。  
  
 **シンプルなフレーム コントロールとして動作**  
 指定するコントロールの他のコントロールのコンテナーを設定して、`OLEMISC_SIMPLEFRAME`コントロールのビットです。 詳細については、上、 [MSDN ライブラリ](http://go.microsoft.com/fwlink/linkid=150542)web サイト、「簡単なフレーム サイト コンテインメント」を検索します。  
  
 **プロパティを非同期的に読み込みます**  
 以前の非同期データのリセットを有効し、コントロールの非同期のプロパティの新しい読み込みを開始します。  
  
## <a name="see-also"></a>関連項目  
 [MFC ActiveX コントロール ウィザード](../../mfc/reference/mfc-activex-control-wizard.md)   
 [アプリケーションの設定、MFC ActiveX コントロール ウィザード](../../mfc/reference/application-settings-mfc-activex-control-wizard.md)   
 [コントロール名、MFC ActiveX コントロール ウィザード](../../mfc/reference/control-names-mfc-activex-control-wizard.md)


