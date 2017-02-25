---
title: "CComboBoxEx クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComboBoxEx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComboBoxEx クラス"
  - "コンボ ボックス [C++], CComboBoxEx クラス"
  - "コモン コントロール [C++], 拡張コンボ ボックス"
  - "拡張コンボ ボックス, CComboBoxEx クラス"
  - "Internet Explorer 4.0 コモン コントロール"
  - "Windows コモン コントロール [C++], 拡張コンボ ボックス"
ms.assetid: 33ca960a-2409-478c-84a4-a2ee8ecfe8f7
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# CComboBoxEx クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

イメージ リストをサポートすることにより、コンボ ボックス コントロールを拡張します。  
  
## 構文  
  
```  
class CComboBoxEx : public CComboBox  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CComboBoxEx::CComboBoxEx](../Topic/CComboBoxEx::CComboBoxEx.md)|`CComboBoxEx` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CComboBoxEx::Create](../Topic/CComboBoxEx::Create.md)|コンボ ボックスを作成し、`CComboBoxEx` のオブジェクトにアタッチします。|  
|[CComboBoxEx::CreateEx](../Topic/CComboBoxEx::CreateEx.md)|指定されたウィンドウの拡張スタイルのコンボ ボックスを作成し、**ComboBoxEx** のオブジェクトにアタッチします。|  
|[CComboBoxEx::DeleteItem](../Topic/CComboBoxEx::DeleteItem.md)|**ComboBoxEx** のコントロールから項目を削除します。|  
|[CComboBoxEx::GetComboBoxCtrl](../Topic/CComboBoxEx::GetComboBoxCtrl.md)|子コンボ ボックス コントロールへのポインターを取得します。|  
|[CComboBoxEx::GetEditCtrl](../Topic/CComboBoxEx::GetEditCtrl.md)|**ComboBoxEx** のコントロールのエディット コントロール部分にハンドルを取得します。|  
|[CComboBoxEx::GetExtendedStyle](../Topic/CComboBoxEx::GetExtendedStyle.md)|**ComboBoxEx** のコントロールに使用中の拡張スタイルを取得します。|  
|[CComboBoxEx::GetImageList](../Topic/CComboBoxEx::GetImageList.md)|**ComboBoxEx** のコントロールにイメージ リストへのポインターを取得します。|  
|[CComboBoxEx::GetItem](../Topic/CComboBoxEx::GetItem.md)|**ComboBoxEx** の特定の項目の項目の情報を取得します。|  
|[CComboBoxEx::HasEditChanged](../Topic/CComboBoxEx::HasEditChanged.md)|ユーザーが入力して **ComboBoxEx** の編集コントロールの内容を変更したかどうかを判断します。|  
|[CComboBoxEx::InsertItem](../Topic/CComboBoxEx::InsertItem.md)|**ComboBoxEx** のコントロールの新しい項目を挿入します。|  
|[CComboBoxEx::SetExtendedStyle](../Topic/CComboBoxEx::SetExtendedStyle.md)|**ComboBoxEx** 内のコントロール セットによって拡張スタイル。|  
|[CComboBoxEx::SetImageList](../Topic/CComboBoxEx::SetImageList.md)|**ComboBoxEx** のコントロールのイメージ リストを設定します。|  
|[CComboBoxEx::SetItem](../Topic/CComboBoxEx::SetItem.md)|**ComboBoxEx** のコントロール内の項目の属性を設定します。|  
|[CComboBoxEx::SetWindowTheme](../Topic/CComboBoxEx::SetWindowTheme.md)|拡張コンボ ボックス コントロールでの視覚スタイルを設定します。|  
  
## 解説  
 `CComboBoxEx` でコンボ ボックス コントロールを作成すると、イメージ描画用のコードを独自に実装する必要がなくなります。  `CComboBoxEx` では、イメージ リストのイメージが使用できます。  
  
## イメージ リストのサポート  
 標準コンボ ボックスの場合、コンボ ボックスのオーナーがイメージを描画します。つまり、オーナー描画コントロールとしてコンボ ボックスを作成します。  `CComboBoxEx` では、描画スタイル **CBS\_OWNERDRAWFIXED** と **CBS\_HASSTRINGS** は暗黙的に指定されるため、この 2 つの描画スタイルを設定する必要はありません。  **CComboBoxEx** を使用しない場合は、描画を実行するコードを作成する必要があります。  `CComboBoxEx` コントロールでは、項目ごとに最大 3 つのイメージを使用できます。選択された状態、選択されていない状態、オーバーレイ イメージの 3 つです。  
  
## スタイル  
 `CComboBoxEx` は、**CBS\_SIMPLE**、**CBS\_DROPDOWN**、**CBS\_DROPDOWNLIST**、**WS\_CHILD** の 4 スタイルをサポートします。  ウィンドウ作成時にこれ以外のスタイルを指定しても、コントロールによって無視されます。  ほかのコンボ ボックス スタイルを指定するには、ウィンドウの作成後に `CComboBoxEx` のメンバー関数 [SetExtendedStyle](../Topic/CComboBoxEx::SetExtendedStyle.md) を呼び出します。  これらのスタイルを使用して、以下のことができます。  
  
-   リスト内の文字列検索時に大文字と小文字を区別する。  
  
-   スラッシュ \('\/'\)、円記号 \('\\'\)、およびピリオド \('.'\) を単語区切りとして使用するコンボ ボックス コントロールを作成する。  ショートカット キー \(Ctrl キーと方向キーの組み合わせ\) で単語間を移動できるようになります。  
  
-   コンボ ボックス コントロールでのイメージの表示\/非表示を設定する。  イメージを表示しない場合は、イメージ配置用のインデントをコンボ ボックスから削除できます。  
  
-   幅の狭いコンボ ボックス コントロールを作成する。このコンボ ボックス コントロールより幅の広いコンボ ボックスは切り取られます。  
  
 これらのスタイル フラグの詳細については、「[CComboBoxEx の使い方](../../mfc/using-ccomboboxex.md)」を参照してください。  
  
## 項目の保存属性とコールバック属性  
 項目情報、つまり項目とイメージのインデックス、インデントの値、テキスト文字列などの情報は、Win32 [COMBOBOXEXITEM](http://msdn.microsoft.com/library/windows/desktop/bb775746) 構造体に格納されます。詳細については、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] を参照してください。  この構造体には、コールバック フラグ用のメンバーもあります。  
  
 概念の詳細については、「[CComboBoxEx の使い方](../../mfc/using-ccomboboxex.md)」を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CComboBox](../../mfc/reference/ccombobox-class.md)  
  
 `CComboBoxEx`  
  
## 必要条件  
 **ヘッダー :** afxcmn.h  
  
## 参照  
 [MFC MFCIE サンプル](../../top/visual-cpp-samples.md)   
 [CComboBox クラス](../../mfc/reference/ccombobox-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CComboBox クラス](../../mfc/reference/ccombobox-class.md)