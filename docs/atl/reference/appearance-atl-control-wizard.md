---
title: "表示形式、ATL コントロール ウィザード |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.control.misc
dev_langs:
- C++
helpviewer_keywords:
- ATL Control Wizard, appearance
ms.assetid: cc16d7ff-74d7-4c15-9ebd-4b19201ff457
caps.latest.revision: 12
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
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: dde27a7b62f3ee3b5fe8fcacd8141e9f89ed3c98
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="appearance-atl-control-wizard"></a>外観、ATL コントロール ウィザード
「検索結果」の概要をここに挿入します。  
  
 コントロールの追加のユーザーの要素のオプションを識別するために、ウィザードのこのページを使用します。 として識別されるコントロールのこのページは**標準コントロール****コントロール型**上、[オプション]、[ATL コントロール ウィザード](../../atl/reference/options-atl-control-wizard.md)ページです。  
  
## <a name="uielement-list"></a>UIElement の一覧  
 **状態の表示**  
 コンテナー内のコントロールの外観を設定します。  
  
-   **不透明な**: セット、`VIEWSTATUS_OPAQUE`内のビット、[な VIEWSTATUS](http://msdn.microsoft.com/library/windows/desktop/ms687201)列挙と、コントロール全体渡された四角形を描画、 [CComControlBase::OnDraw](../../atl/reference/ccomcontrolbase-class.md#ondraw)メソッドです。 コントロールが完全に不透明ですが表示され、コントロールの境界の背後にあるコンテナーの [なし] を示しています。  
  
     この設定は、コントロールの描画をより迅速にコンテナーをことができます。 このオプションが選択されていない場合、コントロールは、透明な部分を含めることができます。  
  
     不透明なコントロールだけ単色の背景ことができます。  
  
-   セット、`VIEWSTATUS_SOLIDBKGND`内のビット、`VIEWSTATUS`列挙します。 コントロールの背景は、パターンのない純色として表示されます。  
  
     このオプションは利用可能な場合にのみ、**不透明**オプションも選択します。  
  
 **コントロールを追加します。**  
 コントロールを追加することによって Windows のコントロール型に基づく設定、 [CContainedWindow](ccontainedwindowt-class.md)コントロールを実装するクラスにデータ メンバーです。 また、メッセージ マップとコントロール用の Windows メッセージを処理するメッセージ ハンドラー関数を追加します。 存在する場合は、作成する Windows コントロールの種類を一覧から選択します。  

  
-   `Button`  
  
-   `ListBox`  
  
-   `SysAnimate32`  
  
-   `SysListView32`  
  
-   `ComboBox`  
  
-   `RichEdit`  
  
-   `SysDateTimePick32`  
  
-   `SysMonthCal32`  
  
-   `ComboBoxEx32`  
  
-   `ScrollBar`  
  
-   `SysHeader32`  
  
-   `SysTabControl32`  
  
-   `Edit`  
  
-   `Static`  
  
-   `SysIPAddress32`  
  
-   `SysTreeView32`  
  
 **その他の状態**  
 コントロールの外観と動作の追加オプションを設定します。  
  
-   **実行時に非表示**: 非表示に実行時にコントロールを設定します。 非表示のコントロールを使用して、指定された間隔でイベントを発生させるなど、バック グラウンドで操作を実行することができます。  
  
-   **ボタンのように動作**: セット、`OLEMISC_ACTSLIKEBUTTON`内のビット、[入ります](http://msdn.microsoft.com/library/windows/desktop/ms678497)ボタンなどのコントロールに動作を有効にするための列挙体です。 コンテナーには、既定のボタンとコントロールのクライアント サイトがマークされた、このオプションを選択すると、button コントロール自体を太くフレームを描画することによって既定のボタンとして表示を有効になります。 参照してください[CComControlBase::GetAmbientDisplayAsDefault](../../atl/reference/ccomcontrolbase-class.md#getambientdisplayasdefault)の詳細。  
  
-   **ラベルのように動作**: セット、`OLEMISC_ACTSLIKELABEL`内のビット、`OLEMISC`コンテナーのネイティブのラベルを置換するためのコントロールを有効にするための列挙体です。 コンテナーは、あった場合、このフラグの処理方法を決定します。  
  
 **その他**  
 コントロールの他の動作オプションを設定します。  
  
-   **DC を正規化された**: 自体を描画するで呼び出された場合は、正規化されたデバイス コンテキストを作成するコントロールを設定します。 コントロールの外観を標準化します。 このアクションが、描画の効率が低下します。  
  
-   **ウィンドウのみ**: ウィンドウなしのコントロールであることを指定します。 このオプションを選択しない場合、コントロールはウィンドウなしのオブジェクトをサポートするコンテナー内に自動的にウィンドウなしとウィンドウなしのオブジェクトをサポートしていないコンテナー内に自動的にウィンドウを持つことができます。 このオプションを選択するように強制、ウィンドウなしのオブジェクトをサポートするコンテナーでも、ウィンドウが表示されます。  
  
-   **挿入可能な**: コントロールを表示しておくには、このオプションを選択、**オブジェクトの挿入**Word や Excel などのアプリケーションのダイアログ ボックス。 コントロールは、このダイアログ ボックスを使用して埋め込みオブジェクトをサポートする任意のアプリケーションで挿入できます。  
  
## <a name="see-also"></a>関連項目  
 [ATL コントロール ウィザード](../../atl/reference/atl-control-wizard.md)   
 [サンプルを SUBEDIT: スーパークラス Windows 標準コントロール](http://msdn.microsoft.com/en-us/30e46bdc-ed92-417c-b6b8-359017265a7b)


