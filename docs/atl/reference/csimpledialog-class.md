---
title: "CSimpleDialog クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CSimpleDialog"
  - "CSimpleDialgo"
  - "CSimpleDialog"
  - "ATL.CSimpleDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleDialog クラス"
  - "CSimpleDialog クラス, モーダル ダイアログ ボックス (ATL の)"
  - "ダイアログ ボックス, モーダル"
  - "モーダル ダイアログ ボックス, ATL"
ms.assetid: 2ae65cc9-4f32-4168-aecd-200b4a480fdf
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CSimpleDialog クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、基本的なモーダル ダイアログ ボックスを実装します。  
  
## 構文  
  
```  
  
      template <  
   WORD t_wDlgTemplateID,  
   BOOL t_bCenter = TRUE  
>  
class CSimpleDialog :  
   public CDialogImplBase  
```  
  
#### パラメーター  
 *t\_wDlgTemplateID*  
  
 ダイアログ テンプレート リソースのリソース id。  
  
 *t\_bCenter*  
 ダイアログ オブジェクトがオーナー ウィンドウで中央揃えする場合**TRUE** ; それ **FALSE**。  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CSimpleDialog::DoModal](../Topic/CSimpleDialog::DoModal.md)|モーダル ダイアログ ボックスを作成します。|  
  
## 解説  
 基本的な機能のモーダル ダイアログ ボックスを実装します。  `CSimpleDialog` は、Windows コモン コントロールのみをサポートします。  モーダル ダイアログ ボックスを作成して表示するには、ダイアログ ボックスに既存のリソース テンプレートの名前を指定するこのクラスのインスタンスを作成します。  ダイアログ ボックスのオブジェクトは、ユーザーが定義済みの値を持つコントロールをクリックすると閉じます \(IDOK や IDCANCEL など\)。  
  
 `CSimpleDialog` は、モーダル ダイアログ ボックスのみ行うことができます。  `CSimpleDialog` は、適切なハンドラーにメッセージを指定するには、既定のメッセージ マップを使用してダイアログ ボックスの手順を提供します。  
  
 詳細については、[ダイアログ ボックスの実行](../../atl/implementing-a-dialog-box.md) を参照してください。  
  
## 継承階層  
 `CDialogImplBase`  
  
 `CSimpleDialog`  
  
## 必要条件  
 **Header:** atlwin.h  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)