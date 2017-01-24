---
title: "プロパティ ページ (MFC) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "プロパティ ページのデータ転送関数 (MFC の)"
  - "プロパティ ページ, グローバル MFC 関数"
ms.assetid: 734f88bc-c776-4136-9b0e-f45c761a45c1
caps.latest.revision: 14
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# プロパティ ページ (MFC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プロパティ ページは、ダイアログ データ エクスチェンジ \(DDX\) に基くデータ マップ機構をサポートすることにより、表示や編集のためのカスタマイズ可能なグラフィカル インターフェイスに、特定の OLE コントロール プロパティの現在値を表示します。  
  
 データ マップ機構は、OLE コントロールの各プロパティにプロパティ ページ コントロールを割り当てます。  コントロール プロパティの値は、プロパティ ページ コントロールのステータスまたは内容を反映します。  プロパティ ページの `DoDataExchange` メンバー関数での **DDP\_** 関数呼び出しによって、プロパティ ページ コントロールとプロパティの間のマップが指定されます。  コントロールのプロパティ ページを使用して入力されたデータを交換する **DDP\_** 関数の一覧を次に示します。  
  
### プロパティ ページ データ転送  
  
|||  
|-|-|  
|[DDP\_CBIndex](../Topic/DDP_CBIndex.md)|コンボ ボックスで選択された文字列のインデックスをコントロールのプロパティにリンクします。|  
|[DDP\_CBString](../Topic/DDP_CBString.md)|コンボ ボックスで選択された文字列をコントロールのプロパティにリンクします。  選択された文字列はプロパティの値と同じ文字から始まっている必要がありますが、すべてが一致していなくてもかまいません。|  
|[DDP\_CBStringExact](../Topic/DDP_CBStringExact.md)|コンボ ボックスで選択された文字列をコントロールのプロパティにリンクします。  選択された文字列とプロパティの文字列値が完全に一致している必要があります。|  
|[DDP\_Check](../Topic/DDP_Check.md)|コントロールのプロパティ ページのチェック ボックスをコントロールのプロパティにリンクします。|  
|[DDP\_LBIndex](../Topic/DDP_LBIndex.md)|リスト ボックスで選択された文字列のインデックスをコントロールのプロパティにリンクします。|  
|[DDP\_LBString](../Topic/DDP_LBString.md)|リスト ボックスで選択された文字列をコントロールのプロパティにリンクします。  選択された文字列はプロパティの値と同じ文字から始まっている必要がありますが、すべてが一致していなくてもかまいません。|  
|[DDP\_LBStringExact](../Topic/DDP_LBStringExact.md)|リスト ボックスで選択された文字列をコントロールのプロパティにリンクします。  選択された文字列とプロパティの文字列値が完全に一致している必要があります。|  
|[DDP\_PostProcessing](../Topic/DDP_PostProcessing.md)|コントロールからのプロパティ値の転送を終了します。|  
|[DDP\_Radio](../Topic/DDP_Radio.md)|コントロールのプロパティ ページのオプション ボタン グループをコントロールのプロパティにリンクします。|  
|[DDP\_Text](../Topic/DDP_Text.md)|コントロールのプロパティ ページのコントロールをコントロールのプロパティにリンクします。  この関数は、**double**、**short**、`BSTR`、**long** など、複数の異なる型のプロパティを処理します。|  
  
 `DoDataExchange` 関数とプロパティ ページの詳細については、「[MFC ActiveX コントロール : プロパティ ページ](../../mfc/mfc-activex-controls-property-pages.md)」を参照してください。  
  
 OLE コントロール用プロパティ ページの作成と管理に使用されるマクロの一覧を次に示します。  
  
### \[プロパティ ページ\]  
  
|||  
|-|-|  
|[BEGIN\_PROPPAGEIDS](../Topic/BEGIN_PROPPAGEIDS.md)|プロパティ ページ ID のリストを開始します。|  
|[END\_PROPPAGEIDS](../Topic/END_PROPPAGEIDS.md)|プロパティ ページ ID のリストを終了します。|  
|[PROPPAGEID](../Topic/PROPPAGEID.md)|コントロール クラスのプロパティ ページを宣言します。|  
  
## 参照  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)