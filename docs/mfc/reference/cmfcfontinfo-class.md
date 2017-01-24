---
title: "CMFCFontInfo クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCFontInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCFontInfo クラス"
  - "CMFCFontInfo::CMFCFontInfo コンストラクター"
ms.assetid: f88329b2-d74e-4921-9441-a3bb6536a049
caps.latest.revision: 26
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCFontInfo クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCFontInfo` クラスは、フォントの名前とその他の属性を説明します。  
  
## 構文  
  
```  
class CMFCFontInfo : public CObject  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|`CMFCFontInfo`|`CMFCFontInfo` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCFontInfo::GetFullName](../Topic/CMFCFontInfo::GetFullName.md)|フォントおよびフォントの文字セット \(スクリプト\) を連結した名前を取得します。|  
  
### データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CMFCFontInfo::m\_nCharSet](../Topic/CMFCFontInfo::m_nCharSet.md)|フォントに関連付けられている文字セット \(スクリプト\) を示す値。|  
|[CMFCFontInfo::m\_nPitchAndFamily](../Topic/CMFCFontInfo::m_nPitchAndFamily.md)|フォントのピッチとファミリを示す値。|  
|[CMFCFontInfo::m\_nType](../Topic/CMFCFontInfo::m_nType.md)|フォントの種類を示す値。|  
|[CMFCFontInfo::m\_strName](../Topic/CMFCFontInfo::m_strName.md)|フォント名 \(**Arial** など\) です。|  
|[CMFCFontInfo::m\_strScript](../Topic/CMFCFontInfo::m_strScript.md)|フォントに関連付けられている文字セット \(スクリプト\) の名前です。|  
  
## 解説  
 `CMFCFontInfo` オブジェクトは [CMFCToolBarFontComboBox クラス](../../mfc/reference/cmfctoolbarfontcombobox-class.md) クラスのアイテムにアタッチできます。  `CMFCFontInfo` オブジェクトへのポインターを取得するには、[CMFCToolBarFontComboBox::GetFontDesc](../Topic/CMFCToolBarFontComboBox::GetFontDesc.md) メソッドを呼び出します。  
  
## 使用例  
 `CMFCFontInfo` クラスのさまざまなメンバーの使用方法を次の例に示します。  この例では、`CMFCRibbonFontComboBox` から `CMFCFontInfo` オブジェクトを取得して、そのローカル変数にアクセスする方法を説明します。  この例は、[MSOffice 2007 Demo サンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!CODE [NVC_MFC_MSOffice2007Demo#6](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_MSOffice2007Demo#6)]  
  
## 必要条件  
 **ヘッダー :** afxtoolbarfontcombobox.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCToolBarFontComboBox クラス](../../mfc/reference/cmfctoolbarfontcombobox-class.md)   
 [CMFCToolBarFontSizeComboBox クラス](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)