---
title: "CWinFormsView クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CWinFormsView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWinFormsView クラス"
  - "MFC [C++], Windows フォームのサポート"
  - "Windows フォーム [C++], MFC サポート"
ms.assetid: d597e397-6529-469b-88f5-7f65a6b9e895
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# CWinFormsView クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows フォーム コントロールのホスティング用の汎用機能を MFC ビューとして提供します。  
  
## 構文  
  
```  
class CWinFormsView : public CView;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CWinFormsView::CWinFormsView](../Topic/CWinFormsView::CWinFormsView.md)|`CWinFormsView` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CWinFormsView::GetControl](../Topic/CWinFormsView::GetControl.md)|Windows フォーム コントロールへのポインターを取得します。|  
  
### パブリック演算子  
  
|名前||  
|--------|-|  
|[CWinFormsView::operator Control^](../Topic/CWinFormsView::operator%20Control%5E.md)|Windows フォームのコントロールに型をとしてキャスト ポインター。|  
  
## 解説  
 MFC でのビュー内の .NET Framework Windows フォーム コントロールをホストするために `CWinFormsView` クラスを使用します。  コントロールは、ネイティブ ビューの子で、MFC ビューのクライアント領域全体を占有します。  結果は `CFormView` のビューのようになります、Windows フォーム デザイナーや実行時を利用するための豊富なフォーム ベースのビューを作成するできます。  
  
 Windows フォームの使い方の詳細については、「[MFC での Windows フォーム ユーザー コントロールの使用](../../dotnet/using-a-windows-form-user-control-in-mfc.md)」を参照してください。  
  
> [!NOTE]
>  MFC Windows は、MFC \(AFXDLL が定義されているプロジェクトに動的にリンクするプロジェクトにのみ統合する作業を形成します。  
  
> [!NOTE]
>  CWinFormsView は、MFC の分割ウィンドウ \([CSplitterWnd クラス](../../mfc/reference/csplitterwnd-class.md)\) をサポートしていません。  現在の分割線の Windows フォーム コントロール \(<xref:System.Windows.Forms.Splitter>\) のみサポートされます。  
  
## 必要条件  
 **ヘッダー:** afxwinforms.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CWinFormsControl クラス](../../mfc/reference/cwinformscontrol-class.md)   
 [CWinFormsDialog クラス](../Topic/CWinFormsDialog%20Class.md)   
 [CFormView クラス](../../mfc/reference/cformview-class.md)