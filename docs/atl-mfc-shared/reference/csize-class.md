---
title: "CSize クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSize クラス"
  - "次元"
  - "次元, MFC"
  - "SIZE"
ms.assetid: fb2cf85a-0bc1-46f8-892b-309c108b52ae
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# CSize クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

相対座標や位置を実装する [サイズ変更](http://msdn.microsoft.com/library/windows/desktop/dd145106) Windows の構造体と同様に。  
  
## 構文  
  
```  
class CSize : public tagSIZE  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CSize::CSize](../Topic/CSize::CSize.md)|`CSize` オブジェクトを構築します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CSize::operator \-](../Topic/CSize::operator%20-.md)|減算 2 個のサイズ。|  
|[CSize::operator \!\=](../Topic/CSize::operator%20!=.md)|`CSize` とサイズとが非等値の確認。|  
|[CSize::operator \+](../Topic/CSize::operator%20+.md)|2 種類のサイズを追加します。|  
|[CSize::operator \+\=](../Topic/CSize::operator%20+=.md)|`CSize`にサイズを追加します。|  
|[CSize::operator \-\=](../Topic/CSize::operator%20-=.md)|`CSize`からサイズを減算します。|  
|[CSize::operator \=\=](../Topic/CSize::operator%20==.md)|`CSize` とサイズと等しいかどうかを調べます。|  
  
## 解説  
 このクラスは **サイズ変更** の構造から派生します。  これを呼び出す **サイズ変更** を **サイズ変更** の構造体のデータ メンバーがアクセスできるデータ メンバーの `CSize`で、パラメーターの `CSize` を渡すことができることを意味します。  
  
 **サイズ変更** \(および\) `CSize`の **cx** と **cy** のメンバーはパブリックです。  また、`CSize` は **サイズ変更** の構造体を操作するメンバー関数を実装します。  
  
> [!NOTE]
>  `CSize` などの共有ユーティリティ クラスの詳細については、「[共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)」を参照してください。  
  
## 継承階層  
 `tagSIZE`  
  
 `CSize`  
  
## 必要条件  
 **ヘッダー:** atltypes.h  
  
## 参照  
 [MFC MDI サンプル](../../top/visual-cpp-samples.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CRect クラス](../../atl-mfc-shared/reference/crect-class.md)   
 [CPoint クラス](../Topic/CPoint%20Class.md)