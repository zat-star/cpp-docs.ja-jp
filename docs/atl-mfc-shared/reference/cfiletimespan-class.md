---
title: "CFileTimeSpan クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFileTimeSpan"
  - "ATL.CFileTimeSpan"
  - "ATL::CFileTimeSpan"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFileTimeSpan クラス"
  - "共有クラス, CFileTimeSpan"
ms.assetid: 5856fb39-9c82-4027-8ccf-8760890491ec
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# CFileTimeSpan クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、ファイルに関連付けられた相対日付と時刻の値を管理するためのメソッドを提供します。  
  
## 構文  
  
```  
  
class CFileTimeSpan  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CFileTimeSpan::CFileTimeSpan](../Topic/CFileTimeSpan::CFileTimeSpan.md)|コンストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CFileTimeSpan::GetTimeSpan](../Topic/CFileTimeSpan::GetTimeSpan.md)|`CFileTimeSpan` のオブジェクトから時刻を取得するときにこのメソッドを呼び出します。|  
|[CFileTimeSpan::SetTimeSpan](../Topic/CFileTimeSpan::SetTimeSpan.md)|`CFileTimeSpan` のオブジェクトの時刻を設定するには、このメソッドを呼び出します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CFileTimeSpan::operator \-](../Topic/CFileTimeSpan::operator%20-.md)|`CFileTimeSpan` のオブジェクトの減算を実行します。|  
|[CFileTimeSpan::operator \!\=](../Topic/CFileTimeSpan::operator%20!=.md)|非等値の `CFileTimeSpan` の 2 種類のオブジェクトを比較します。|  
|[CFileTimeSpan::operator \+](../Topic/CFileTimeSpan::operator%20+.md)|`CFileTimeSpan` オブジェクトの追加を実行します。|  
|[CFileTimeSpan::operator \+\=](../Topic/CFileTimeSpan::operator%20+=.md)|`CFileTimeSpan` オブジェクトの追加を実行し、現在のオブジェクトに結果を代入します。|  
|[CFileTimeSpan::operator \<](../Topic/CFileTimeSpan::operator%20%3C.md)|`CFileTimeSpan` の 2 種類のオブジェクトは少なくを決定する比較します。|  
|[CFileTimeSpan::operator \<\=](../Topic/CFileTimeSpan::operator%20%3C=.md)|`CFileTimeSpan` の 2 種類のオブジェクトの等価性や小さいかを判断する比較します。|  
|[CFileTimeSpan::operator \=](../Topic/CFileTimeSpan::operator%20=.md)|代入演算子です。|  
|[CFileTimeSpan::operator \-\=](../Topic/CFileTimeSpan::operator%20-=.md)|`CFileTimeSpan` のオブジェクトの減算を実行し、現在のオブジェクトに結果を代入します。|  
|[CFileTimeSpan::operator \=\=](../Topic/CFileTimeSpan::operator%20==.md)|等価性の `CFileTimeSpan` の 2 種類のオブジェクトを比較します。|  
|[CFileTimeSpan::operator \>](../Topic/CFileTimeSpan::operator%20%3E.md)|`CFileTimeSpan` のオブジェクトを 2 つを超える決定する比較します。|  
|[CFileTimeSpan::operator \>\=](../Topic/CFileTimeSpan::operator%20%3E=.md)|`CFileTimeSpan` の 2 種類のオブジェクトをより大きいか等しいかどうかを確認します。比較します。|  
  
## 解説  
 このクラスは、頻繁に使用される相対的な期間を管理するファイルが、最後にアクセスまたは最終更新作成時に操作を実行するときに使用するメソッドを提供します。  このクラスのメソッドは [CFileTime のクラス](../../atl-mfc-shared/reference/cfiletime-class.md) のオブジェクトとともによく使用されます。  
  
## 使用例  
 [CFileTime::Millisecond](../Topic/CFileTime::Millisecond.md)の例を参照してください。  
  
## 必要条件  
 **ヘッダー :** atltime.h  
  
## 参照  
 [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284)   
 [CFileTime クラス](../../atl-mfc-shared/reference/cfiletime-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC の共有クラス](../../atl-mfc-shared/atl-mfc-shared-classes.md)