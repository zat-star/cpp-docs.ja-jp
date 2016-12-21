---
title: "COleException クラス | Microsoft Docs"
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
  - "COleException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleException クラス"
  - "例外, OLE"
ms.assetid: 2571e9fe-26cc-42f0-9ad9-8ad5b4311ec1
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleException クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE 操作に関する例外条件を表します。  
  
## 構文  
  
```  
class COleException : public CException  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[COleException::Process](../Topic/COleException::Process.md)|OLE リターン コードにキャッチされた例外に変換されます。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[COleException::m\_sc](../Topic/COleException::m_sc.md)|例外の理由を示すステータス コードが含まれています。|  
  
## 解説  
 `COleException` のクラスは、例外の理由を示すステータス コードを保持するパブリック データ メンバーが含まれています。  
  
 一般に、`COleException` のオブジェクトを直接作成する必要はありません; 代わりに、[AfxThrowOleException](../Topic/AfxThrowOleException.md)を呼び出す必要があります。  
  
 例外の詳細については、" " [例外処理 \(MFC\)](../../mfc/exception-handling-in-mfc.md) と [例外: OLE の例外](../Topic/Exceptions:%20OLE%20Exceptions.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `COleException`  
  
## 必要条件  
 **ヘッダー :** afxdisp.h  
  
## 参照  
 [MFC CALCDRIV サンプル](../../top/visual-cpp-samples.md)   
 [CException クラス](../../mfc/reference/cexception-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)